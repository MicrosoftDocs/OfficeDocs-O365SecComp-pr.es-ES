---
title: Evitar caracteres no válidos en las reglas de filtro de correo no deseado y la Directiva de filtro de correo no deseado
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 9/24/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Proporciona ayuda a los administradores que tienen caracteres no válidos en la configuración contra correo no deseado y tienen problemas al intentar usar el centro &amp; de seguridad y cumplimiento.
ms.openlocfilehash: 0e7dcb40d8e54045caa55083e2cbf0585a80869d
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154171"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a>Evitar caracteres no válidos en las reglas de filtro de correo no deseado y Directiva de filtro de correo no deseado 

Anteriormente, los administradores de Office 365 instalaron y configuraron reglas de filtro de correo no deseado y la Directiva de filtro de correo no deseado mediante el centro de administración de Exchange (EAC). Ahora, puede usar el centro &amp; de seguridad y cumplimiento para administrar la configuración contra correo no deseado. Los siguientes caracteres se admitiron en el EAC, pero no se admiten para su &amp; uso en el centro de seguridad y cumplimiento.  

**Caracteres no válidos:**
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

Si las reglas de filtro de correo no deseado o la Directiva de filtro de correo no deseado contienen alguno de los caracteres no válidos, puede encontrarse alguno o todos estos problemas:
- Es posible que no pueda encontrar la Directiva o las reglas en el &amp; centro de seguridad y cumplimiento.
- Es posible que reciba errores al intentar obtener las reglas o la Directiva mediante Windows PowerShell.
- Es posible que la Directiva o la configuración no se ejecuten o no funcionen de la manera esperada.

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a>Quitar los caracteres no válidos de la Directiva y reglas del filtro de correo no deseado

Una vez que haya identificado la Directiva y las reglas que contienen caracteres no válidos, puede cambiar los nombres con los cmdlets de Windows PowerShell. 

1. [Conéctese a Exchange online mediante PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
    
2. Para cambiar el nombre de la Directiva de filtro de correo no deseado, ejecute el cmdlet Set-HostedContentFilterPolicy de la siguiente manera:
    
    ```
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. Para cambiar el nombre de una regla de filtro de correo no deseado, ejecute el cmdlet Set-HostedContentFilterRule de la siguiente manera:
    
    ```
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a>Más información

[Administración de amenazas en el &amp; centro de seguridad y cumplimiento](threat-management.md)
  
[Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy?view=exchange-ps)

[Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule?view=exchange-ps)

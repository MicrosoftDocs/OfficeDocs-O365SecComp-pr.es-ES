---
title: Evitar los caracteres no válidos en la directiva de filtro de correo y las reglas de filtro de spam
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 9/24/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Proporciona ayuda para los administradores que tienen caracteres no válidos en su configuración contra correo no deseado y ejecutan en problemas cuando se intenta usar la seguridad &amp; centro de cumplimiento.
ms.openlocfilehash: ca409b4daa7bec01417adb7cbfdfa2a128929e81
ms.sourcegitcommit: c168410974bc90aaf55f1dcaa9e05c09b2b78d76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25018739"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a>Evitar los caracteres no válidos en las reglas de filtro de spam y directiva de filtro de correo no deseado 

Anteriormente, los administradores de Office 365 configuración y configurar la directiva de filtro de correo y las reglas de filtro de spam mediante el centro de administración de Exchange (EAC). Ahora, use la seguridad &amp; centro de cumplimiento para administrar la su configuración contra correo no deseada. Los siguientes caracteres se admitían en el CEF pero no son compatibles para su uso en la seguridad &amp; centro de cumplimiento.  

**Caracteres no válidos:**
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

Si las reglas de filtro de spam o la directiva de filtro de spam contiene cualquiera de los caracteres no válidos, se podrían encontrarse con cualquier o todos estos problemas:
- Es posible que no se puede encontrar la directiva o las reglas en la seguridad &amp; centro de cumplimiento.
- Es posible que reciba errores al intentar obtener las reglas o directivas mediante Windows PowerShell.
- Es posible que la directiva o configuración de no ejecutar o realizar según lo previsto.

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a>Quitar los caracteres no válidos de la directiva de filtro de spam y reglas

Una vez que haya identificado la directiva y las reglas que contienen caracteres no válidos, puede cambiar los nombres mediante el uso de los cmdlets de Windows PowerShell. 

1. [Conectarse a Exchange Online mediante PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
    
2. Para cambiar el nombre de la directiva de filtro de spam, ejecute el cmdlet Set-HostedContentFilterPolicy como sigue:
    
    ```
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. Para cambiar el nombre de una regla de filtro de spam, ejecute el cmdlet Set-HostedContentFilterRule como sigue:
    
    ```
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a>Más información

[Administración de la seguridad de amenazas &amp; centro de cumplimiento](threat-management.md)
  
[Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy?view=exchange-ps)

[Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule?view=exchange-ps)

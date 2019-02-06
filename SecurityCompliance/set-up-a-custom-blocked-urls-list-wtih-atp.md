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
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a>Configurar una lista personalizada de direcciones URL bloqueada mediante Office 365 ATP seguros vínculos

Con [Office 365 avanzada una protección contra amenazas](office-365-atp.md) (ATP), la organización puede tener una lista personalizada de direcciones de sitios Web (URL) que están bloqueados. Cuando se bloquea una dirección URL, se toman las personas que haga clic en vínculos a la dirección URL bloqueada a una [página de advertencia](atp-safe-links-warning-pages.md) que es similar a la siguiente imagen: 
  
![Este sitio está bloqueado](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
Se define la lista de direcciones URL bloqueadas por el equipo de seguridad de Office 365 de su organización, y esa lista se aplica a todas las personas de la organización que está cubierta por las directivas de Office 365 ATP seguros vínculos. 
  
Lea este artículo para obtener información sobre cómo configurar la lista de direcciones URL personalizada bloqueada de su organización para [ATP vínculos seguros en Office 365](atp-safe-links.md).
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>Ver o editar una lista personalizada de direcciones URL bloqueadas

[ATP vínculos seguros en Office 365](atp-safe-links.md) usa varias listas, incluida la lista de direcciones URL personalizada bloqueada de su organización. Si tiene los permisos necesarios, puede configurar la lista personalizada de su organización. Para ello, mediante la edición de la directiva de su organización predeterminada vínculos seguros.

Para editar las directivas de ATP (o definir), debe asignar uno de los roles que se describen en la siguiente tabla: 

|Rol  |Dónde y cómo asignado  |
|---------|---------|
|Administrador Global de Office 365 |La persona que se registra para comprar Office 365 es un administrador global de forma predeterminada. (Consulte [acerca de Office 365 roles de administrador](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para obtener más información).         |
|Administrador de seguridad de Office 365 |Centro de administración ([https://aka.ms/admincenter](https://aka.ms/admincenter))|
|Administración de la organización en línea de Exchange |Centro de administración de Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>o <br>  Cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
  
1. Vaya a [https://protection.office.com](https://protection.office.com) y el inicio de sesión con la cuenta de trabajo o escuela. 
    
2. En la izquierda, en **administración de amenaza**, elija **Directiva** \> **Vínculos seguros**.
    
3. En la sección de **directivas que se aplican a toda la organización** , seleccione **predeterminado**y, a continuación, elija **Editar** (el botón Editar se parece a un lápiz).<br/>![Haga clic en Editar para editar la directiva predeterminada para la protección de vínculos seguros](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)<br/>Permite ver la lista de direcciones URL bloqueadas. En primer lugar, puede que no tenga todas las direcciones URL que se muestran aquí.<br/>![Lista de direcciones URL en la directiva predeterminada de vínculos seguros bloqueados](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. Seleccione el cuadro **Escriba una dirección URL válida** , escriba una dirección URL y, a continuación, seleccione el signo más (**+**). 

5. Cuando haya terminado de agregar las direcciones URL, en la esquina inferior derecha de la pantalla, elija **Guardar**.
    
## <a name="a-few-things-to-keep-in-mind"></a>Algunas cosas que debe tener en cuenta

Mientras se agregan las direcciones URL a la lista, tenga en cuenta los siguientes puntos: 

- No incluya una barra diagonal ( **/**) al final de la dirección URL. Por ejemplo, en lugar de escribir `http://www.contoso.com/`, escriba `http://www.contoso.com`.
    
- Puede especificar una dirección URL de dominio (como `contoso.com` o `tailspintoys.com`). Esto bloqueará clics en cualquier dirección URL que contiene el dominio.

- Puede especificar un subdominio (al igual que `toys.contoso.com*`) sin bloquear un dominio completo (como `contoso.com`). Esto le permitirá bloque hace clic en cualquier dirección URL que contiene el subdominio, pero no puede bloquear clics a una dirección URL que contiene el dominio completo.  
    
- Puede incluir hasta tres asteriscos comodín (\*) por la dirección URL. La siguiente tabla se enumeran algunos ejemplos de lo que puede escribir y el efecto que esas entradas tienen.
    
|**Entrada de ejemplo**|**Para qué sirve**|
|:-----|:-----|
|`contoso.com`o`*contoso.com*`  <br/> |Bloquea el dominio, subdominios y rutas de acceso, como `https://www.contoso.com`, `http://sub.contoso.com`, y`http://contoso.com/abc`  <br/> |
|`http://contoso.com/a`  <br/> |Bloquea un sitio `http://contoso.com/a` pero subtrazados no adicionales, como`http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a*`  <br/> |Bloquea un sitio `http://contoso.com/a` y subtrazados adicionales, como`http://contoso.com/a/b`  <br/> |
|`http://toys.contoso.com*`  <br/> |Bloques de un subdominio ("toys" en este caso), pero permiten a los clics a otras direcciones URL de dominio (como `http://contoso.com` o `http://home.contoso.com`).  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a>Procedimiento para definir excepciones para determinados usuarios en una organización

Si desea que ciertos grupos puedan ver las direcciones URL que podrían estar bloqueadas para que otros usuarios, puede especificar una directiva de vínculos seguros de ATP que se aplica a determinados destinatarios. Consulte [Configurar una "no reescritura" las direcciones URL de lista personalizada con vínculos seguros de ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
  


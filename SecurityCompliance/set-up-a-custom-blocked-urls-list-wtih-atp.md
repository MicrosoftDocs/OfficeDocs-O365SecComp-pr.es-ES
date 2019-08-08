---
title: Configurar una lista de direcciones URL bloqueadas personalizadas con los vínculos seguros de Office 365 ATP
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo configurar una lista de direcciones URL bloqueadas para su organización mediante la protección contra amenazas avanzada de Office 365. Las direcciones URL bloqueadas se aplicarán a los mensajes de correo electrónico y documentos de Office de acuerdo con las directivas de vínculos seguros de ATP.
ms.openlocfilehash: 8d2b93fca599359ec1c6f4b4b3794ee2ccb466fe
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230334"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a>Configurar una lista de direcciones URL bloqueadas personalizadas con los vínculos seguros de Office 365 ATP

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen la [protección contra amenazas avanzada de Office 365](office-365-atp.md). Si es un usuario doméstico que busca información sobre vínculos seguros en Outlook, consulte [Advanced Outlook.com Security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

Con [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), su organización puede tener una lista personalizada de direcciones de sitios web (URL) que están bloqueadas. Cuando se bloquea una dirección URL, los usuarios que hacen clic en los vínculos a la dirección URL bloqueada se toman en una [Página de advertencia](atp-safe-links-warning-pages.md) similar a la siguiente: 
  
![Este sitio está bloqueado](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
La lista de URL bloqueadas se define en el equipo de seguridad de Office 365 de su organización y esa lista se aplica a todas las personas de la organización que están cubiertas por las directivas de vínculos seguros de ATP de Office 365. 
  
Lea este artículo para obtener información sobre cómo configurar la lista de direcciones URL bloqueadas personalizadas de la organización para [vínculos seguros de ATP en Office 365](atp-safe-links.md).
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>Ver o editar una lista personalizada de direcciones URL bloqueadas

[Vínculos seguros de ATP en Office 365](atp-safe-links.md) usa varias listas, incluida la lista de direcciones URL bloqueadas personalizadas de la organización. Si tiene los permisos necesarios, puede configurar la lista personalizada de su organización. Para ello, edite la Directiva de vínculos a prueba de errores predeterminada de su organización.

Para editar (o definir) las directivas de ATP, debe tener asignado uno de los roles descritos en la siguiente tabla: 

|Role  |Dónde y cómo se asigna  |
|---------|---------|
|Administrador global de Office 365 |La persona que se registra para comprar Office 365 es un administrador global de forma predeterminada. (Consulte [acerca de los roles de administrador de Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para obtener más información).         |
|Administrador de seguridad |Centro de administración de Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ()|
|Administración de la organización de Exchange Online |Centro de administración de[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>o <br>  Cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

> [!TIP]
> Para obtener más información acerca de los roles y los permisos, consulte Permissions [in the Office 365 &amp; Security Compliance Center](permissions-in-the-security-and-compliance-center.md).

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a>Para ver o editar una lista de direcciones URL bloqueadas personalizadas
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa. 
    
2. En el panel de navegación izquierdo, en **Administración de amenazas**, elija **vínculos seguros**de **Directiva** \> .
    
3. En la sección **directivas que se aplican a toda la organización** , seleccione predeterminado y, a continuación, elija **Editar** (el botón Editar **es**similar a un lápiz).<br/>![Haga clic en Editar para editar la directiva predeterminada para protección de vínculos seguros](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)<br/>Esto le permite ver la lista de direcciones URL bloqueadas. En primer lugar, es posible que no tenga ninguna dirección URL mencionada aquí.<br/>![Lista de direcciones URL bloqueadas en la Directiva de vínculos seguros predeterminada](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. Seleccione el cuadro **Escriba una dirección URL válida** , escriba una dirección URL y, a continuación, elija**+** el signo más (). 

5. Cuando termine de agregar direcciones URL, en la esquina inferior derecha de la pantalla, elija **Guardar**.
    
## <a name="a-few-things-to-keep-in-mind"></a>Algunas cosas que debe tener en cuenta

Mientras agrega direcciones URL a la lista, tenga en cuenta los siguientes puntos: 

- No incluya una barra diagonal ( **/**) al final de la dirección URL. Por ejemplo, en lugar de escribir `http://www.contoso.com/`, escriba `http://www.contoso.com`.
    
- Puede especificar una dirección URL de solo dominio (like `contoso.com` o `tailspintoys.com`). Esto impedirá que se haga clic en cualquier dirección URL que contenga el dominio.

- Puede especificar un subdominio (como `toys.contoso.com*`) sin bloquear un dominio completo (como `contoso.com`). Este bloque hará clic en cualquier dirección URL que contenga el subdominio, pero no bloqueará los clics en una dirección URL que contenga el dominio completo.  
    
- Puede incluir hasta tres asteriscos comodín (\*) por dirección URL. En la tabla siguiente se enumeran algunos ejemplos de lo que se puede especificar y el efecto que tienen dichas entradas.
    
|**Entrada de ejemplo**|**Qué hace**|
|:-----|:-----|
|`contoso.com` o `*contoso.com*`  <br/> |Bloquea el dominio, los subdominios y las rutas de los `https://www.contoso.com`, `http://sub.contoso.com`como, y`http://contoso.com/abc`  <br/> |
|`http://contoso.com/a`  <br/> |Bloquea un sitio `http://contoso.com/a` , pero no otros subtrazados adicionales como`http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a*`  <br/> |Bloquea un sitio `http://contoso.com/a` y subrutas adicionales como`http://contoso.com/a/b`  <br/> |
|`http://toys.contoso.com*`  <br/> |Bloquea un subdominio ("juguetes" en este caso), pero permite hacer clic en otras direcciones URL de `http://contoso.com` dominio `http://home.contoso.com`(como o).  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a>Cómo definir excepciones para determinados usuarios de una organización

Si desea que determinados grupos puedan ver direcciones URL que puedan estar bloqueadas para otros usuarios, puede especificar una directiva de vínculos seguros ATP que se aplique a destinatarios específicos. Consulte [configurar una lista de direcciones URL personalizadas "no reescribir" mediante vínculos seguros de ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
  


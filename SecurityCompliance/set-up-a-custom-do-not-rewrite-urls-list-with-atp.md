---
title: Configurar una lista personalizada de direcciones URL de reescritura de no hacer con Office 365 ATP seguros vínculos
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection: M365-security-compliance
description: Al configurar las directivas de vínculos seguros de ATP, puede incluir una reescritura de no hacer ' lista de direcciones URL para habilitar algunas personas de la organización visitar sitios que se incluyen en la lista.
ms.openlocfilehash: 87a245e2f21408cd06d483ec5fdcdac47ce7e317
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995381"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a>Configurar una lista personalizada de direcciones URL de reescritura de no hacer con Office 365 ATP seguros vínculos

> [!IMPORTANT]
> En este artículo está destinada a los clientes empresariales. Si es un usuario particular para obtener más información acerca de los vínculos seguros en Outlook, vea [seguridad de Outlook.com avanzadas](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

Con [Office 365 avanzada una protección contra amenazas](office-365-atp.md) (ATP), la organización puede tener un [URL bloqueadas personalizadas](set-up-a-custom-blocked-urls-list-wtih-atp.md), por ejemplo, que cuando haga clic en personas en web direcciones (URL) en mensajes de correo electrónico o de determinados documentos de Office, se impide que se va a esas direcciones. La organización también puede tener listas personalizadas "no reescritura" para grupos específicos de la organización. Una lista "no reescritura" permite algunas personas visitar las direcciones URL que en caso contrario, están bloqueadas por [ATP vínculos seguros en Office 365](atp-safe-links.md). 
  
En este artículo se describe cómo especificar una lista de direcciones URL que se excluyen de examen de vínculos seguros de ATP y algunos puntos importantes que deben tenerse en cuenta.

## <a name="set-up-a-do-not-rewrite-list"></a>Configurar una lista "no reescritura de"

Protección de vínculos seguros de ATP utiliza varias listas, incluida la lista de direcciones URL bloqueadas de la organización y las listas de "no volver a escribir" para las excepciones. Si tiene los permisos necesarios, puede configurar las listas personalizadas "no reescritura de". Para ello, al agregar o editar las directivas de seguros vínculos que se aplican a determinados destinatarios en la organización. 

Para editar las directivas de ATP (o definir), debe asignar uno de los roles que se describen en la siguiente tabla:

|Rol  |Dónde y cómo asignado  |
|---------|---------|
|Administrador Global de Office 365 |La persona que se registra para comprar Office 365 es un administrador global de forma predeterminada. (Consulte [acerca de Office 365 roles de administrador](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para obtener más información).         |
|Administrador de seguridad |Centro de administración de Azure Active Directory ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Administración de la organización en línea de Exchange |Centro de administración de Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>o <br>  Cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

> [!TIP]
> Para obtener más información sobre los roles y permisos, vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>Para ver o editar una lista de direcciones URL personalizada "no reescritura de"
  
1. Vaya a [https://protection.office.com](https://protection.office.com) y el inicio de sesión con la cuenta de trabajo o escuela. 
    
2. En la izquierda, en **administración de amenaza** \> **Directiva** \> **Vínculos seguros**.
    
3. En la sección de **directivas que se aplican a determinados destinatarios** , elija **nuevo** (el botón nuevo se parece a un signo más ( **+**)) para crear una nueva directiva. (Como alternativa, puede editar una directiva existente).<br/>![Elija nuevo para agregar una directiva de vínculos seguros para los destinatarios de correo electrónico específica](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
4. Especifique un nombre y una descripción para la directiva.
    
5. En la sección **no de reescritura de las siguientes direcciones URL** , seleccione el cuadro **Escriba una dirección URL válida** y, a continuación, escriba una dirección URL y, a continuación, elija el signo más (+). 
    
6. En la sección **Aplicar a** , elija **el destinatario es un miembro de**y, a continuación, elija el grupo o grupos que desea incluir en la directiva. Elija **Agregar**y, a continuación, elija **Aceptar**.
    
7. Cuando haya terminado de agregar las direcciones URL, en la esquina inferior derecha de la pantalla, elija **Guardar**.
    
> [!NOTE]
> Asegúrese de revisar la lista personalizada de la organización de las URL bloqueadas. Consulte [Configurar una lista de direcciones URL bloqueada personalizada con vínculos seguros de ATP](set-up-a-custom-blocked-urls-list-wtih-atp.md). 
  
## <a name="important-points-to-keep-in-mind"></a>Puntos importantes que deben tenerse en cuenta

- Cualquier dirección URL que especifique en la lista "no reescritura" se excluye de vínculos seguros ATP análisis para los destinatarios que especifique.
 
- Cuando se especifica una lista de "no volver a escribir" para una directiva de vínculos seguros ATP, puede incluir hasta tres asteriscos comodín (\*). Caracteres comodín (\*) se supone que las entradas de como `contoso.com`, que no explícitamente incluir prefijos o subdominios, como `http://` o `https://`. Esto significa que una entrada, como `contoso.com` es similar a `*contoso.com*` para la lista de "no volver a escribir".

- Si ya tiene una lista de direcciones URL en la lista de "no reescritura", asegúrese de revisar esa lista y agregue caracteres comodín según corresponda. Por ejemplo, si la lista existente tiene una entrada como `http://contoso.com/a` y desea incluir subrutas como `http://contoso.com/a/b` en la directiva, agregue un carácter comodín a la entrada para el aspecto `http://contoso.com/a*`.
    
- No incluya una barra diagonal (/) en las direcciones URL que especifique en la lista de "no volver a escribir". Por ejemplo, en lugar de escribir `contoso.com/` en la lista de "no reescritura", escriba `contoso.com`.
    
Tienen los siguientes ejemplos de listas de tabla de lo que puede escribir y el efecto que esas entradas.
    
|**Entrada de ejemplo**|**Para qué sirve**|
|:-----|:-----|
|`*contoso.com*`  <br/> |Permite a los destinatarios específicos visite un dominio, subdominios y rutas de acceso, como `http://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, o`http://www.contoso.com/a`  <br/> |
|`http://contoso.com/a`  <br/> |Permite a los destinatarios específicos a visitar un sitio como `http://contoso.com/a`, pero no subtrazados like`http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a*`  <br/> |Permite a los destinatarios específicos a visitar un sitio como `http://contoso.com/a` y subtrazados como`http://contoso.com/a/b`  <br/> |
   
 
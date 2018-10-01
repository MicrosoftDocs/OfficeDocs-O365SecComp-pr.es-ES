---
title: Configurar una lista personalizada de direcciones URL de reescritura de no hacer con Office 365 ATP seguros vínculos
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
description: Al configurar las directivas de vínculos seguros de ATP, puede incluir una reescritura de no hacer ' lista de direcciones URL para habilitar algunas personas de la organización visitar sitios que se incluyen en la lista.
ms.openlocfilehash: 3ce783a3f783889bdc59ad8d412c80a79e7dd914
ms.sourcegitcommit: 7032830867eb3fc71760e04b8342aff174c5d757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "25353266"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a>Configurar una lista personalizada de direcciones URL de reescritura de no hacer con Office 365 ATP seguros vínculos

Con [Office 365 avanzada una protección contra amenazas](office-365-atp.md) (ATP), la organización puede tener un [URL bloqueadas personalizadas](set-up-a-custom-blocked-urls-list-wtih-atp.md), por ejemplo, que cuando haga clic en personas en web direcciones (URL) en mensajes de correo electrónico o de determinados documentos de Office, se impide que se va a esas direcciones. La organización también puede tener listas personalizadas "no reescritura" para grupos específicos de la organización. Una lista "no reescritura" permite algunas personas visitar las direcciones URL que en caso contrario, están bloqueadas por [ATP vínculos seguros en Office 365](atp-safe-links.md). 
  
En este artículo se describe cómo especificar una lista de direcciones URL que se excluyen de examen de vínculos seguros de ATP y algunos puntos importantes que deben tenerse en cuenta.

## <a name="set-up-a-do-not-rewrite-list"></a>Configurar una lista "no reescritura de"

Protección de vínculos seguros de ATP utiliza varias listas, incluida la lista de direcciones URL bloqueadas de la organización y las listas de "no volver a escribir" para las excepciones. Si tiene los permisos necesarios, puede configurar las listas personalizadas "no reescritura de". Para ello, al agregar o editar las directivas de seguros vínculos que se aplican a determinados destinatarios en la organización. 
  
1. Vaya a [https://protection.office.com](https://protection.office.com) y el inicio de sesión con la cuenta de trabajo o escuela. 
    
2. En la izquierda, en **administración de amenaza** \> **Directiva** \> **Vínculos seguros**.
    
3. En la sección de **directivas que se aplican a determinados destinatarios** , elija **nuevo** (el botón nuevo se parece a un signo más ( **+**)) para crear una nueva directiva. (Como alternativa, puede editar una directiva existente).
    
    ![Elija nuevo para agregar una directiva de vínculos seguros para los destinatarios de correo electrónico específica](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
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
   
  

## <a name="related-topics"></a>Temas relacionados

[Protección contra amenazas avanzada de Office 365](office-365-atp.md)
  
[Vínculos de ATP seguros en Office 365](atp-safe-links.md)
  
[Configurar directivas de vínculos seguros de ATP en Office 365](set-up-atp-safe-links-policies.md)
  
[Configurar una lista de direcciones URL bloqueada personalizada con vínculos seguros de ATP](set-up-a-custom-blocked-urls-list-wtih-atp.md)

[Visualización de informes para la protección de amenaza avanzada de Office 365](view-reports-for-atp.md)

[Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md)
  


---
title: Configurar una lista personalizada de direcciones URL bloqueada mediante Office 365 ATP seguros vínculos
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
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
description: Lea este artículo para obtener información sobre cómo configurar una lista de direcciones URL bloqueadas para su organización mediante la protección de amenaza avanzada de Office 365. Las direcciones URL bloqueadas se aplicarán a los mensajes de correo electrónico y documentos de Office según las directivas de vínculos seguros de ATP.
ms.openlocfilehash: 0429546e521bf3f6b7144342ab0997e924c2f616
ms.sourcegitcommit: 099bbfb1d16b251fd5cf18ec6515faaf9a989176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25454367"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a>Configurar una lista personalizada de direcciones URL bloqueada mediante Office 365 ATP seguros vínculos

Con [Office 365 avanzada una protección contra amenazas](office-365-atp.md) (ATP), la organización puede tener una lista personalizada de direcciones de sitios Web (URL) que están bloqueados. Cuando se bloquea una dirección URL, se toman las personas que haga clic en vínculos a la dirección URL bloqueada a una [página de advertencia](atp-safe-links-warning-pages.md) que es similar a la siguiente imagen: 
  
![Este sitio está bloqueado](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
Se define la lista de direcciones URL bloqueadas por el equipo de seguridad de Office 365 de su organización, y esa lista se aplica a todas las personas de la organización que está cubierta por las directivas de Office 365 ATP seguros vínculos. 
  
Lea este artículo para obtener información sobre cómo configurar la lista de direcciones URL personalizada bloqueada de su organización para [ATP vínculos seguros en Office 365](atp-safe-links.md).
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>Ver o editar una lista personalizada de direcciones URL bloqueadas

[ATP vínculos seguros en Office 365](atp-safe-links.md) usa varias listas, incluida la lista de direcciones URL personalizada bloqueada de su organización. Si tiene los permisos necesarios, puede configurar la lista personalizada de su organización. Para ello, mediante la edición de la directiva de su organización predeterminada vínculos seguros.
  
1. Vaya a [https://protection.office.com](https://protection.office.com) y el inicio de sesión con la cuenta de trabajo o escuela. 
    
2. En la izquierda, en **administración de amenaza**, elija **Directiva** \> **Vínculos seguros**.
    
3. En la sección de **directivas que se aplican a toda la organización** , seleccione **predeterminado**y, a continuación, elija **Editar** (el botón Editar se parece a un lápiz). 
    
    ![Haga clic en Editar para editar la directiva predeterminada para la protección de vínculos seguros](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
    Esto es donde vaya a ver la lista de direcciones URL bloqueadas. Tenga en cuenta que, en primer lugar, no tendrá ningún direcciones URL que aparecen.
    
    ![La lista de direcciones URL bloqueado está en el valor predeterminado directiva vínculos seguros que se aplica a toda la organización.](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. Seleccione el cuadro **Escriba una dirección URL válida** y, a continuación, escriba una dirección URL y, a continuación, elija el signo más (+). A continuación presentamos algunas cosas que debe tener en cuenta: 
    
  - Puede especificar una dirección URL de dominio (como `contoso.com` o `tailspintoys.com`). Esto bloqueará clics en cualquier dirección URL que contiene el dominio.
    
  - No incluya una barra diagonal ( **/**) al final de la dirección URL. Por ejemplo, en lugar de escribir `http://www.contoso.com/`, escriba `http://www.contoso.com`.
    
  - Puede incluir hasta tres asteriscos comodín (\*) por la dirección URL. La siguiente tabla se enumeran algunos ejemplos de lo que puede escribir y el efecto que esas entradas tienen.
    
|**Entrada de ejemplo**|**Para qué sirve**|
|:-----|:-----|
|`contoso.com`o`*contoso.com*`  <br/> |Bloquea el dominio, subdominios y rutas de acceso, como `https://www.contoso.com`, `http://sub.contoso.com`, y`http://contoso.com/abc`  <br/> |
|`http://contoso.com/a`  <br/> |Bloquea un sitio `http://contoso.com/a` pero subtrazados no adicionales, como`http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a*`  <br/> |Bloquea un sitio `http://contoso.com/a` y subtrazados adicionales, como`http://contoso.com/a/b`  <br/> |
   
5. Cuando haya terminado de agregar las direcciones URL, en la esquina inferior derecha de la pantalla, elija **Guardar**.
    
## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a>Procedimiento para definir excepciones para determinados usuarios en una organización

Si desea que ciertos grupos puedan ver las direcciones URL que podrían estar bloqueadas para que otros usuarios, puede especificar una directiva de vínculos seguros de ATP que se aplica a determinados destinatarios. Consulte [Configurar una "no reescritura" las direcciones URL de lista personalizada con vínculos seguros de ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
  
## <a name="related-topics"></a>Temas relacionados

[Protección contra amenazas avanzada de Office 365](office-365-atp.md)
  
[Vínculos de ATP seguros en Office 365](atp-safe-links.md)
  
[Configurar directivas de vínculos seguros de ATP en Office 365](set-up-atp-safe-links-policies.md)
  
[Datos adjuntos seguros de ATP en Office 365](atp-safe-attachments.md)

[Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md)
  


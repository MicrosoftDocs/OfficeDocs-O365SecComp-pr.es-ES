---
title: Introducción a las recomendaciones de la directiva DLP
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 8/7/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
description: Esta recomendación basada en la información ayuda a su organización a mantener la seguridad del contenido confidencial cuando se almacena y se comparte en Office 365, ya que le informa cuando hay una brecha posible en la cobertura de la Directiva DLP. Verá esta recomendación en la Página principal del centro de seguridad &amp; y cumplimiento, si los documentos contienen alguno de los cinco tipos más comunes de información confidencial, pero no están protegidos por una directiva DLP.
ms.openlocfilehash: 6edb6a28182cb72e66a649ac5eb0c1561c596091
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2019
ms.locfileid: "30638887"
---
# <a name="get-started-with-dlp-policy-recommendations"></a>Introducción a las recomendaciones de la directiva DLP

Esta recomendación basada en la información ayuda a su organización a mantener la seguridad del contenido confidencial cuando se almacena y se comparte en Office 365, ya que le informa cuando hay una brecha posible en la cobertura de la Directiva DLP. Verá esta recomendación en la página **principal** del centro de seguridad &amp; y cumplimiento, si los documentos contienen alguno de los cinco tipos más comunes de información confidencial, pero no están protegidos por una directiva de prevención de pérdida de datos (DLP). 
  
Puede usar este widget para crear rápidamente una directiva de DLP personalizada en tan solo un clic o dos y después de crear esta directiva de DLP, es totalmente personalizable. Tenga en cuenta que si no ve la recomendación en primer lugar, intente hacer clic en **+ más** en la parte inferior de la sección **recomendada para usted** . 
  
![Widget denominado información confidencial desprotegida](media/91bc04d2-6eff-4294-8b73-b2d56d26ffc4.png)
  
## <a name="create-the-recommended-dlp-policy"></a>Crear la Directiva de DLP recomendada

Cuando el widget muestre información confidencial desprotegida, elija **empezar** en la parte inferior para crear rápidamente una directiva de DLP. 
  
Para ayudar a proteger la información confidencial, esta directiva de DLP:
  
- Detecta cuando el contenido de Exchange, SharePoint y OneDrive que contiene uno de los tipos de información confidencial no protegidos se comparte con personas de fuera de la organización.
    
- Genera informes de actividad detallados para que pueda realizar un seguimiento de cosas como quién ha compartido el contenido con personas de fuera de la organización y cuándo lo ha hecho. Puede usar los [informes de DLP](view-the-dlp-reports.md) y los datos del [registro de auditoría](search-the-audit-log-in-security-and-compliance.md) (donde**DLP**de **actividad** = ) para ver esta información.
    
También puede elegir que la Directiva DLP:
  
- Envíe un informe de correo electrónico de incidentes cuando los usuarios compartan gran parte de esta información confidencial con personas de fuera de la organización.
    
- Agregar otros usuarios al informe de incidentes de correo electrónico.
    
- Mostrar una sugerencia de directiva y enviar una notificación por correo electrónico a los usuarios cuando intenten compartir esta información confidencial con personas de fuera de la organización. Para obtener más información sobre estas opciones, vea [enviar notificaciones de correo electrónico y Mostrar sugerencias de directiva para directivas de DLP](use-notifications-and-policy-tips.md).
    
Si desea cambiar estas opciones más adelante, puede editar la Directiva DLP una vez creada. Por ejemplo, puede hacer que la Directiva sea más restrictiva impidiendo que los usuarios compartan contenido que contiene información confidencial en el primer lugar; consulte la siguiente sección.
  
![Configuración del widget denominado información confidencial desprotegida](media/b6106cbd-1bed-4582-aaef-b678de470c9b.png)
  
## <a name="edit-the-recommended-dlp-policy"></a>Edición de la Directiva de DLP recomendada

Después de usar el widget para crear una directiva de DLP, la directiva aparece en **prevención de pérdida de datos** en la página de la **Directiva** del centro de seguridad &amp; y cumplimiento. 
  
De forma predeterminada, la Directiva se denomina **Directiva recomendada del sistema para compartir información confidencial**. Esta directiva es totalmente personalizable, igual que cualquier directiva DLP que se cree a partir de cero. Por ejemplo, si decidió no activar los informes de incidentes y las sugerencias de directiva al usar el widget, siempre puede editar la Directiva y activar estas opciones en cualquier momento.
  
![Directiva recomendada por el sistema para compartir información confidencial](media/2fc49f25-ec25-4433-add4-d60f73888f13.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>Cuando el widget no aparece

El widget denominado **información confidencial no protegida** aparece en la sección **recomendada para usted** de la página **principal** del centro de seguridad &amp; y cumplimiento. 
  
Este widget solo aparece cuando:
  
- Los documentos nuevos que contienen los cinco tipos más comunes de información confidencial se detectan en SharePoint o en OneDrive en los últimos 30 días.
    
- La información confidencial todavía no está protegida por una directiva de DLP existente.
    
A diferencia de las directivas de DLP que continuamente examinan los datos, esta recomendación examina las brechas de la cobertura de la Directiva de DLP aproximadamente cada 48 horas, por lo que, una vez cargado el nuevo contenido, puede tardar hasta dos días en aparecer la recomendación.
  
Por último, después de usar el widget para crear una directiva de DLP recomendada, el widget desaparecerá de la página **principal** . 
  


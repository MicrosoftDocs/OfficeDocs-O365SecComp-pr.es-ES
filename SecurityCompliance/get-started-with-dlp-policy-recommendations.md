---
title: Introducción a las recomendaciones de la directiva DLP
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/7/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 2ea4459b-cb13-4ce2-b9d1-0619316df88c
description: Esta recomendación controlados por insight ayuda a su organización a mantener segura la contenido confidencial cuando se almacena y se comparten en Office 365 para informar cuando hay una posible brecha en la cobertura de la directiva DLP. Verá esta recomendación en la página principal de la seguridad &amp; centro de cumplimiento, si los documentos contienen cualquiera de los tipos más comunes de cinco de la parte superior de la información confidencial, pero no están protegidos por una directiva de DLP.
ms.openlocfilehash: fcd3a5a3a12932b22c310938c12f71fb01019411
ms.sourcegitcommit: ede6230c2df398dc0a633e8f32ee0bfede0d5142
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25002633"
---
# <a name="get-started-with-dlp-policy-recommendations"></a>Introducción a las recomendaciones de la directiva DLP

Esta recomendación controlados por insight ayuda a su organización a mantener segura la contenido confidencial cuando se almacena y se comparten en Office 365 para informar cuando hay una posible brecha en la cobertura de la directiva DLP. Verá esta recomendación en la página **principal** de la seguridad &amp; centro de cumplimiento, si los documentos contienen cualquiera de los tipos más comunes de cinco de la parte superior de la información confidencial, pero no están protegidos por una directiva de (DLP) de prevención de pérdida de datos. 
  
Puede usar este widget para crear rápidamente una directiva de DLP personalizada en un clic o dos y, después de crear esta directiva DLP, es totalmente personalizable. Tenga en cuenta que si no ve la recomendación en primer lugar, intente hacer clic en **+ más** en la parte inferior de la sección **recomendado para usted** . 
  
![Widget con nombre de información confidencial desprotegida](media/91bc04d2-6eff-4294-8b73-b2d56d26ffc4.png)
  
## <a name="create-the-recommended-dlp-policy"></a>Crear la directiva DLP recomendada

Cuando se muestra en el widget desprotegido información confidencial, elija **empezar a trabajar** en la parte inferior para crear rápidamente una directiva de DLP. 
  
Para ayudar a proteger la información confidencial, esta directiva DLP:
  
- Detecta cuando el contenido de Exchange, SharePoint y OneDrive que contiene uno de los tipos de información confidencial desprotegidos se comparte con personas fuera de la organización.
    
- Genera informes de actividad detallada de modo que puede realizar un seguimiento de cosas como el contenido que compartido con personas fuera de la organización y cuando lo hacían. Puede usar los [informes DLP](view-the-dlp-reports.md) y los [datos de registro de auditoría](search-the-audit-log-in-security-and-compliance.md) (donde **actividad** = **DLP**) para ver esta información.
    
También puede elegir que tengan la directiva DLP:
  
- Enviará un correo electrónico de informe del incidente cuando los usuarios compartir una gran cantidad de información confidencial con personas fuera de la organización.
    
- Agregar otros usuarios al informe de incidentes de correo electrónico.
    
- Mostrar una sugerencia de directiva y enviar una notificación de correo electrónico a los usuarios cuando intenten compartir esta información confidencial con personas fuera de la organización. Para obtener más información acerca de estas opciones, vea [Enviar notificaciones por correo electrónico y mostrar sugerencias de directivas para las directivas DLP](use-notifications-and-policy-tips.md).
    
Si desea cambiar estas opciones más adelante, puede editar la directiva DLP después de crearla. Por ejemplo, puede realizar la directiva más restrictiva por personas incluso bloqueo de uso compartido de contenido que contiene información confidencial en primer lugar - vea la siguiente sección.
  
![Configuración para el widget con nombre de información confidencial desprotegida](media/b6106cbd-1bed-4582-aaef-b678de470c9b.png)
  
## <a name="edit-the-recommended-dlp-policy"></a>Editar la directiva DLP recomendada

Después de usar el widget para crear una directiva de DLP, la directiva aparece bajo la **prevención de pérdida de datos** en la página **Directiva** de la seguridad &amp; centro de cumplimiento. 
  
De forma predeterminada, la directiva se denomina **Directiva del sistema se recomienda para el uso compartido de información confidencial**. Esta directiva es totalmente personalizable, igual que cualquier directiva DLP crear usted mismo desde el principio. Por ejemplo, si ha decidido no activar informes de incidentes y sugerencias de directiva cuando se utiliza el widget, siempre puede editar la directiva y activar estas opciones en cualquier momento.
  
![Sistema recomendado directiva para uso compartido de información confidencial](media/2fc49f25-ec25-4433-add4-d60f73888f13.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>Cuando el widget y no aparece

El widget con nombre de **Información confidencial desprotegida** aparece en la sección de **recomendado para usted** de la página **principal** de la seguridad &amp; centro de cumplimiento. 
  
Este widget aparece sólo cuando:
  
- Se detectan nuevos documentos que contengan cualquiera de los cinco tipos más comunes de información confidencial en SharePoint o OneDrive durante los últimos 30 días.
    
- Esa información confidencial ya no está protegida por una directiva DLP existente.
    
A diferencia de las directivas de DLP que constantemente se están analizando los datos, esta recomendación examina para los vacíos en la cobertura de la directiva DLP aproximadamente cada 48 horas, por lo que después de carga el nuevo contenido, puede tardar hasta dos días para la recomendación que aparezca.
  
Por último, después de usar el widget para crear una directiva DLP recomendada, el widget desaparece de la página **principal** . 
  


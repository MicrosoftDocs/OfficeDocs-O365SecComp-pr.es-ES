---
title: Introducción a la directiva predeterminada de DLP
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/10/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
description: Antes de crear la primera directiva de prevención (DLP) de pérdida de datos incluso, DLP es ayudar a proteger la información confidencial con una directiva predeterminada. Esta directiva predeterminada y su mantener de ayuda recomendación (que se muestra a continuación), el contenido confidencial seguro y se lo comunica al número de tarjeta de correo electrónico o documentos que contengan un crédito se comparte con alguien de fuera de la organización.
ms.openlocfilehash: 1b522a2c04e72353970ef5dfcd62183023a01994
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536859"
---
# <a name="get-started-with-the-default-dlp-policy"></a>Introducción a la directiva predeterminada de DLP

Antes de crear la primera directiva de prevención (DLP) de pérdida de datos incluso, DLP es ayudar a proteger la información confidencial con una directiva predeterminada. Esta directiva predeterminada y su mantener de ayuda recomendación (que se muestra a continuación), el contenido confidencial seguro y se lo comunica al número de tarjeta de correo electrónico o documentos que contengan un crédito se comparte con alguien de fuera de la organización. Verá esta recomendación en la página **principal** de la seguridad &amp; centro de cumplimiento. 
  
Puede usar este widget para ver rápidamente cuándo y la cantidad de información confidencial se ha compartido y, a continuación, refinar la directiva DLP predeterminada en un clic o un doble. También puede editar la directiva DLP predeterminado en cualquier momento porque es totalmente personalizable. Tenga en cuenta que si no ve la recomendación en primer lugar, intente hacer clic en **+ más** en la parte inferior de la sección **recomendado para usted** . 
  
![Widget denominado más proteger contenido compartido](media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a>Ver el informe y refinar la directiva DLP predeterminada

Cuando el widget muestra que los usuarios comparte información confidencial con personas fuera de la organización, seleccione **Directiva de DLP refinar** en la parte inferior. 
  
El informe detallado muestra cuándo y cómo se ha compartido la cantidad de contenido que contiene los números de tarjeta de crédito en los últimos 30 días. Tenga en cuenta que coincide con la regla puede tardar hasta 48 horas aparezca en el widget.
  
Para ayudar a proteger la información confidencial, la directiva DLP predeterminada:
  
- Detecta cuando el contenido de Exchange, SharePoint y OneDrive que contiene al menos una tarjeta de crédito se comparte con personas fuera de la organización.
    
- Muestra una sugerencia de directiva y envía una notificación de correo electrónico a los usuarios cuando intenten compartir esta información confidencial con personas fuera de la organización. Para obtener más información acerca de estas opciones, vea [Enviar notificaciones por correo electrónico y mostrar sugerencias de directivas para las directivas DLP](use-notifications-and-policy-tips.md).
    
- Genera informes de actividad detallada de modo que puede realizar un seguimiento de cosas como el contenido que compartido con personas fuera de la organización y cuando lo hacían. Puede usar los [informes DLP](view-the-dlp-reports.md) y los [datos de registro de auditoría](search-the-audit-log-in-security-and-compliance.md) (donde **actividad** = **DLP**) para ver esta información.
    
Para refinar rápidamente la directiva DLP de forma predeterminada, puede elegir para que:
  
- Enviará un correo electrónico de informe del incidente cuando los usuarios compartir esta información confidencial con personas fuera de la organización.
    
- Agregar otros usuarios al informe de incidentes de correo electrónico.
    
- Bloquee el acceso al contenido que contiene la información confidencial, pero permitir que el usuario invalidar y compartir o enviar si es necesario.
    
Para obtener más información sobre los informes de incidentes o restringir el acceso, vea [información general de las directivas de prevención de pérdida de datos](data-loss-prevention-policies.md).
  
Si desea cambiar estas opciones más adelante, puede editar el valor predeterminado directiva DLP en cualquier momento - vea la siguiente sección.
  
![Configuración de widget denominado más protege contenido compartido](media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a>Editar la directiva DLP predeterminada

Esta directiva se denomina **directiva predeterminada Office 365 DLP** y aparece bajo la **prevención de pérdida de datos** en la página **Directiva** de la seguridad &amp; centro de cumplimiento. 
  
Esta directiva es totalmente personalizable, igual que cualquier directiva DLP crear usted mismo desde el principio. También puede desactivar o eliminar la directiva, de modo que los usuarios ya no reciben sugerencias de directiva o notificaciones por correo electrónico.
  
![Directiva DLP denominada directiva predeterminada DLP de Office 365](media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>Cuando el widget y no aparece

El widget denominado **proteger más el contenido compartido** aparece en la sección de **recomendado para usted** de la página **principal** de la seguridad &amp; centro de cumplimiento. 
  
Este widget aparece sólo cuando:
  
- No hay ningún directivas de prevención de pérdida de datos en la seguridad &amp; centro de cumplimiento o centro de administración de Exchange. Este widget está pensada para ayudarle a empezar a trabajar con DLP, para que no aparezca si ya dispone de las directivas de DLP.
    
- Contenido que contenga menos una tarjeta de crédito se ha compartido con alguien de fuera de la organización en los últimos 30 días.
    
Tenga en cuenta que coincide con la regla puede tardar hasta 48 horas esté disponible para el widget, por lo que una vez que se detecta información confidencial shared externamente, puede tardar hasta dos días para la recomendación que aparezca.
  
Por último, después de usar el widget para refinar la directiva DLP de forma predeterminada, el widget desaparece de la página **principal** . 
  


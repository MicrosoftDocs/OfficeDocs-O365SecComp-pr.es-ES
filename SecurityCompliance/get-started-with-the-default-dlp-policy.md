---
title: Introducción a la directiva predeterminada de DLP
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/10/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
description: Antes de crear la primera Directiva de prevención de pérdida de datos (DLP), DLP ayuda a proteger la información confidencial con una directiva predeterminada. Esta directiva predeterminada y su recomendación (que se muestra a continuación) ayudan a mantener seguro el contenido confidencial mediante una notificación cuando el correo electrónico o los documentos que contienen un número de tarjeta de crédito se han compartido con alguien ajeno a la organización.
ms.openlocfilehash: 3182abcc825c8e27da83ebfb64ed8b2cba6ebcb3
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341321"
---
# <a name="get-started-with-the-default-dlp-policy"></a>Introducción a la directiva predeterminada de DLP

Antes de crear la primera Directiva de prevención de pérdida de datos (DLP), DLP ayuda a proteger la información confidencial con una directiva predeterminada. Esta directiva predeterminada y su recomendación (que se muestra a continuación) ayudan a mantener seguro el contenido confidencial mediante una notificación cuando el correo electrónico o los documentos que contienen un número de tarjeta de crédito se han compartido con alguien ajeno a la organización. Verá esta recomendación en la página **principal** del centro de seguridad &amp; y cumplimiento. 
  
Puede usar este widget para ver rápidamente cuándo y cuánto se ha compartido la información confidencial y, a continuación, refinar la Directiva de DLP predeterminada en solo un clic o dos. También puede editar la Directiva DLP predeterminada en cualquier momento, ya que es totalmente personalizable. Tenga en cuenta que si no ve la recomendación en primer lugar, intente hacer clic en **+ más** en la parte inferior de la sección **recomendada para usted** . 
  
![Widget denominado protección de contenido compartido adicional](media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a>Ver el informe y refinar la Directiva de DLP predeterminada

Cuando el widget muestre que los usuarios comparten información confidencial con personas de fuera de la organización, elija refinar la **Directiva DLP** en la parte inferior. 
  
El informe detallado muestra Cuándo y cuánto contenido que contiene los números de las tarjetas de crédito se ha compartido en los últimos 30 días. Tenga en cuenta que las coincidencias de regla pueden tardar hasta 48 horas en mostrarse en el widget.
  
Para ayudar a proteger la información confidencial, la Directiva de DLP predeterminada:
  
- Detecta si el contenido de Exchange, SharePoint y OneDrive que contiene al menos un número de tarjeta de crédito se comparte con personas de fuera de la organización.
    
- Muestra una sugerencia de directiva y envía una notificación por correo electrónico a los usuarios cuando intentan compartir esta información confidencial con personas de fuera de la organización. Para obtener más información sobre estas opciones, vea [enviar notificaciones de correo electrónico y Mostrar sugerencias de directiva para directivas de DLP](use-notifications-and-policy-tips.md).
    
- Genera informes de actividad detallados para que pueda realizar un seguimiento de cosas como quién ha compartido el contenido con personas de fuera de la organización y cuándo lo ha hecho. Puede usar los [informes de DLP](view-the-dlp-reports.md) y los datos del [registro de auditoría](search-the-audit-log-in-security-and-compliance.md) (donde**DLP**de **actividad** = ) para ver esta información.
    
Para refinar rápidamente la Directiva DLP predeterminada, puede elegir que:
  
- Envíe un informe de correo electrónico de incidentes cuando los usuarios compartan esta información confidencial con personas de fuera de la organización.
    
- Agregar otros usuarios al informe de incidentes de correo electrónico.
    
- Bloquee el acceso al contenido que contiene la información confidencial, pero permita al usuario reemplazar y compartir o enviar si es necesario.
    
Para obtener más información sobre los informes de incidentes o restringir el acceso, consulte [información general sobre las directivas de prevención de pérdida de datos](data-loss-prevention-policies.md).
  
Si desea cambiar estas opciones más adelante, puede editar la Directiva DLP predeterminada en cualquier momento (consulte la sección siguiente).
  
![Configuración del widget con el nombre protección de contenido compartido adicional](media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a>Edición de la Directiva de DLP predeterminada

Esta Directiva se denomina **Directiva DLP predeterminada de Office 365** y aparece en **prevención de pérdida de datos** en la página de la **Directiva** del centro de seguridad &amp; y cumplimiento. 
  
Esta directiva es totalmente personalizable, igual que cualquier directiva DLP que se cree a partir de cero. También puede desactivar o eliminar la Directiva para que los usuarios dejen de recibir sugerencias de directiva o notificaciones de correo electrónico.
  
![Directiva DLP denominada Directiva DLP predeterminada de Office 365](media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>Cuando el widget no aparece

El widget denominado **protección de contenido compartido adicional** aparece en la sección **recomendada para usted** de la página **principal** del centro &amp; de seguridad y cumplimiento. 
  
Este widget solo aparece cuando:
  
- No hay directivas de prevención de pérdida de datos en &amp; el centro de seguridad y cumplimiento o en el centro de administración de Exchange. Este widget está pensado para ayudarle a empezar a usar DLP, por lo que no aparece si ya tiene directivas de DLP.
    
- En los últimos 30 días se ha compartido el contenido que contiene menos una tarjeta de crédito con alguien ajeno a su organización.
    
Tenga en cuenta que las coincidencias de regla pueden tardar hasta 48 horas en estar disponibles para el widget, por lo que, una vez detectada la información confidencial compartida de forma externa, puede tardar hasta dos días en aparecer la recomendación.
  
Por último, después de usar el widget para refinar la Directiva de DLP predeterminada, el widget desaparecerá de la página **principal** . 
  


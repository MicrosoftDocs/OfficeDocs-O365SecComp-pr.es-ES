---
title: Cómo funciona DLP entre el centro &amp; de seguridad y cumplimiento y el centro de administración de Exchange
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/4/2017
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Obtenga información sobre cómo DLP en &amp; el centro de seguridad y cumplimiento funciona con las reglas de transporte y DLP en el centro de administración de Exchange.
ms.openlocfilehash: 531a45308594d03dc219f50d989a08236b8b5e20
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215650"
---
# <a name="how-dlp-works-between-the-security-amp-compliance-center-and-exchange-admin-center"></a>Cómo funciona DLP entre el centro &amp; de seguridad y cumplimiento y el centro de administración de Exchange

En Office 365, puede crear una directiva de prevención de pérdida de datos (DLP) en dos centros de administración diferentes:
  
- En el **Centro &amp; de seguridad y cumplimiento**, puede crear una única directiva DLP para ayudar a proteger el contenido de SharePoint, OneDrive y Exchange. Siempre que sea posible, se recomienda crear una directiva de DLP aquí. Para obtener más información, consulte [DLP en el &amp; centro de seguridad y cumplimiento](data-loss-prevention-policies.md).
    
- En el **centro de administración de Exchange**, puede crear una directiva DLP para ayudar a proteger el contenido solo en Exchange. Esta Directiva puede usar reglas de transporte de Exchange, por lo que tiene más opciones específicas para administrar el correo electrónico. Para obtener más información, consulte [DLP en el centro de administración de Exchange](https://go.microsoft.com/fwlink/?linkid=852311).
    
Las directivas de DLP creadas en estos centros de administración trabajan en paralelo: en este tema se explica cómo hacerlo.
  
![Páginas de DLP en el centro de seguridad y cumplimiento y el centro de administración de Exchange](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security-amp-compliance-center-works-with-dlp-and-transport-rules-in-the-exchange-admin-center"></a>Cómo trabaja DLP en el &amp; centro de seguridad y cumplimiento con las reglas de transporte y DLP en el centro de administración de Exchange

Después de crear una directiva DLP en el centro &amp; de seguridad y cumplimiento, la Directiva se implementa en todas las ubicaciones incluidas en la Directiva. Si la Directiva incluye Exchange Online, la Directiva se sincroniza y se aplica exactamente de la misma manera que una directiva de DLP creada en el centro de administración de Exchange. 
  
Si ha creado directivas de DLP en el centro de administración de Exchange, estas directivas seguirán funcionando en paralelo con las directivas de correo electrónico que cree en el centro &amp; de seguridad y cumplimiento. Pero tenga en cuenta que las reglas creadas en el centro de administración de Exchange tienen prioridad. Todas las reglas de transporte de Exchange se procesan en primer lugar y, a &amp; continuación, se procesan las reglas de DLP del centro de seguridad y cumplimiento.
  
Esto significa que:
  
- Las reglas de DLP creadas en el centro de seguridad &amp; y cumplimiento no examinarán los mensajes bloqueados por las reglas de transporte de Exchange.
    
- Si una regla de transporte de Exchange modifica un mensaje de tal forma que hace coincidir una directiva DLP en el centro &amp; de seguridad y cumplimiento (por ejemplo, agregar usuarios externos), las reglas de DLP lo detectarán y aplicarán la Directiva según sea necesario.
    
Además, tenga en cuenta que las reglas de transporte de Exchange que usan la acción "detener el procesamiento" no afectan al &amp; procesamiento de reglas de DLP en el centro de seguridad y cumplimiento, se procesarán igualmente.
  
## <a name="policy-tips-in-the-security-amp-compliance-center-vs-the-exchange-admin-center"></a>Sugerencias de directiva en el &amp; centro de seguridad y cumplimiento frente al centro de administración de Exchange

Las sugerencias de Directiva pueden funcionar con las directivas de DLP y las reglas de flujo de correo creadas en el centro de administración de Exchange, &amp; o con las directivas de DLP creadas en el centro de seguridad y cumplimiento, pero no ambas. Esto se debe a que estas directivas se almacenan en ubicaciones distintas, pero las sugerencias de directiva solo pueden dibujar desde una única ubicación.
  
Si ha configurado sugerencias de directiva en el centro de administración de Exchange, las sugerencias de directiva que configure &amp; en el centro de seguridad y cumplimiento no se mostrarán a los usuarios en Outlook en la web y Outlook 2013 y versiones posteriores hasta que desactive las sugerencias en el centro de administración de Exchange. Esto garantiza que las reglas de transporte de Exchange actuales seguirán funcionando hasta que elija cambiar al centro de seguridad &amp; y cumplimiento.
  
Tenga en cuenta que, aunque las sugerencias de directiva solo pueden dibujar desde una única ubicación, siempre se envían notificaciones de correo electrónico, incluso si está usando &amp; directivas de DLP tanto en el centro de administración de seguridad como en el centro de administración de Exchange.
  


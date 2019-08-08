---
title: Funcionamiento de DLP entre el Centro de seguridad y cumplimiento y el Centro de administración de Exchange
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/19/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Obtenga información sobre cómo DLP en el centro de seguridad & cumplimiento funciona con DLP y reglas de flujo de correo (reglas de transporte) en el centro de administración de Exchange.
ms.openlocfilehash: 65df871361eca66dca543cd2a6dcb0a529446169
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230624"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a>Funcionamiento de DLP entre el Centro de seguridad y cumplimiento y el Centro de administración de Exchange

En Office 365, puede crear una directiva de prevención de pérdida de datos (DLP) en dos centros de administración diferentes:
  
- En el **centro de seguridad & cumplimiento**, puede crear una única directiva DLP para ayudar a proteger el contenido de SharePoint, OneDrive, Exchange y ahora Microsoft Teams. Siempre que sea posible, se recomienda crear una directiva de DLP aquí. Para obtener más información, consulte [DLP en el centro de seguridad & cumplimiento](data-loss-prevention-policies.md).
    
- En el **centro de administración de Exchange**, puede crear una directiva DLP para ayudar a proteger el contenido solo en Exchange. Esta Directiva puede usar reglas de flujo de correo de Exchange (también conocidas como reglas de transporte), por lo que tiene más opciones específicas para administrar el correo electrónico. Para obtener más información, consulte [DLP en el centro de administración de Exchange](https://go.microsoft.com/fwlink/?linkid=852311).
    
Las directivas de DLP creadas en estos centros de administración trabajan en paralelo: en este tema se explica cómo hacerlo.
  
![Páginas de DLP en el centro de seguridad y cumplimiento y el centro de administración de Exchange](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>Cómo trabaja DLP en el centro de cumplimiento de & de seguridad con DLP y reglas de flujo de correo en el centro de administración de Exchange

Después de crear una directiva DLP en el centro de seguridad & cumplimiento, la Directiva se implementa en todas las ubicaciones incluidas en la Directiva. Si la Directiva incluye Exchange Online, la Directiva se sincroniza y se aplica exactamente de la misma manera que una directiva de DLP creada en el centro de administración de Exchange. 
  
Si ha creado directivas DLP en el centro de administración de Exchange, estas directivas seguirán funcionando en paralelo con las directivas de correo electrónico que cree en el centro de seguridad & cumplimiento. Pero tenga en cuenta que las reglas creadas en el centro de administración de Exchange tienen prioridad. Todas las reglas de flujo de correo de Exchange se procesan en primer lugar y, a continuación, se procesan las reglas de DLP del centro de seguridad & cumplimiento.
  
Esto significa que:
  
- Las reglas de DLP creadas en el centro de seguridad & cumplimiento no examinarán los mensajes bloqueados por las reglas de flujo de correo de Exchange.
    
- Si una regla de flujo de correo de Exchange modifica un mensaje de forma que hace coincidir una directiva DLP en el centro de seguridad & cumplimiento del sistema, como agregar usuarios externos, las reglas de DLP lo detectarán y aplicarán la Directiva según sea necesario.
    
Además, tenga en cuenta que las reglas de flujo de correo de Exchange que usan la acción "detener el procesamiento" no afectan al procesamiento de reglas DLP en el centro de seguridad & cumplimiento, se procesarán todavía.
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>Sugerencias de directiva en el centro de seguridad & cumplimiento frente al centro de administración de Exchange

Las sugerencias de Directiva pueden funcionar con las directivas DLP y las reglas de flujo de correo creadas en el centro de administración de Exchange o con las directivas de DLP creadas en el centro de seguridad & cumplimiento, pero no ambas. Esto se debe a que estas directivas se almacenan en ubicaciones distintas, pero las sugerencias de directiva solo pueden dibujar desde una única ubicación.
  
Si ha configurado sugerencias de directiva en el centro de administración de Exchange, las sugerencias de directiva que configure en el centro de seguridad & cumplimiento no aparecerán para los usuarios de Outlook en la web y Outlook 2013 y versiones posteriores hasta que desactive las sugerencias en el centro de administración de Exchange. Esto garantiza que las reglas actuales de flujo de correo de Exchange seguirán funcionando hasta que decida cambiar al centro de seguridad & cumplimiento.
  
Tenga en cuenta que, aunque las sugerencias de directiva solo pueden dibujar desde una única ubicación, siempre se envían notificaciones de correo electrónico, incluso si está usando directivas de DLP tanto en el centro de seguridad & cumplimiento como en el centro de administración de Exchange.
  


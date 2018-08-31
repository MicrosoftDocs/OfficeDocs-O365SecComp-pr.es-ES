---
title: Cómo funciona la DLP entre la seguridad &amp; centro de cumplimiento y el centro de administración de Exchange
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/4/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Obtenga información sobre cómo DLP en la seguridad &amp; centro de cumplimiento funciona con DLP y reglas de transporte en el centro de administración de Exchange.
ms.openlocfilehash: bc7494f504c2c0ffa668562d6e64b9f29992e24f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536473"
---
# <a name="how-dlp-works-between-the-security-amp-compliance-center-and-exchange-admin-center"></a>Cómo funciona la DLP entre la seguridad &amp; centro de cumplimiento y el centro de administración de Exchange

En Office 365, puede crear una directiva de (DLP) de prevención de pérdida de datos en dos centros de administración diferentes:
  
- En la **seguridad &amp; centro de cumplimiento**, puede crear una sola directiva DLP para ayudar a proteger el contenido de SharePoint, OneDrive y Exchange. Cuando sea posible, se recomienda que cree una directiva de DLP aquí. Para obtener más información, vea [DLP en la seguridad &amp; centro de cumplimiento](data-loss-prevention-policies.md).
    
- En el **Centro de administración de Exchange**, puede crear una directiva DLP para ayudar a proteger el contenido sólo en Exchange. Esta directiva puede usar las reglas de transporte de Exchange, por lo que tiene más opciones específicas a la gestión de correo electrónico. Para obtener más información, vea [DLP en el centro de administración de Exchange](https://go.microsoft.com/fwlink/?linkid=852311).
    
Las directivas de DLP creado en estos admin centros de trabajan en paralelo - en este tema se explica cómo.
  
![Páginas DLP en seguridad y el centro de cumplimiento y el centro de administración de Exchange](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security-amp-compliance-center-works-with-dlp-and-transport-rules-in-the-exchange-admin-center"></a>¿Cómo DLP en la seguridad &amp; centro de cumplimiento funciona con DLP y reglas de transporte en el centro de administración de Exchange

Después de crear una directiva de DLP en la seguridad &amp; centro de cumplimiento, la directiva se implementa en todas las ubicaciones que se incluyen en la directiva. Si la directiva incluye Exchange Online, la directiva sincronizado existe y se aplica en exactamente de la misma manera que una directiva de DLP creada en el centro de administración de Exchange. 
  
Si ya ha creado las directivas de DLP en el centro de administración de Exchange, esas directivas seguirán funcionando codo con codo con las directivas de correo electrónico que se crea en la seguridad &amp; centro de cumplimiento. Pero tenga en cuenta que las reglas creadas en el centro de administración de Exchange tiene prioridad. Todas las reglas de transporte de Exchange se procesan en primer lugar y, a continuación, reglas de DLP desde la seguridad &amp; se procesan centro de cumplimiento.
  
Esto significa:
  
- Los mensajes que están bloqueados por las reglas de transporte de Exchange no obtener examinados por las reglas DLP creadas en la seguridad &amp; centro de cumplimiento.
    
- Si una regla de transporte de Exchange modifica un mensaje de una manera que hace que coinciden con una directiva de DLP en la seguridad &amp; centro de cumplimiento - como la adición de usuarios externos -, a continuación, las reglas DLP detectará esto y aplicar la directiva según sea necesario.
    
También tenga en cuenta que las reglas de transporte de Exchange que use la acción "detener el procesamiento de" no influyen en el procesamiento de DLP de reglas en la seguridad &amp; centro de cumplimiento - éstas se procesarán aún.
  
## <a name="policy-tips-in-the-security-amp-compliance-center-vs-the-exchange-admin-center"></a>Sugerencias de directiva en la seguridad &amp; centro de cumplimiento de normas frente el centro de administración de Exchange

Sugerencias de directiva pueden trabajar con directivas de DLP y creadas en el centro de administración de Exchange, o con las directivas DLP creadas en la seguridad de las reglas de flujo de correo &amp; centro de cumplimiento, pero no ambos. Esto es debido a que estas directivas se almacenan en distintas ubicaciones, pero pueden dibujar sugerencias de directiva sólo desde una única ubicación.
  
Si ha configurado sugerencias de directivas en el centro de administración de Exchange, las sugerencias de directiva que configurar en la seguridad &amp; centro de cumplimiento no se mostrará a los usuarios de Outlook en la web y Outlook 2013 y versiones posteriores hasta que desactivar las sugerencias en el centro de administración de Exchange. Esto garantiza que las reglas de transporte de Exchange actuales continuará funcionando hasta que se elija Cambiar a la seguridad &amp; centro de cumplimiento.
  
Tenga en cuenta que las notificaciones de correo electrónico mientras sugerencias de directiva pueden dibujar sólo desde una única ubicación, siempre se envían, incluso si está usando las directivas de DLP en tanto la seguridad &amp; centro de cumplimiento y el centro de administración de Exchange.
  


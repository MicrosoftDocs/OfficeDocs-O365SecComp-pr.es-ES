---
title: Configurar las directivas contra correo electrónico no deseado
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/9/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 31279431-828d-48bd-b979-20b6de15fa4a
description: El filtrado de correo no deseado se habilita automáticamente en toda la compañía con las directivas de correo no deseado predeterminadas (filtro de conexión, filtro de correo no deseado y correo no deseado saliente). Como administrador, puede ver y editar, y no eliminar, las directivas contra correo no deseado predeterminadas para que se adapten mejor a las necesidades de la organización. Para mayor granularidad, también puede crear directivas de filtro de correo no deseado personalizadas y aplicarlas a determinados usuarios, grupos o dominios de la organización. De manera predeterminada, las directivas personalizadas tienen prioridad sobre las directivas predeterminadas, pero esta prioridad se puede cambiar.
ms.openlocfilehash: c1bec3c7e8db3222f25a423ac94068d537529cac
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002356"
---
# <a name="configure-the-anti-spam-policies"></a>Configurar las directivas contra correo electrónico no deseado

El filtrado de correo no deseado se habilita automáticamente en toda la compañía con las directivas de correo no deseado predeterminadas (filtro de conexión, filtro de correo no deseado y correo no deseado saliente). Como administrador, puede ver y editar, y no eliminar, las directivas contra correo no deseado predeterminadas para que se adapten mejor a las necesidades de la organización. Para mayor granularidad, también puede crear directivas de filtro de correo no deseado personalizadas y aplicarlas a determinados usuarios, grupos o dominios de la organización. De manera predeterminada, las directivas personalizadas tienen prioridad sobre las directivas predeterminadas, pero esta prioridad se puede cambiar. 
  
Para obtener más información acerca de la configuración de políticas contra correo no deseado, consulte los temas siguientes:
  
[Configurar la directiva de filtro de conexión](configure-the-connection-filter-policy.md)
  
[Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> Para clientes independientes de EOP: De manera predeterminada, los filtros de contenido de EOP envían mensajes detectados como correo no deseado a la carpeta Correo electrónico no deseado del destinatario. Sin embargo, a fin de garantizar que la acción **Mover mensaje a la carpeta Correo electrónico no deseado** va a funcionar en los buzones locales, debe configurar dos reglas de transporte de Exchange en los servidores locales para detectar los encabezados de correo no deseado agregados mediante EOP. Para más información, consulte [Asegurarse de que el correo no deseado se enruta a la carpeta de correo no deseado de cada usuario](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). 
  
[Configurar la directiva de correo no deseado saliente](configure-the-outbound-spam-policy.md)
  


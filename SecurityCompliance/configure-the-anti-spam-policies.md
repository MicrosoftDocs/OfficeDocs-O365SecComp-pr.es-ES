---
title: Configurar las directivas contra correo electrónico no deseado
ms.author: tracyp
author: MSFTTracyP
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
ms.collection:
- M365-security-compliance
description: El filtrado de correo no deseado se habilita automáticamente en toda la compañía con las directivas de correo no deseado predeterminadas (filtro de conexión, filtro de correo no deseado y correo no deseado saliente). Como administrador, puede ver y editar, y no eliminar, las directivas contra correo no deseado predeterminadas para que se adapten mejor a las necesidades de la organización. Para mayor granularidad, también puede crear directivas de filtro de correo no deseado personalizadas y aplicarlas a determinados usuarios, grupos o dominios de la organización. De manera predeterminada, las directivas personalizadas tienen prioridad sobre las directivas predeterminadas, pero esta prioridad se puede cambiar.
ms.openlocfilehash: 3e972a150b70f1081cb4c3b5e3672a3acba34785
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "30340971"
---
# <a name="configure-the-anti-spam-policies"></a>Configurar las directivas contra correo electrónico no deseado

El filtrado de correo no deseado se habilita automáticamente en toda la compañía con las directivas de correo no deseado predeterminadas (filtro de conexión, filtro de correo no deseado y correo no deseado saliente). Como administrador, puede ver y editar, y no eliminar, las directivas contra correo no deseado predeterminadas para que se adapten mejor a las necesidades de la organización. Para mayor granularidad, también puede crear directivas de filtro de correo no deseado personalizadas y aplicarlas a determinados usuarios, grupos o dominios de la organización. De manera predeterminada, las directivas personalizadas tienen prioridad sobre las directivas predeterminadas, pero esta prioridad se puede cambiar. 
  
Para obtener más información acerca de la configuración de políticas contra correo no deseado, consulte los temas siguientes:
  
[Configurar la directiva de filtro de conexión](configure-the-connection-filter-policy.md)
  
[Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> Para clientes independientes de EOP: de manera predeterminada, los filtros de contenido de EOP envían mensajes detectados como correo no deseado a la carpeta de correo electrónico no deseado de cada destinatario. Sin embargo, para asegurarse de que la acción **mover el mensaje a la carpeta correo no deseado** funcionará con los buzones locales, debe configurar dos reglas de flujo de correo de Exchange (también conocidas como reglas de transporte) en los servidores locales para detectar los encabezados de correo no deseado agregados por EOP. Para obtener más información, consulte [asegurarse de que el correo no deseado se enruta a la carpeta de correo no deseado de cada usuario](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). 
  
[Configurar la directiva de correo no deseado saliente](configure-the-outbound-spam-policy.md)
  


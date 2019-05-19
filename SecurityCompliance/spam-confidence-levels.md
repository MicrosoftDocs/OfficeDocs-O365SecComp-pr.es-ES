---
title: Niveles de confianza de correo no deseado
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/2/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: A cada mensaje de correo electrónico que pasa por el filtrado de correo no deseado se le asigna una puntuación de correo no deseado. La puntuación se asigna a una clasificación de nivel de confianza contra correo no deseado (SCL) individual y se marca en un encabezado X. El servicio realiza acciones en los mensajes según la interpretación de la confianza contra correo no deseado de las clasificaciones de SCL. La tabla siguiente muestra cómo las distintas clasificaciones de SCL se interpretan en los filtros y la acción predeterminada que se realiza en los mensajes entrantes por cada clasificación.
ms.openlocfilehash: 4eba1dc6fa1bbadcfd135a7bf43e7353755df6c4
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158272"
---
# <a name="spam-confidence-levels"></a>Niveles de confianza de correo no deseado

A cada mensaje de correo electrónico que pasa por el filtrado de correo no deseado se le asigna una puntuación de correo no deseado. La puntuación se asigna a una clasificación de nivel de confianza contra correo no deseado (SCL) individual y se marca en un encabezado X. El servicio realiza acciones en los mensajes según la interpretación de la confianza contra correo no deseado de las clasificaciones de SCL. La tabla siguiente muestra cómo las distintas clasificaciones de SCL se interpretan en los filtros y la acción predeterminada que se realiza en los mensajes entrantes por cada clasificación.
  
|**Clasificación de SCL**|**Interpretación de confianza de correo no deseado**|**Acción predeterminada**|
|:-----|:-----|:-----|
|-1|Correo no deseado procedente de un remitente seguro, un destinatario seguro o una dirección IP de lista segura (asociado de confianza).|Se entrega el mensaje a la bandeja de entrada de los destinatarios.|
|0, 1|Correo electrónico no deseado porque el mensaje se examinó y se determinó como limpio.|Se entrega el mensaje a la bandeja de entrada de los destinatarios.|
|5, 6|Correo no deseado|El mensaje se entrega a la carpeta de Correo no deseado de los destinatarios.|
|7, 8, 9|Correo no deseado de alta confianza|El mensaje se entrega a la carpeta de Correo no deseado de los destinatarios.|
   
> [!TIP]
> El servicio no establece las clasificaciones de SCL de 2, 3, 4, 7 y 8. Una clasificación de SCL de 5 o 6 se considera sospecha de correo no deseado, que es menos probable que sea correo no deseado que una clasificación de SCL de 9, que indica con certeza que se trata de correo no deseado. Se pueden configurar diversas acciones para el correo no deseado y el correo no deseado de alta confianza en las directivas de filtro de contenido en el Centro de administración de Exchange. Para obtener más información, vea [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md). También puede establecer la clasificación SCL para los mensajes que coinciden con condiciones específicas usando reglas de flujo de correo (también conocidas como reglas de transporte), como se describe en [usar reglas de flujo de correo para establecer el nivel de confianza contra correo no deseado (SCL) en los mensajes](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md). Si usa una regla de flujo de correo para establecer SCL de 7, 8 o 9, el mensaje se considerará correo no deseado de confianza alta. 
  
||
|:-----|
|![El icono reducido de LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **¿Es la primera vez que usa Office 365?**         LinkedIn Learning pone a su disposición vídeos gratuitos de cursos de **Office 365 admins and IT pros**.|
   


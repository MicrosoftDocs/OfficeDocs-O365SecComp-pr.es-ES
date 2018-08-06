---
title: Niveles de confianza de correo no deseado
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
description: A cada mensaje de correo electrónico que pasa por el filtrado de correo no deseado se le asigna una puntuación de correo no deseado. La puntuación se asigna a una clasificación de nivel de confianza contra correo no deseado (SCL) individual y se marca en un encabezado X. El servicio realiza acciones en los mensajes según la interpretación de la confianza contra correo no deseado de las clasificaciones de SCL. La tabla siguiente muestra cómo las distintas clasificaciones de SCL se interpretan en los filtros y la acción predeterminada que se realiza en los mensajes entrantes por cada clasificación.
ms.openlocfilehash: cd33f440828761ab8cb496d9eff07288d974514c
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026287"
---
# <a name="spam-confidence-levels"></a>Niveles de confianza de correo no deseado

A cada mensaje de correo electrónico que pasa por el filtrado de correo no deseado se le asigna una puntuación de correo no deseado. La puntuación se asigna a una clasificación de nivel de confianza contra correo no deseado (SCL) individual y se marca en un encabezado X. El servicio realiza acciones en los mensajes según la interpretación de la confianza contra correo no deseado de las clasificaciones de SCL. La tabla siguiente muestra cómo las distintas clasificaciones de SCL se interpretan en los filtros y la acción predeterminada que se realiza en los mensajes entrantes por cada clasificación.
  
|**Clasificación de SCL**|**Interpretación de confianza de correo no deseado**|**Acción predeterminada**|
|:-----|:-----|:-----|
|-1  <br/> |Mensajes seguros provenientes de un remitente seguro, de un destinatario seguro o de una dirección IP permitida (socio de confianza)  <br/> |Se entrega el mensaje a la bandeja de entrada de los destinatarios.  <br/> |
|0, 1  <br/> |Mensaje seguro debido a que se examinó el mensaje y se determinó como limpio  <br/> |Se entrega el mensaje a la bandeja de entrada de los destinatarios.  <br/> |
|5, 6  <br/> | Correo no deseado  <br/> |El mensaje se entrega a la carpeta de Correo no deseado de los destinatarios.  <br/> |
|7, 8, 9  <br/> |Correo no deseado de alta confianza  <br/> |El mensaje se entrega a la carpeta de Correo no deseado de los destinatarios.  <br/> |
   
> [!TIP]
> Clasificaciones de SCL de 2, 3, 4, 7 y 8 no se establecen por el servicio. Una clasificación SCL de 5 o 6 se considera sospechoso de ser correo no deseado que es menos determinado ser correo no deseado que un SCL de 9, que se considera determinada spam. Diferentes acciones para correo no deseado y spam de alta confianza se pueden configurar a través de las directivas de filtro de contenido en el centro de administración de Exchange. Para obtener más información, vea [configurar sus directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md). También puede establecer la clasificación de SCL para los mensajes que coinciden con las condiciones específicas mediante el uso de reglas de transporte, tal como se describe en [las reglas de flujo de correo de uso para establecer el nivel de confianza de correo no deseado (SCL) en los mensajes](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md). Si utiliza una regla de transporte para establecer SCL de 7, 8 o 9 se tratará el mensaje como correo no deseado de alta confianza. 
  
||
|:-----|
|![El icono reducido de LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **¿Es la primera vez que usa Office 365?**         LinkedIn Learning pone a su disposición vídeos gratuitos de cursos de **Office 365 admins and IT pros**. |
   


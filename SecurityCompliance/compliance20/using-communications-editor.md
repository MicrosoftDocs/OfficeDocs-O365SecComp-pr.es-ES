---
title: Usar el editor de comunicaciones
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: c2957c88217bce4c9a34f8d3f9a9e291f1223cc9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32241247"
---
# <a name="use-the-communications-editor"></a>Usar el editor de comunicaciones

Al definir el contenido del contenido del portal, las notificaciones de retención legal y los avisos/escalas relacionados, puede aprovechar el editor de comunicaciones para formatear y personalizar el contenido de forma dinámica.

## <a name="rich-text-editor"></a>Editor de texto enriquecido 

El editor de comunicaciones permite al usuario personalizar el texto con las opciones del editor. Por ejemplo, los usuarios pueden cambiar los tipos de fuente, crear listas con viñetas, resaltar contenido, etc. 

## <a name="merge-field-variables"></a>Combinar variables de campo

Puede aprovechar las variables de combinación de correo electrónico del editor de comunicaciones para incrustar atributos de custodios personalizados en el texto del cuerpo de una comunicación. Cuando se envía al custodio, el campo de combinación se rellenará con el campo correspondiente. Por ejemplo, cuando se envía a custodio Andrés Díaz, el campo de combinación [nombre del custodio] se convertiría con el nombre correspondiente. 

Puede usar los campos de combinación de correo electrónico seleccionando los iconos de **campo de combinación** en la parte superior del control del editor de texto enriquecido. El marcador de posición se agregará en función de la ubicación del cursor de los usuarios. 

### <a name="list-of-merge-field-variables"></a>Lista de variables de campo de combinación

| Nombre del campo                  | Detalles de campo | 
| :------------------- | :------------------- |
| Nombre para mostrar  | Nombre y apellido del custodio. | 
| Vínculo de confirmación | Un vínculo personalizado para registrar la confirmación de cada custodio.|                 |
| Vínculo al portal     | Un vínculo personalizado para el portal de cumplimiento de la custodio.|                |
| Responsable de la expedición                   | La dirección de correo electrónico del oficial de expedición especificado.|                   |
| Fecha de emisión                   | La fecha en que se emitió el aviso (UTC).              |
---
title: Con el editor de comunicaciones
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 107f45510bcf70942c6f03bdfed0a9090f1d83c0
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608367"
---
# <a name="using-the-communications-editor"></a>Con el Editor de comunicaciones
Tal y como se define el contenido del contenido del portal, con fines legales mantenga las notificaciones y avisos/escalaciones relacionados, puede aprovechar el Editor de comunicaciones para aplicar formato y personalizar dinámicamente el contenido.

## <a name="rich-text-editor"></a>Editor de texto enriquecido 

El Editor de Communications permite al usuario personalizar el texto con las opciones del editor. Por ejemplo, los usuarios pueden cambiar los tipos de fuente, crear listas con viñetas, contenido de resaltado y mucho más. 

<<include screenshot>>

## <a name="merge-field-variables"></a>Combinar Variables de campo

Puede sacar provecho de las variables de combinación de correo electrónico desde el Editor de comunicaciones para incrustar atributos de custodia personalizada en texto de cuerpo de una comunicación. Cuando se envía a la custodia, se rellenará el campo de combinación con el campo correspondiente. Por ejemplo, cuando se envía a custodia John Smith, el campo de combinación de [nombre de custodia] ¿traducirse con el nombre correspondiente. 

Puede usar los campos de combinación de correo electrónico mediante la selección de los iconos de **Campo de combinación** en la parte superior del control de editor de texto enriquecido. El marcador de posición se agregarán en función desactiva la ubicación del cursor de los usuarios. 

### <a name="list-of-merge-field-variables"></a>Lista de Variables de campo de combinación
| Nombre de campo                  | Detalles del campo | 
| :------------------- | :-------------------: |
| Nombre para mostrar  | Custodia y los apellidos del nombre | 
| Vínculo de confirmación                 | Vínculo personalizado para registrar la confirmación de cada custodia                 |
| Vínculo del portal     | Vínculo personalizado para el Portal de cumplimiento de normas de custodia                 |
| Emitir ordenador                   | Dirección de correo electrónico del ordenador emisora especificado                   |
| Fecha de emisión                   | fecha en la que el aviso se emitió (UTC)              |
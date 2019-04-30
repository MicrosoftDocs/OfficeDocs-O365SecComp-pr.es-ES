---
title: Volver a intentar una búsqueda de contenido para resolver un error de ubicación de contenido
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use el botón Reintentar para resolver búsquedas de contenido que tienen errores de ubicación de contenido.
ms.openlocfilehash: 0963bccfe88a74b82ec3155469ca6d892bf2f7d8
ms.sourcegitcommit: 72e8a74b55fe7f56b50e30ff10a635734b5a3220
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2019
ms.locfileid: "33472385"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>Volver a intentar una búsqueda de contenido para resolver un error de ubicación de contenido

Cuando usa la búsqueda de contenido en el centro de seguridad y cumplimiento para buscar en un gran número de buzones, es posible que obtenga errores de búsqueda similares a los siguientes:

```
Error

The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

Estos errores (con códigos de error de CS008-009 y CS012-002) indican que la búsqueda de contenido no pudo buscar ubicaciones de contenido específicas; en este ejemplo, no se han buscado dos buzones. Estos errores se muestran en la página flotante de detalles de estado de la búsqueda de contenido.

## <a name="cause-of-content-location-errors"></a>Causa de errores de ubicación de contenido

Al buscar en un gran número de buzones, la búsqueda se distribuye entre miles de servidores en un centro de recursos de Microsoft. En un momento dado, los servidores específicos podrían estar en estado de reinicio o en proceso de conmutación por error a copias redundantes. En cualquiera de estos casos, se agotará el tiempo de espera de la solicitud de búsqueda de contenido para recuperar datos. En el ejemplo anterior, los errores de los buzones de correo que no superaron el resultado de la búsqueda superan el tiempo de espera.

## <a name="resolving-content-location-errors"></a>Resolución de errores de ubicación de contenido

El reinicio de la búsqueda con frecuencia provocará errores similares en servidores diferentes. En lugar de reiniciar la búsqueda, haga clic en el botón **Reintentar** que se muestra en la parte superior de la página de resultados de búsqueda.

![Haga clic en el botón Reintentar para resolver los errores de ubicación de contenido](media/retrycontentsearch3.png)

Esto hará que se vuelva a intentar la búsqueda de los buzones de correo que no se realizaron correctamente. Cuando se vuelve a intentar la búsqueda, se conservan los otros resultados que se devolvieron correctamente.

## <a name="tips-to-avoid-content-location-errors"></a>Sugerencias para evitar errores de ubicación de contenido

Estas son algunas de las causas de los errores de ubicación de contenido y algunas sugerencias para ayudarle a evitarlos cuando busque grandes cantidades de buzones.

- El buzón en el que se realiza la búsqueda puede estar ocupado debido a la actividad del usuario. En este caso, el servicio de búsqueda se puede limitar para evitar que el buzón deje de estar disponible. Para evitarlo, intente ejecutar búsquedas durante el horario no comercial.

- La consulta de búsqueda podría estar recuperando demasiado contenido del buzón. Si es posible, intente restringir el ámbito de la búsqueda usando palabras clave, intervalos de fechas y condiciones de búsqueda.

- Demasiadas palabras clave o frases de palabras clave al crear una consulta de búsqueda con la [lista de palabras clave](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches). Cuando se ejecuta una consulta de búsqueda que usa la lista de palabras clave, el servicio básicamente ejecuta una búsqueda independiente para cada fila de la lista de palabras clave de modo que se puedan generar estadísticas. Si está usando la lista de palabras clave en las consultas de búsqueda, minimice el número de filas de la lista de palabras clave o divida las palabras clave de número en listas más pequeñas y cree una búsqueda diferente para cada lista de palabras clave.

  > [!NOTE]
  > Para ayudar a reducir los problemas causados por listas de palabras clave grandes, ahora está limitado a un máximo de 20 filas en la lista de palabras clave de una consulta de búsqueda.

- Se están realizando demasiadas búsquedas en el mismo buzón al mismo tiempo. Si es posible, intente ejecutar una búsqueda cada vez en un buzón.

- Buscar en un gran número de buzones en una sola búsqueda. La probabilidad de errores de ubicación de contenido aumenta al buscar un gran número de buzones. Si es posible, intente ejecutar varias búsquedas para que cada búsqueda incluya un subconjunto de buzones de correo en la organización.

- Se está realizando el mantenimiento necesario en el buzón de correo. Aunque esta causa probablemente se produzca con frecuencia, espere un poco después de recibir el error de ubicación de contenido y, a continuación, vuelva a intentar la búsqueda.

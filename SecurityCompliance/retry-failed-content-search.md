---
title: Vuelva a intentar una búsqueda de contenido para resolver un error de ubicación de contenido
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use el botón Reintentar para resolver las búsquedas de contenido que tienen errores de ubicación de contenido.
ms.openlocfilehash: 0fdc11593fec42e1f9f9b76fbbb408d9c16fd183
ms.sourcegitcommit: d5f841744b716fcf368c670009b61441f5a5eed2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2018
ms.locfileid: "27210201"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>Vuelva a intentar una búsqueda de contenido para resolver un error de ubicación de contenido

Cuando se usa la búsqueda de contenido en el centro de cumplimiento y seguridad de Office 365 para buscar un gran número de buzones (por ejemplo, buscar 100.000 buzones o más en una sola búsqueda de contenido), obtendrá errores de búsqueda que son similares a lo siguiente:

```
Error

The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

Estos errores (con códigos de error de CS008-009 y CS012-002) indican que no se pudieron búsqueda de contenido buscar en ubicaciones específicas de contenido; en este ejemplo, no se han buscado dos buzones. Estos errores se muestran en la página de emergente de detalles de estado de la búsqueda de contenido.

## <a name="cause-of-content-location-errors"></a>Causa de errores de ubicación de contenido

Al buscar en un gran número de buzones de correo, la búsqueda se distribuye a través de miles de servidores en un centro de datos de Microsoft. En un momento dado, servidores específicos podrían estar en estado de reinicio o en el proceso de conmutación por error para copias redundantes. En cualquiera de estos casos, la solicitud de búsqueda de contenido para recuperar datos será tiempo de espera. En el ejemplo anterior, los errores para los buzones de correo que no se pudo eran el resultado de la búsqueda alcanzar el tiempo límite.

## <a name="resolving-content-location-errors"></a>Resolución de errores de ubicación de contenido

Reiniciar la búsqueda a menudo provocarán errores similares en servidores diferentes. En lugar de reiniciar la búsqueda, haga clic en el botón **Reintentar** que se muestra en la parte superior de la página de resultados de búsqueda.

![Haga clic en el botón Reintentar para resolver errores de ubicación de contenido](media/retrycontentsearch3.png)

Esto dará como resultado de volver a intentar la búsqueda solo para los buzones de correo con errores. Cuando se vuelva a intentar la búsqueda, se conservan los otros resultados que se han devuelto correctamente.

## <a name="tips-to-avoid-content-location-errors"></a>Sugerencias para evitar errores de ubicación de contenido

A continuación presentamos algunas de las causas adición de errores de la ubicación del contenido y algunos consejos para ayudarle a evitarlos al buscar en un gran número de buzones de correo.

- El buzón de correo que se buscan esté ocupado debido a la actividad de usuario. En este caso, el servicio de búsqueda puede limitar propio para evitar que el buzón de correo no está disponible. Para evitar este problema, intente ejecutar búsquedas durante el horario no.

- La consulta de búsqueda puede estar recuperando demasiado contenido desde el buzón de correo. Si es posible, intente reducir el ámbito de la búsqueda mediante el uso de palabras clave, los intervalos de fechas y las condiciones de búsqueda.

- Demasiadas palabras clave o frases de palabra clave cuando se crea una consulta de búsqueda con la [lista de palabras clave](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches). Cuando se ejecuta una consulta de búsqueda que usa la lista de palabras clave, básicamente ejecuta el servicio una búsqueda independiente para cada fila en la lista de palabras clave para que se pueden generar las estadísticas. Si utiliza la lista de palabras clave en las consultas de búsqueda, minimizar el número de filas de la lista de palabras clave o dividir las palabras clave números en listas más pequeñas y crear una búsqueda diferente para cada lista de palabras clave.

  > [!NOTE]
  > Para ayudar a reducir los problemas de listas de palabras clave de gran tamaño, ahora está limitado a un máximo de 20 filas de la lista de palabras clave de una consulta de búsqueda.

- Un número excesivo de búsquedas se están ejecutando en el mismo buzón al mismo tiempo. Si es posible, intente ejecutar una búsqueda a la vez en un buzón de prueba.

- Búsqueda de un número excesivo de buzones de correo en una sola búsqueda. La probabilidad de errores de ubicación de contenido aumenta al buscar en un gran número de buzones de correo. Si es posible, intente ejecutar varias búsquedas de modo que cada búsqueda incluye un subconjunto de los buzones de correo en la organización.

- Mantenimiento necesario se lleva a cabo en el buzón de correo. Aunque esto causa probablemente se produce con poca frecuencia, esperar un poco mientras después de recibir el error de ubicación de contenido y, a continuación, vuelva a intentar la búsqueda.

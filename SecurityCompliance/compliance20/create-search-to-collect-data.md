---
title: Create a search
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 1aa4ce6e406e4b3a3b72b9d93f651416b1fc65f9
ms.sourcegitcommit: 803baca9f99a6691fb41a3308e799752e4d8f20c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222254"
---
# <a name="create-a-search"></a>Create a search

En la ficha **búsquedas** en su caso, puede crear una nueva búsqueda haciendo clic en **nueva búsqueda** y siguiendo el asistente.

## <a name="name-your-search-and-give-it-a-description"></a>Asigne un nombre a la búsqueda y dele una descripción

Cada búsqueda con un caso debe tener un nombre único. Opcionalmente, puede proporcionar una descripción para la búsqueda. 

## <a name="define-your-search-query-and-conditions"></a>Definir la consulta y las condiciones de búsqueda

Puede definir las palabras clave Query y las condiciones de la búsqueda con las tarjetas de condición predefinidas o con el lenguaje de consulta de palabras clave (KQL). Para obtener más información, vea [crear consultas de búsqueda](building-search-queries.md).

## <a name="choose-the-custodians-to-search-from"></a>Elegir los custodios donde buscar

Una vez que haya definido las condiciones, debe elegir qué ubicaciones desea buscar. Una forma de hacerlo es especificar los custodios que ya ha agregado al caso en el que desea realizar la búsqueda. Al seleccionar un custodio, se ejecutará la búsqueda en todos los orígenes de datos asignados al custodio. Consulte [work with custodios](managing-custodians.md) para obtener más información sobre cómo agregar custodios a su caso y administrar sus orígenes de datos.

## <a name="choose-non-custodial-locations"></a>Elegir ubicaciones que no sean de privación

En algunos casos, es posible que quiera buscar orígenes de datos que no están asignados a un custodio. En este caso, puede especificar las ubicaciones en las que desea realizar búsquedas o elegir buscar en todas las ubicaciones de contenido de un servicio de Office 365 específico (por ejemplo, buscar en todos los buzones de Exchange o en todos los sitios de SharePoint y OneDrive para la empresa).
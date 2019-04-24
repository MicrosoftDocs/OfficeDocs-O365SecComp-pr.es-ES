---
title: Crear una búsqueda para recopilar datos
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
ms.openlocfilehash: 14f90b29cbff9c1a588b816563178039c7af7da6
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243418"
---
# <a name="create-a-search-to-collect-data"></a>Crear una búsqueda para recopilar datos

En la ficha **búsquedas** en su caso, puede crear una nueva búsqueda haciendo clic en **nueva búsqueda** y siguiendo el asistente.

## <a name="name-your-search-and-give-description"></a>Asigne un nombre a la búsqueda y proporcione una descripción

Cada búsqueda con un caso debe tener un nombre único. Opcionalmente, puede proporcionar una descripción para la búsqueda. 

## <a name="define-your-conditions"></a>Definir las condiciones

Puede definir las condiciones para la búsqueda con las tarjetas de condición predefinidas o con el lenguaje de consulta de palabras clave (KQL). Para obtener más información, vea [crear consultas de búsqueda](building-search-queries.md).

## <a name="choose-the-custodians-to-search-from"></a>Elegir los custodios donde buscar

Una vez que haya definido las condiciones, debe elegir qué ubicaciones desea buscar. Una forma de hacerlo es especificar los custodios que ya ha agregado al caso en el que desea realizar la búsqueda. Al seleccionar un custodio, se ejecutará la búsqueda en todos los orígenes de datos asignados al custodio. Consulte [work with custodios](managing-custodians.md) para obtener más información sobre cómo agregar custodios a su caso y administrar sus orígenes de datos.

## <a name="choose-non-custodial-locations"></a>Elegir ubicaciones que no sean de privación

En algunos casos, es posible que quiera buscar orígenes de datos que no están asignados a un custodio. En este caso, puede especificar las ubicaciones en las que desea realizar búsquedas o elegir buscar en todas las ubicaciones de contenido de un servicio de Office 365 específico (por ejemplo, buscar en todos los buzones de Exchange o en todos los sitios de SharePoint y OneDrive para la empresa).
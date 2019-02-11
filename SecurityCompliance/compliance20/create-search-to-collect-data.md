---
title: Crear una búsqueda para recopilar datos
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
ms.openlocfilehash: 773137cbfc73d449766e04bf7eccc77f8bdd0cca
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706141"
---
# <a name="create-a-search-to-collect-data"></a>Crear una búsqueda para recopilar datos

En la ficha de **búsquedas** en su caso, puede crear una nueva búsqueda haciendo clic en **nuevo de búsqueda** y siga el asistente.

## <a name="name-your-search-and-give-description"></a>Póngale un nombre la búsqueda y descripción

Cada búsqueda con un caso debe tener un nombre único. Puede proporcionar opcionalmente una descripción para la búsqueda. 

## <a name="define-your-conditions"></a>Definir las condiciones

Puede definir las condiciones para la búsqueda mediante las tarjetas de condición creados previamente o mediante el lenguaje de consulta de palabras clave (KQL). Para obtener más información, vea [las consultas de búsqueda de compilación](building-search-queries.md).

## <a name="choose-the-custodians-to-search-from"></a>Elija la custodia para buscar desde

Una vez que haya definido las condiciones, debe elegir las ubicaciones que desea buscar. Una forma de hacerlo es mediante la especificación de qué custodia ya ha agregado el caso que desea buscar. Mediante la selección de custodia, se ejecutará la búsqueda en todos los orígenes de datos que se asignan a la custodia. Para obtener más información acerca de cómo agregar a custodia a su caso y administrar sus orígenes de datos, vea [trabajar con custodia](managing-custodians.md) .

## <a name="choose-non-custodial-locations"></a>Elija las ubicaciones que no sean custodia

En algunos casos, es posible que desee buscar en orígenes de datos que no se asignan a una custodia. En este caso, puede especificar las ubicaciones que desea buscar, o elegir buscar todas las ubicaciones de contenido para un servicio específico de Office 365 (por ejemplo, busca todos los buzones de Exchange o con SharePoint y OneDrive de todos los sitios de profesionales).
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
# <a name="create-a-search-to-collect-data"></a><span data-ttu-id="46401-102">Crear una búsqueda para recopilar datos</span><span class="sxs-lookup"><span data-stu-id="46401-102">Create a search to collect data</span></span>

<span data-ttu-id="46401-103">En la ficha de **búsquedas** en su caso, puede crear una nueva búsqueda haciendo clic en **nuevo de búsqueda** y siga el asistente.</span><span class="sxs-lookup"><span data-stu-id="46401-103">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

## <a name="name-your-search-and-give-description"></a><span data-ttu-id="46401-104">Póngale un nombre la búsqueda y descripción</span><span class="sxs-lookup"><span data-stu-id="46401-104">Name your search and give description</span></span>

<span data-ttu-id="46401-p101">Cada búsqueda con un caso debe tener un nombre único. Puede proporcionar opcionalmente una descripción para la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="46401-p101">Each search with a case should have a unique name. You can optionally provide a description for your search.</span></span> 

## <a name="define-your-conditions"></a><span data-ttu-id="46401-107">Definir las condiciones</span><span class="sxs-lookup"><span data-stu-id="46401-107">Define your conditions</span></span>

<span data-ttu-id="46401-p102">Puede definir las condiciones para la búsqueda mediante las tarjetas de condición creados previamente o mediante el lenguaje de consulta de palabras clave (KQL). Para obtener más información, vea [las consultas de búsqueda de compilación](building-search-queries.md).</span><span class="sxs-lookup"><span data-stu-id="46401-p102">You can define the conditions for your search using the pre-built condition cards or using Keyword Query Language (KQL). For more information, see [Build search queries](building-search-queries.md).</span></span>

## <a name="choose-the-custodians-to-search-from"></a><span data-ttu-id="46401-110">Elija la custodia para buscar desde</span><span class="sxs-lookup"><span data-stu-id="46401-110">Choose the custodians to search from</span></span>

<span data-ttu-id="46401-p103">Una vez que haya definido las condiciones, debe elegir las ubicaciones que desea buscar. Una forma de hacerlo es mediante la especificación de qué custodia ya ha agregado el caso que desea buscar. Mediante la selección de custodia, se ejecutará la búsqueda en todos los orígenes de datos que se asignan a la custodia. Para obtener más información acerca de cómo agregar a custodia a su caso y administrar sus orígenes de datos, vea [trabajar con custodia](managing-custodians.md) .</span><span class="sxs-lookup"><span data-stu-id="46401-p103">Once you have defined your conditions, you need to choose which locations you want to search. One way to do it is by specifying which custodians you have already added to the case you want to search. By selecting a custodian, you will run the search against all data sources mapped to the custodian. See [Work with custodians](managing-custodians.md) for more information on how to add custodians to your case and manage their data sources.</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="46401-115">Elija las ubicaciones que no sean custodia</span><span class="sxs-lookup"><span data-stu-id="46401-115">Choose non-custodial locations</span></span>

<span data-ttu-id="46401-p104">En algunos casos, es posible que desee buscar en orígenes de datos que no se asignan a una custodia. En este caso, puede especificar las ubicaciones que desea buscar, o elegir buscar todas las ubicaciones de contenido para un servicio específico de Office 365 (por ejemplo, busca todos los buzones de Exchange o con SharePoint y OneDrive de todos los sitios de profesionales).</span><span class="sxs-lookup"><span data-stu-id="46401-p104">In some cases, you may wish to search data sources that are not mapped to a custodian. In this case, you can specify the locations you would like to search, or choose to search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or all SharePoint and OneDrive for Business sites).</span></span>
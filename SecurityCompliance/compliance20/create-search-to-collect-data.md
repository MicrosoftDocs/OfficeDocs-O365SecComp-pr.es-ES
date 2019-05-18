---
title: Crear una búsqueda para recopilar datos
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
ms.openlocfilehash: 360ba6a67d43a0b78b1104ae64885697009bb222
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155112"
---
# <a name="create-a-search-to-collect-data"></a><span data-ttu-id="bf76f-102">Crear una búsqueda para recopilar datos</span><span class="sxs-lookup"><span data-stu-id="bf76f-102">Create a search to collect data</span></span>

<span data-ttu-id="bf76f-103">En la ficha **búsquedas** en su caso, puede crear una nueva búsqueda haciendo clic en **nueva búsqueda** y siguiendo el asistente.</span><span class="sxs-lookup"><span data-stu-id="bf76f-103">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

## <a name="name-your-search-and-give-description"></a><span data-ttu-id="bf76f-104">Asigne un nombre a la búsqueda y proporcione una descripción</span><span class="sxs-lookup"><span data-stu-id="bf76f-104">Name your search and give description</span></span>

<span data-ttu-id="bf76f-105">Cada búsqueda con un caso debe tener un nombre único.</span><span class="sxs-lookup"><span data-stu-id="bf76f-105">Each search with a case should have a unique name.</span></span> <span data-ttu-id="bf76f-106">Opcionalmente, puede proporcionar una descripción para la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="bf76f-106">You can optionally provide a description for your search.</span></span> 

## <a name="define-your-conditions"></a><span data-ttu-id="bf76f-107">Definir las condiciones</span><span class="sxs-lookup"><span data-stu-id="bf76f-107">Define your conditions</span></span>

<span data-ttu-id="bf76f-108">Puede definir las condiciones para la búsqueda con las tarjetas de condición predefinidas o con el lenguaje de consulta de palabras clave (KQL).</span><span class="sxs-lookup"><span data-stu-id="bf76f-108">You can define the conditions for your search using the pre-built condition cards or using Keyword Query Language (KQL).</span></span> <span data-ttu-id="bf76f-109">Para obtener más información, vea [crear consultas de búsqueda](building-search-queries.md).</span><span class="sxs-lookup"><span data-stu-id="bf76f-109">For more information, see [Build search queries](building-search-queries.md).</span></span>

## <a name="choose-the-custodians-to-search-from"></a><span data-ttu-id="bf76f-110">Elegir los custodios donde buscar</span><span class="sxs-lookup"><span data-stu-id="bf76f-110">Choose the custodians to search from</span></span>

<span data-ttu-id="bf76f-111">Una vez que haya definido las condiciones, debe elegir qué ubicaciones desea buscar.</span><span class="sxs-lookup"><span data-stu-id="bf76f-111">Once you have defined your conditions, you need to choose which locations you want to search.</span></span> <span data-ttu-id="bf76f-112">Una forma de hacerlo es especificar los custodios que ya ha agregado al caso en el que desea realizar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="bf76f-112">One way to do it is by specifying which custodians you have already added to the case you want to search.</span></span> <span data-ttu-id="bf76f-113">Al seleccionar un custodio, se ejecutará la búsqueda en todos los orígenes de datos asignados al custodio.</span><span class="sxs-lookup"><span data-stu-id="bf76f-113">By selecting a custodian, you will run the search against all data sources mapped to the custodian.</span></span> <span data-ttu-id="bf76f-114">Consulte [work with custodios](managing-custodians.md) para obtener más información sobre cómo agregar custodios a su caso y administrar sus orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="bf76f-114">See [Work with custodians](managing-custodians.md) for more information on how to add custodians to your case and manage their data sources.</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="bf76f-115">Elegir ubicaciones que no sean de privación</span><span class="sxs-lookup"><span data-stu-id="bf76f-115">Choose non-custodial locations</span></span>

<span data-ttu-id="bf76f-116">En algunos casos, es posible que quiera buscar orígenes de datos que no están asignados a un custodio.</span><span class="sxs-lookup"><span data-stu-id="bf76f-116">In some cases, you may wish to search data sources that are not mapped to a custodian.</span></span> <span data-ttu-id="bf76f-117">En este caso, puede especificar las ubicaciones en las que desea realizar búsquedas o elegir buscar en todas las ubicaciones de contenido de un servicio de Office 365 específico (por ejemplo, buscar en todos los buzones de Exchange o en todos los sitios de SharePoint y OneDrive para la empresa).</span><span class="sxs-lookup"><span data-stu-id="bf76f-117">In this case, you can specify the locations you would like to search, or choose to search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or all SharePoint and OneDrive for Business sites).</span></span>
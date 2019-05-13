---
title: Tipos de información confidencial personalizada para DLP
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/23/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga la información general de los tipos de información confidencial personalizada para DLP.
ms.openlocfilehash: a31817b2de1f48a5f49c02af150ce40a9d58c24a
ms.sourcegitcommit: 666bc17da0ab0969cf46f99f8726f463327cf599
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2019
ms.locfileid: "33829133"
---
# <a name="custom-sensitive-information-types"></a><span data-ttu-id="d6ed0-103">Tipos de información confidencial personalizada</span><span class="sxs-lookup"><span data-stu-id="d6ed0-103">Custom sensitive information types in PowerShell</span></span>

## <a name="overview"></a><span data-ttu-id="d6ed0-104">Información general</span><span class="sxs-lookup"><span data-stu-id="d6ed0-104">Overview</span></span>

<span data-ttu-id="d6ed0-105">Office 365 incluye muchos tipos de información confidencial que están listos para usarse en su organización, como [prevención de pérdida de datos](data-loss-prevention-policies.md) (DLP), o con [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="d6ed0-105">Office 365 includes many built-in sensitive information types that are ready for you to use in your organization, such as for [data loss prevention](data-loss-prevention-policies.md) (DLP), or with [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span> <span data-ttu-id="d6ed0-106">Los tipos de información confidencial integrados pueden ayudar a identificar y proteger números de tarjetas de crédito, números de cuentas bancarias, números de pasaporte y más, en función de los patrones definidos por una expresión regular (regex) o una función.</span><span class="sxs-lookup"><span data-stu-id="d6ed0-106">Built-in sensitive information types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more, based on patterns that are defined by a regular expression (regex) or a function.</span></span> <span data-ttu-id="d6ed0-107">Para obtener más información, consulte [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d6ed0-107">To learn more, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>

<span data-ttu-id="d6ed0-108">Pero, ¿qué sucede si necesita identificar y proteger un tipo diferente de información confidencial, como el id. de empleados o los números de proyecto, mediante un formato específico para su organización?</span><span class="sxs-lookup"><span data-stu-id="d6ed0-108">But what if you need to identify and protect a different type of sensitive information, such as for employee IDs or project numbers, using a format that's specific to your organization?</span></span> <span data-ttu-id="d6ed0-109">Para ello, puede crear un tipo de información confidencial personalizado.</span><span class="sxs-lookup"><span data-stu-id="d6ed0-109">To do this, you can create a custom sensitive information type.</span></span>

<span data-ttu-id="d6ed0-110">Estas son las partes básicas de un tipo personalizado de información confidencial:</span><span class="sxs-lookup"><span data-stu-id="d6ed0-110">The fundamental parts of a custom sensitive information type are:</span></span>

- <span data-ttu-id="d6ed0-111">**Patrón principal**: números de id. de empleado, números de proyecto, etc. Suele identificarse mediante una expresión regular (regex), pero también puede ser una lista de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="d6ed0-111">**Primary pattern**: employee ID numbers, project numbers, etc. This is typically identified by a regular expression (RegEx), but it can also be a list of keywords.</span></span>

- <span data-ttu-id="d6ed0-p103">**Evidencia adicional**: imagine que busca un número de id. de empleado de nueve dígitos. No todos los números de nueve dígitos son números de id. de empleado, pero puede buscar texto adicional (palabras clave como “empleado”, “identificación” o “id.”, o bien otros patrones de texto basados en expresiones regulares). Esta evidencia complementaria (también conocida como _evidencia_ _corroborativa_) incrementa la probabilidad de que el número de nueve dígitos encontrado en el contenido sea realmente un número de id. de empleado.</span><span class="sxs-lookup"><span data-stu-id="d6ed0-p103">**Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.</span></span>

- <span data-ttu-id="d6ed0-p104">**Proximidad de caracteres**: tiene sentido que, cuanto más próximos estén entre sí el patrón principal y la evidencia complementaria, más probabilidades habrá de que el contenido detectado sea lo que busca. Puede especificar la distancia de caracteres entre el patrón principal y la evidencia complementaria (también conocida como _ventana de proximidad_), como se muestra en el diagrama siguiente:</span><span class="sxs-lookup"><span data-stu-id="d6ed0-p104">**Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:</span></span>

    ![Diagrama de evidencia corroborativa y ventana de proximidad](media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- <span data-ttu-id="d6ed0-p105">**Nivel de confianza**: cuantas más evidencias complementarias tenga, mayor será la probabilidad de que una coincidencia contenga la información confidencial que busca. Puede asignar mayores niveles de confianza a las coincidencias detectadas mediante el uso de más evidencias.</span><span class="sxs-lookup"><span data-stu-id="d6ed0-p105">**Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.</span></span>

  <span data-ttu-id="d6ed0-p106">Cuando esté conforme, un patrón devolverá un recuento y un nivel de confianza, que podrá usar en las condiciones de las directivas DLP. Al agregar a una directiva DLP una condición para detectar un tipo de información confidencial, puede editar el recuento y el nivel de confianza, como se muestra en el diagrama siguiente:</span><span class="sxs-lookup"><span data-stu-id="d6ed0-p106">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:</span></span>

    ![Opciones de precisión de coincidencia y recuento de instancias](media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="d6ed0-123">Crear tipos de información confidencial personalizados</span><span class="sxs-lookup"><span data-stu-id="d6ed0-123">Creating custom sensitive information types</span></span>

<span data-ttu-id="d6ed0-124">Para crear tipos de información confidencial personalizados en el Centro de seguridad y cumplimiento, puede elegir una de estas opciones:</span><span class="sxs-lookup"><span data-stu-id="d6ed0-124">To create custom sensitive information types in the Security & Compliance Center, you have the following options:</span></span>

- <span data-ttu-id="d6ed0-125">**Usar EDM** (nuevo). Puede establecer los tipos de información confidencial mediante la clasificación basada en la exacta coincidencia de los datos (EDM).</span><span class="sxs-lookup"><span data-stu-id="d6ed0-125">**Use EDM** (NEW!) You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="d6ed0-126">Este método le permite crear un tipo de información confidencial dinámico con una base de datos segura que puede actualizar periódicamente.</span><span class="sxs-lookup"><span data-stu-id="d6ed0-126">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="d6ed0-127">Vea [Crear un tipo de información confidencial personalizado con coincidencia exacta de datos (versión preliminar)](create-custom-sensitive-info-type-edm.md)</span><span class="sxs-lookup"><span data-stu-id="d6ed0-127">See [Create a custom sensitive information type with Exact Data Match based classification (Preview)](create-custom-sensitive-info-type-edm.md).</span></span>

- <span data-ttu-id="d6ed0-128">**Usar PowerShell** Puede configurar los tipos de información confidencial con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6ed0-128">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="d6ed0-129">Aunque este método es más complejo que utilizar la interfaz de usuario, tendrá más opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="d6ed0-129">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="d6ed0-130">Vea [Crear un tipo de información confidencial en el centro de cumplimiento y seguridad PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="d6ed0-130">Create a custom sensitive information type in Security & Compliance Center PowerShell</span></span>

- <span data-ttu-id="d6ed0-131">**Usar la interfaz de usuario** Puede configurar un tipo de información confidencial personalizado mediante la interfaz de usuario del centro de cumplimiento y seguridad.</span><span class="sxs-lookup"><span data-stu-id="d6ed0-131">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="d6ed0-132">Con este método, puede usar expresiones regulares, palabras clave y diccionarios de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="d6ed0-132">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="d6ed0-133">Para obtener más información, consulte [Crear un tipo de información confidencial](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="d6ed0-133">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>




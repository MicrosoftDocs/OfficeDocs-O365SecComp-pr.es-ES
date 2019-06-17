---
title: Introducción a las barreras de información
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/13/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Usar barreras de la información para garantizar el cumplimiento de la comunicación mediante Microsoft Teams en su organización.
ms.openlocfilehash: a2c202d08f1de60f92f13b2ac4c2b9d3c7f900e8
ms.sourcegitcommit: eeb51470d8996e93fac28d7f12c6117e2aeb0cf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2019
ms.locfileid: "34935942"
---
# <a name="information-barriers-preview"></a><span data-ttu-id="22d51-103">Barreras de la información (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="22d51-103">Information barriers (Preview)</span></span>

## <a name="overview"></a><span data-ttu-id="22d51-104">Información general</span><span class="sxs-lookup"><span data-stu-id="22d51-104">Overview</span></span>

<span data-ttu-id="22d51-105">Los servicios en la nube de Microsoft incluyen eficaces capacidades de comunicación y colaboración.</span><span class="sxs-lookup"><span data-stu-id="22d51-105">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="22d51-106">Pero supongamos que desea restringir las comunicaciones entre dos grupos para evitar que se produzca un conflicto de intereses en la organización.</span><span class="sxs-lookup"><span data-stu-id="22d51-106">But suppose that you want to restrict communications between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="22d51-107">O quizás desee restringir las comunicaciones entre determinadas personas dentro de la organización con el fin de proteger la información interna.</span><span class="sxs-lookup"><span data-stu-id="22d51-107">Or, perhaps you want to restrict communications between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="22d51-108">Microsoft 365 permite la comunicación y la colaboración entre grupos y organizaciones, así que hay una forma de restringir las comunicaciones entre grupos de usuarios específicos cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="22d51-108">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communications among specific groups of users when necessary?</span></span> <span data-ttu-id="22d51-109">Con las barreras de la información, puede hacerlo.</span><span class="sxs-lookup"><span data-stu-id="22d51-109">With information barriers, you can!</span></span> 

<span data-ttu-id="22d51-110">Las barreras de la información están ahora en versión preliminar, comenzando con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="22d51-110">Information barriers are in preview now, beginning with Microsoft Teams.</span></span> <span data-ttu-id="22d51-111">Cuando estas características están disponibles para su organización, un administrador de cumplimiento o una barrera de la información pueden definir directivas para permitir o impedir las comunicaciones entre grupos de usuarios en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="22d51-111">When these features are available for your organization, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="22d51-112">Las directivas de barrera de información se pueden usar para situaciones como estas:</span><span class="sxs-lookup"><span data-stu-id="22d51-112">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="22d51-113">Un comerciante de día no puede llamar a alguien del equipo de marketing</span><span class="sxs-lookup"><span data-stu-id="22d51-113">A day trader cannot call someone on the marketing team</span></span>
- <span data-ttu-id="22d51-114">El personal de finanzas que trabaja con información de la compañía confidencial no puede recibir llamadas de determinados grupos de la organización</span><span class="sxs-lookup"><span data-stu-id="22d51-114">Finance personnel working on confidential company information cannot receive calls from certain groups within their organization</span></span>
- <span data-ttu-id="22d51-115">Un equipo interno con material de secreto comercial no puede llamar o chatear en línea con personas de determinados grupos de la organización</span><span class="sxs-lookup"><span data-stu-id="22d51-115">An internal team with trade secret material cannot call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="22d51-116">Un equipo de investigación solo puede llamar o chatear en línea con un equipo de desarrollo del producto</span><span class="sxs-lookup"><span data-stu-id="22d51-116">A research team can only call or chat online with a product development team</span></span>

<span data-ttu-id="22d51-117">Para todos estos escenarios de ejemplo (y más), se pueden definir directivas de barrera de información para impedir o permitir las comunicaciones en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="22d51-117">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="22d51-118">Estas directivas pueden impedir que los usuarios llamen o chatean con ellos que no deben, o bien permitir que los usuarios se comuniquen solo con grupos específicos en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="22d51-118">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="22d51-119">Con las directivas de barrera de información en vigor, cada vez que los usuarios que están cubiertos por estas directivas intentan comunicarse con otros usuarios de Microsoft Teams, se realizan comprobaciones para evitar (o permitir) la comunicación (según las directivas de la barrera de información definida).</span><span class="sxs-lookup"><span data-stu-id="22d51-119">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> <span data-ttu-id="22d51-120">Para obtener más información sobre la experiencia del usuario con barreras de información, consulte [barreras de la información en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span><span class="sxs-lookup"><span data-stu-id="22d51-120">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="22d51-121">Las barreras de la información no se aplican a las comunicaciones de correo electrónico ni al uso compartido de archivos a través de SharePoint Online o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="22d51-121">Information barriers will not apply to email communications or to file sharing through SharePoint Online or OneDrive.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="22d51-122">Permisos y licencias necesarios</span><span class="sxs-lookup"><span data-stu-id="22d51-122">Required licenses and permissions</span></span>

<span data-ttu-id="22d51-123">**Actualmente, la característica de barrera de información está en la versión preliminar privada**.</span><span class="sxs-lookup"><span data-stu-id="22d51-123">**Currently, the information barrier feature is in private preview**.</span></span> <span data-ttu-id="22d51-124">Si estas características están disponibles para el público en general, se incluirán en las suscripciones, como:</span><span class="sxs-lookup"><span data-stu-id="22d51-124">When these features are generally available, they'll be included in subscriptions, such as:</span></span>

- <span data-ttu-id="22d51-125">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="22d51-125">Microsoft 365 E5</span></span>
- <span data-ttu-id="22d51-126">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="22d51-126">Office 365 E5</span></span>
- <span data-ttu-id="22d51-127">Cumplimiento avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="22d51-127">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="22d51-128">Protección de la información y cumplimiento de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="22d51-128">Microsoft 365 E5 Information Protection and Compliance</span></span>

<span data-ttu-id="22d51-129">Para obtener más información, consulte [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span><span class="sxs-lookup"><span data-stu-id="22d51-129">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

<span data-ttu-id="22d51-130">Para [definir o editar directivas de barrera de información](information-barriers-policies.md), debe tener asignado uno de los siguientes roles:</span><span class="sxs-lookup"><span data-stu-id="22d51-130">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="22d51-131">Administrador global de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="22d51-131">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="22d51-132">Administrador global de Office 365</span><span class="sxs-lookup"><span data-stu-id="22d51-132">Office 365 global administrator</span></span>
- <span data-ttu-id="22d51-133">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="22d51-133">Compliance administrator</span></span>
- <span data-ttu-id="22d51-134">Administrador de obstáculos de la información</span><span class="sxs-lookup"><span data-stu-id="22d51-134">Information barriers administrator</span></span>

<span data-ttu-id="22d51-135">Debe estar familiarizado con los cmdlets de PowerShell para poder definir, validar o editar directivas de barrera de información.</span><span class="sxs-lookup"><span data-stu-id="22d51-135">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="22d51-136">Aunque proporcionamos varios ejemplos de cmdlets de PowerShell en la [información de procedimientos](information-barriers-policies.md), necesitará conocer más detalles, como parámetros, para su organización.</span><span class="sxs-lookup"><span data-stu-id="22d51-136">Although we provide several examples of PowerShell cmdlets in the [how-to information](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="22d51-137">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="22d51-137">Next steps</span></span>

- [<span data-ttu-id="22d51-138">Obtenga más información sobre las barreras de la información en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="22d51-138">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="22d51-139">Ver los atributos que se pueden usar para las directivas de barrera de información</span><span class="sxs-lookup"><span data-stu-id="22d51-139">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="22d51-140">Definir políticas para las barreras de la información</span><span class="sxs-lookup"><span data-stu-id="22d51-140">Define policies for information barriers</span></span>](information-barriers-policies.md) 


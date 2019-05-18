---
title: Configurar usuarios y casos en la exhibición de documentos electrónicos avanzada de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: 'Obtenga información sobre cómo configurar roles de usuario, crear casos y asignar usuarios a los casos en Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: 5eb019afcf57b6df17fd42f3058deb0f6b7229f5
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156472"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a><span data-ttu-id="45469-103">Configurar usuarios y casos en la exhibición de documentos electrónicos avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="45469-103">Set up users and cases in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="45469-104">En este tema se describe cómo configurar usuarios y casos para la exhibición avanzada de documentos electrónicos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="45469-104">This topic describes how to set up users and cases for Office 365 Advanced eDiscovery.</span></span>
  
> [!NOTE]
> <span data-ttu-id="45469-p101">Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="45469-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="45469-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="45469-107">Prerequisites</span></span>

<span data-ttu-id="45469-108">Antes de configurar casos y usuarios en la exhibición avanzada de documentos electrónicos, se requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="45469-108">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="45469-109">Para analizar los datos de un usuario con la exhibición avanzada de documentos electrónicos, el usuario (el custodio de los datos) debe tener asignada una licencia de Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="45469-109">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="45469-110">Como alternativa, se puede asignar una licencia independiente de eDiscovery avanzado a los usuarios con una licencia de Office 365 E1 o E3.</span><span class="sxs-lookup"><span data-stu-id="45469-110">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="45469-111">Los administradores y los responsables de cumplimiento que se asignan a los casos y usan la exhibición avanzada de documentos electrónicos para analizar los datos no necesitan una licencia E5.</span><span class="sxs-lookup"><span data-stu-id="45469-111">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="45469-112">Debe ser miembro del grupo de roles eDiscovery Manager en el centro de seguridad &amp; y cumplimiento de Office 365 para crear un caso de exhibición de documentos electrónicos y agregarle miembros.</span><span class="sxs-lookup"><span data-stu-id="45469-112">You have to be a member of the eDiscovery Manager role group in the Office 365 Security &amp; Compliance Center to create an eDiscovery case and add members to it.</span></span> <span data-ttu-id="45469-113">Para agregarse al grupo de roles de eDiscovery Manager en &amp; el centro de seguridad y cumplimiento, debe ser administrador global de la organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="45469-113">To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your Office 365 organization.</span></span> <span data-ttu-id="45469-114">Si no es un administrador global, deberá solicitar a un administrador global que le agregue al grupo de roles eDiscovery Manager.</span><span class="sxs-lookup"><span data-stu-id="45469-114">If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group.</span></span> <span data-ttu-id="45469-115">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="45469-115">For more information, see:</span></span>
    
  - [<span data-ttu-id="45469-116">Permisos en el centro de seguridad &amp; y cumplimiento de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="45469-116">Permissions in the Microsoft 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
    
  - [<span data-ttu-id="45469-117">Asignar permisos de eDiscovery en el centro de &amp; seguridad y cumplimiento de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="45469-117">Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="45469-118">Paso 1: asignar permisos de eDiscovery para los usuarios</span><span class="sxs-lookup"><span data-stu-id="45469-118">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="45469-119">El primer paso consiste en asignar a los usuarios los permisos de requisitos &amp; en el centro de seguridad y cumplimiento para que puedan agregarse como miembro de un caso de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="45469-119">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case.</span></span> <span data-ttu-id="45469-120">Una vez que un usuario se ha agregado como miembro de un caso en &amp; el centro de seguridad y cumplimiento, podrá obtener acceso al caso en la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="45469-120">After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="45469-121">Para asignar a un usuario los permisos necesarios para que se puedan agregar como miembro de un caso de exhibición de documentos electrónicos, vea el paso 1 en [casos de &amp; eDiscovery en el centro de seguridad y cumplimiento de Microsoft 365](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span><span class="sxs-lookup"><span data-stu-id="45469-121">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="45469-122">Paso 2: crear un caso de exhibición de documentos electrónicos y agregar miembros</span><span class="sxs-lookup"><span data-stu-id="45469-122">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="45469-123">El siguiente paso es crear un nuevo caso de exhibición de documentos electrónicos &amp; en el centro de seguridad y cumplimiento y agregar miembros.</span><span class="sxs-lookup"><span data-stu-id="45469-123">The next step is to create a new eDiscovery case in the Security &amp; Compliance Center and add members.</span></span> <span data-ttu-id="45469-124">Los miembros del caso podrán acceder al caso en la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="45469-124">Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="45469-125">Para crear un nuevo caso de eDiscovery, vea el paso 2 en [casos de eDiscovery en el &amp; centro de seguridad y cumplimiento de Microsoft 365](ediscovery-cases.md#step-2-create-a-new-case).</span><span class="sxs-lookup"><span data-stu-id="45469-125">To create a new eDiscovery case, see Step 2 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
    
2. <span data-ttu-id="45469-126">Para agregar miembros a un caso de eDiscovery, vea el paso 3 de [los casos de eDiscovery en &amp; el centro de seguridad y cumplimiento de 365 de Microsoft](ediscovery-cases.md#step-3-add-members-to-a-case) .</span><span class="sxs-lookup"><span data-stu-id="45469-126">To add members to an eDiscovery case, see Step 3 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span></span>
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="45469-127">Paso 3: ir a un caso en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="45469-127">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="45469-128">Después de crear un caso de exhibición de documentos electrónicos y agregar miembros, usted (o cualquier miembro del caso) puede tener acceso al caso correspondiente en eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="45469-128">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery.</span></span> <span data-ttu-id="45469-129">Para obtener acceso a un caso en la exhibición avanzada de documentos electrónicos, vea el paso 8 en [los casos de eDiscovery en el centro de seguridad &amp; y cumplimiento de Microsoft 365](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span><span class="sxs-lookup"><span data-stu-id="45469-129">To access a case in Advanced eDiscovery, see Step 8 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="45469-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="45469-130">See also</span></span>

[<span data-ttu-id="45469-131">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="45469-131">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="45469-132">Preparar datos</span><span class="sxs-lookup"><span data-stu-id="45469-132">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)
 
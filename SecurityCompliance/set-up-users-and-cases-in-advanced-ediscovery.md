---
title: Configurar usuarios y casos en eDiscovery avanzado de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: 'Obtenga información sobre cómo configurar las funciones de usuario, crear casos y asignar a usuarios a los casos de exhibición de documentos electrónicos avanzada de Office 365.  '
ms.openlocfilehash: 49f76b415d86035cecafc19c23b36c413f7576e5
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536453"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a><span data-ttu-id="2677c-103">Configurar usuarios y casos en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="2677c-103">Set up users and cases in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="2677c-104">En este tema se describe cómo configurar los usuarios y los casos de exhibición de documentos electrónicos avanzada de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2677c-104">This topic describes how to set up users and cases for Office 365 Advanced eDiscovery.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2677c-p101">Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="2677c-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="2677c-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2677c-107">Prerequisites</span></span>

<span data-ttu-id="2677c-108">Antes de configurar los casos y los usuarios de exhibición de documentos electrónicos avanzada, es necesario lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2677c-108">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="2677c-p102">Para analizar los datos de un usuario mediante la exhibición de documentos electrónicos avanzada, el usuario (la custodia de los datos) debe estar asignado una licencia de Office 365 E5. Como alternativa, se pueden asignar una licencia independiente de exhibición de documentos electrónicos avanzada a los usuarios con una licencia de Office 365 E1 o E3. Los administradores y responsables del cumplimiento normativo que se asignan a los casos y utilizan eDiscovery avanzada para analizar datos no necesitan una licencia de E5.</span><span class="sxs-lookup"><span data-stu-id="2677c-p102">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license. Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license. Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="2677c-p103">Tiene que ser un miembro del grupo de roles de administrador de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento para crear un caso de exhibición de documentos electrónicos y agregar miembros a ella. Para agregar su nombre para el grupo de roles de administrador de exhibición de documentos electrónicos en seguridad &amp; centro de cumplimiento, tiene que ser un administrador global de la organización de Office 365. Si no es un administrador global, debe solicitar un administrador global se agrega al grupo de roles de administrador de exhibición de documentos electrónicos. Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="2677c-p103">You have to be a member of the eDiscovery Manager role group in the Office 365 Security &amp; Compliance Center to create an eDiscovery case and add members to it. To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your Office 365 organization. If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group. For more information, see:</span></span>
    
  - [<span data-ttu-id="2677c-116">Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="2677c-116">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
    
  - [<span data-ttu-id="2677c-117">Asignar permisos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="2677c-117">Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="2677c-118">Paso 1: Asignar a los usuarios permisos de exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="2677c-118">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="2677c-p104">El primer paso consiste en asignar a los usuarios los permisos de requisito en la seguridad &amp; del centro de cumplimiento para que puedan me agrega como un miembro de un caso de exhibición de documentos electrónicos. Después de que un usuario se agrega como un miembro de un caso en la seguridad &amp; centro de cumplimiento, podrán tener acceso el caso de exhibición de documentos electrónicos avanzada.</span><span class="sxs-lookup"><span data-stu-id="2677c-p104">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case. After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="2677c-121">Para asignar un usuario los permisos necesarios para que se pueden agregar como un miembro de un caso de exhibición de documentos electrónicos, vea el paso 1 en [casos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span><span class="sxs-lookup"><span data-stu-id="2677c-121">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="2677c-122">Paso 2: Crear un caso de exhibición de documentos electrónicos y agregar miembros</span><span class="sxs-lookup"><span data-stu-id="2677c-122">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="2677c-p105">El siguiente paso es crear un nuevo caso de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento y agregar miembros. Los miembros de las mayúsculas y minúsculas, a continuación, podrá tener acceso el caso de exhibición de documentos electrónicos avanzada.</span><span class="sxs-lookup"><span data-stu-id="2677c-p105">The next step is to create a new eDiscovery case in the Security &amp; Compliance Center and add members. Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="2677c-125">Para crear un nuevo caso de exhibición de documentos electrónicos, vea el paso 2 en [casos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](ediscovery-cases.md#step-2-create-a-new-case).</span><span class="sxs-lookup"><span data-stu-id="2677c-125">To create a new eDiscovery case, see Step 2 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
    
2. <span data-ttu-id="2677c-126">Para agregar miembros a un caso de exhibición de documentos electrónicos, vea el paso 3 en [casos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](ediscovery-cases.md#step-3-add-members-to-a-case)</span><span class="sxs-lookup"><span data-stu-id="2677c-126">To add members to an eDiscovery case, see Step 3 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span></span>
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="2677c-127">Paso 3: Vaya a un caso de exhibición de documentos electrónicos avanzada</span><span class="sxs-lookup"><span data-stu-id="2677c-127">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="2677c-p106">Después de crear un caso de exhibición de documentos electrónicos y agregar a miembros, usted (o cualquier miembro de las mayúsculas y minúsculas) puede tener acceso el caso de exhibición de documentos electrónicos avanzada correspondiente. Para obtener acceso a un caso de exhibición de documentos electrónicos avanzada, vea el paso 8 en [casos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span><span class="sxs-lookup"><span data-stu-id="2677c-p106">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery. To access a case in Advanced eDiscovery, see Step 8 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2677c-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="2677c-130">See also</span></span>

[<span data-ttu-id="2677c-131">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="2677c-131">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="2677c-132">Preparación de datos</span><span class="sxs-lookup"><span data-stu-id="2677c-132">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)
  
[<span data-ttu-id="2677c-133">Acceso y roles de usuario</span><span class="sxs-lookup"><span data-stu-id="2677c-133">User roles and access</span></span>](user-roles-and-access-in-advanced-ediscovery.md)


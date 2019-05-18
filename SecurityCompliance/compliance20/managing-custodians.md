---
title: Trabajar con custodios en eDiscovery avanzado
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
description: La herramienta de administración de custodios de eDiscovery avanzado le permite administrar el flujo de trabajo en torno a la identificación, preservación y recopilación de datos asociados con las personas de interés en un caso legal.
ms.openlocfilehash: 6e365f0b7f80a0a5caa050b2e0b08c94dbed4746
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151602"
---
# <a name="work-with-custodians-in-advanced-ediscovery"></a><span data-ttu-id="37614-103">Trabajar con custodios en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="37614-103">Work with custodians in Advanced eDiscovery</span></span>

<span data-ttu-id="37614-104">Cuando una organización responde a una investigación legal, el flujo de trabajo en torno a la identificación, preservación y recopilación de contenido potencialmente relevante se basa en las personas de la organización que son los custodios de los datos relevantes.</span><span class="sxs-lookup"><span data-stu-id="37614-104">When an organization responds to a legal investigation, the workflow around identifying, preserving, and collecting potentially relevant content is based on the people in the organization who are the custodians of relevant data.</span></span> <span data-ttu-id="37614-105">En eDiscovery, estas personas se denominan custodios de *datos* ( \*\* o simplemente custodios) y se definen como "personas con control administrativo de un documento o un archivo electrónico".</span><span class="sxs-lookup"><span data-stu-id="37614-105">In eDiscovery, these individuals are called *data custodians* (or just *custodians*) and are defined as "persons having administrative control of a document or electronic file".</span></span> <span data-ttu-id="37614-106">Por ejemplo, el custodio de un mensaje de correo electrónico podría ser el propietario del buzón que contiene el mensaje relevante.</span><span class="sxs-lookup"><span data-stu-id="37614-106">For example, the custodian of an email message could be the owner of the mailbox that contains the relevant message.</span></span>  

<span data-ttu-id="37614-107">Cuando se inicia una investigación, el equipo de eDiscovery debe identificar rápidamente todos los custodios y orígenes de datos relevantes relacionados con el caso.</span><span class="sxs-lookup"><span data-stu-id="37614-107">When an investigation begins, the eDiscovery team must quickly identify all the relevant custodians and data sources related to the case.</span></span> <span data-ttu-id="37614-108">Con el tiempo, la lista de custodios y sus orígenes de datos puede aumentar o decreasse.</span><span class="sxs-lookup"><span data-stu-id="37614-108">Over time, the list of custodians and their data sources may increase or decreasse.</span></span> <span data-ttu-id="37614-109">Como resultado, las organizaciones deben mantener un proceso controlado en torno a la identificación, preservación y recopilación de contenido de apoyo durante todo el ciclo de vida de un caso.</span><span class="sxs-lookup"><span data-stu-id="37614-109">As a result, organizations must maintain a controlled process around identifying, preserving, and collecting custodial content throughout the life cycle of a case.</span></span>

<span data-ttu-id="37614-110">En un caso de exhibición avanzada de documentos electrónicos, los equipos jurídicos pueden agregar personas en su organización como custodios e identificar y conservar automáticamente orígenes de datos de Private como buzones de correo de Exchange, cuentas de OneDrive y sitios de SharePoint y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="37614-110">In an Advanced eDiscovery case, legal teams can add individuals in their organization as custodians, and automatically identify and preserve custodial data sources such as Exchange mailboxes, OneDrive accounts, and SharePoint and Teams sites.</span></span> <span data-ttu-id="37614-111">Mediante el uso de la herramienta de administración de custodios integrada en eDiscovery avanzado, las organizaciones pueden proteger la información almacenada electrónicamente de la eliminación accidental (o intencional).</span><span class="sxs-lookup"><span data-stu-id="37614-111">By using the built-in custodian management tool in Advanced eDiscovery, organizations can secure electronically stored information from inadvertent (or intentional) deletion.</span></span> <span data-ttu-id="37614-112">Esto le permite eliminar el proceso lento de tiempo y propenso a errores de tener que llevar a cabo manualmente los procesos de retención legal.</span><span class="sxs-lookup"><span data-stu-id="37614-112">This lets you eliminate the time-consuming and error-prone process of manually having to perform the legal hold processes.</span></span> 

<span data-ttu-id="37614-113">Para obtener más información sobre cómo trabajar con custodios, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="37614-113">For more information about working with custodians, see the following:</span></span> 

- [<span data-ttu-id="37614-114">Agregar administradores a un caso</span><span class="sxs-lookup"><span data-stu-id="37614-114">Add custodians to a case</span></span>](add-custodians-to-case.md)

- [<span data-ttu-id="37614-115">Administrar custodios en un caso</span><span class="sxs-lookup"><span data-stu-id="37614-115">Manage custodians in a case</span></span>](manage-new-custodians.md)

- [<span data-ttu-id="37614-116">Ver la actividad administrativa</span><span class="sxs-lookup"><span data-stu-id="37614-116">View custodian activity</span></span>](view-custodian-activity.md)

## <a name="advanced-ediscovery-permissions"></a><span data-ttu-id="37614-117">Permisos de eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="37614-117">Advanced eDiscovery permissions</span></span>

<span data-ttu-id="37614-118">En eDiscovery avanzado, puede usar el grupo de roles integrado eDiscovery Manager para asignar los permisos necesarios a los investigadores legales para que puedan administrar el flujo de trabajo de un extremo a otro en eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="37614-118">In Advanced eDiscovery, you can use the built-in eDiscovery Manager role group to assign the necessary permissions to legal investigators so they can manage the end-to-end workflow in Advanced eDiscovery.</span></span> <span data-ttu-id="37614-119">Como alternativa, puede crear grupos de roles personalizados con un subconjunto de las funciones necesarias para realizar determinadas acciones en un caso en eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="37614-119">Alternatively, you can create custom role groups with a subset of the roles necessary to perform certain actions in a case in Advanced eDiscovery.</span></span> <span data-ttu-id="37614-120">Para obtener más información sobre los roles relacionados con la exhibición de documentos electrónicos, vea [assign eDiscovery Permissions in the Security _AMP_ Compliance Center](../assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="37614-120">For more information about eDiscovery-related roles, see [Assign eDiscovery permissions in the Security & Compliance Center](../assign-ediscovery-permissions.md).</span></span>

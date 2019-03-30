---
title: Office 365 tratar con daños en los datos
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Una explicación de los datos dañados en Office 365 y los esfuerzos de prevención y recuperación de Microsoft.
ms.openlocfilehash: 9bf55243399ecd9f01f736e2da70d7c07231fa63
ms.sourcegitcommit: 1261a37c414111f869df5791548a768d853fda60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2019
ms.locfileid: "31004097"
---
# <a name="dealing-with-data-corruption-in-office-365"></a><span data-ttu-id="d8528-103">Tratar los daños en los datos en Office 365</span><span class="sxs-lookup"><span data-stu-id="d8528-103">Dealing with Data Corruption in Office 365</span></span>

<span data-ttu-id="d8528-104">Uno de los aspectos desafiantes de la ejecución de un servicio en la nube a gran escala es cómo controlar los daños en los datos, dado el gran volumen de datos y sistemas independientes.</span><span class="sxs-lookup"><span data-stu-id="d8528-104">One of the challenging aspects of running a large-scale cloud service is how to handle data corruption, given the large volume of data and independent systems.</span></span> <span data-ttu-id="d8528-105">Los daños en los datos pueden deberse a:</span><span class="sxs-lookup"><span data-stu-id="d8528-105">Data corruption can be caused by:</span></span>
- <span data-ttu-id="d8528-106">Errores de aplicaciones o de infraestructura, que dañan parte o todo el estado de la aplicación</span><span class="sxs-lookup"><span data-stu-id="d8528-106">Application or infrastructure bugs, corrupting some or all of the application state</span></span> 
- <span data-ttu-id="d8528-107">Problemas de hardware que producen datos perdidos o la incapacidad de leer datos</span><span class="sxs-lookup"><span data-stu-id="d8528-107">Hardware issues that result in lost data or an inability to read data</span></span> 
- <span data-ttu-id="d8528-108">Errores operativos humanos</span><span class="sxs-lookup"><span data-stu-id="d8528-108">Human operational errors</span></span> 
- <span data-ttu-id="d8528-109">Hackers malintencionados y empleados descontentos</span><span class="sxs-lookup"><span data-stu-id="d8528-109">Malicious hackers and disgruntled employees</span></span> 
- <span data-ttu-id="d8528-110">Incidentes en servicios externos que resultan en alguna pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="d8528-110">Incidents in external services that result in some loss of data</span></span> 

<span data-ttu-id="d8528-111">Debido a que una mayor resistencia en la integridad de los datos significa menos incidentes de corrupción de datos, Microsoft ha integrado en los mecanismos de protección de Office 365 para evitar que se produzcan daños, así como sistemas y procesos que nos permiten recuperar datos si es así.</span><span class="sxs-lookup"><span data-stu-id="d8528-111">Because greater resiliency in data integrity means fewer data corruption incidents, Microsoft has built into Office 365 protection mechanisms to prevent corruption from happening, as well as systems and processes that enable us to recover data if it does.</span></span> <span data-ttu-id="d8528-112">Las comprobaciones y procesos existen en las distintas fases del proceso de lanzamiento de ingeniería para aumentar la resistencia contra daños en los datos, entre los que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="d8528-112">Checks and processes exist within the various stages of the engineering release process to increase resiliency against data corruption, including:</span></span>
- <span data-ttu-id="d8528-113">Diseño del sistema</span><span class="sxs-lookup"><span data-stu-id="d8528-113">System Design</span></span>
- <span data-ttu-id="d8528-114">Estructura y organización del código</span><span class="sxs-lookup"><span data-stu-id="d8528-114">Code organization and structure</span></span> 
- <span data-ttu-id="d8528-115">Revisión de código</span><span class="sxs-lookup"><span data-stu-id="d8528-115">Code review</span></span> 
- <span data-ttu-id="d8528-116">Pruebas unitarias, pruebas de integración y pruebas del sistema</span><span class="sxs-lookup"><span data-stu-id="d8528-116">Unit tests, integration tests, and system tests</span></span>
- <span data-ttu-id="d8528-117">Pruebas/puertas de cables de viaje</span><span class="sxs-lookup"><span data-stu-id="d8528-117">Trip wires tests/gates</span></span> 

<span data-ttu-id="d8528-118">Dentro de los entornos de producción de Office 365, la replicación del mismo nivel entre centros de datos garantiza que siempre habrá varias copias activas de todos los datos.</span><span class="sxs-lookup"><span data-stu-id="d8528-118">Within Office 365 production environments, peer replication between datacenters ensures that there are always multiple live copies of any data.</span></span> <span data-ttu-id="d8528-119">Las imágenes y los scripts estándar se usan para recuperar los servidores perdidos y los datos replicados se usan para restaurar los datos del cliente.</span><span class="sxs-lookup"><span data-stu-id="d8528-119">Standard images and scripts are used to recover lost servers, and replicated data is used to restore customer data.</span></span> <span data-ttu-id="d8528-120">Debido a las comprobaciones y procesos integrados de resistencia de datos, Microsoft solo mantiene copias de seguridad de la documentación del sistema de información de Office 365 (incluida la documentación relacionada con la seguridad) mediante la replicación integrada en SharePoint Online y nuestro código interno Repository Tool, Source Depot.</span><span class="sxs-lookup"><span data-stu-id="d8528-120">Because of the built-in data resiliency checks and processes, Microsoft maintains backups only of Office 365 information system documentation (including security-related documentation), using built-in replication in SharePoint Online and our internal code repository tool, Source Depot.</span></span> <span data-ttu-id="d8528-121">La documentación del sistema se almacena en SharePoint Online y Source Depot contiene imágenes del sistema y de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d8528-121">System documentation is stored in SharePoint Online, and Source Depot contains system and application images.</span></span> <span data-ttu-id="d8528-122">SharePoint Online y Source Depot usan el control de versiones y se replican casi en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="d8528-122">Both SharePoint Online and Source Depot use versioning and are replicated in near real-time.</span></span> 
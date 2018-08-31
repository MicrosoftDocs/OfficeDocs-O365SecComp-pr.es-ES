---
title: Office 365 tratar con daños en los datos
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Una explicación de los daños en Office 365 y los esfuerzos de Microsoft de prevención y recuperación de datos.
ms.openlocfilehash: 087be23ce5dad1daf62357cb08e27c0a15962792
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536288"
---
# <a name="dealing-with-data-corruption-in-office-365"></a><span data-ttu-id="0e4e5-103">Tratar con daños en los datos en Office 365</span><span class="sxs-lookup"><span data-stu-id="0e4e5-103">Dealing with Data Corruption in Office 365</span></span>

<span data-ttu-id="0e4e5-p101">Uno de los aspectos difíciles de ejecutar un servicio de nube a gran escala es cómo controlar daños en los datos, dado el gran volumen de datos y sistemas independientes. Pueden deberse a daños en los datos:</span><span class="sxs-lookup"><span data-stu-id="0e4e5-p101">One of the challenging aspects of running a large-scale cloud service is how to handle data corruption, given the large volume of data and independent systems. Data corruption can be caused by:</span></span>
- <span data-ttu-id="0e4e5-106">Errores de aplicación o infraestructura, dañar todo o parte del estado de la aplicación</span><span class="sxs-lookup"><span data-stu-id="0e4e5-106">Application or infrastructure bugs, corrupting some or all of the application state</span></span> 
- <span data-ttu-id="0e4e5-107">Problemas de hardware que se crean en pérdida de datos o la imposibilidad de leer datos</span><span class="sxs-lookup"><span data-stu-id="0e4e5-107">Hardware issues that result in lost data or an inability to read data</span></span> 
- <span data-ttu-id="0e4e5-108">Errores operativos humanos</span><span class="sxs-lookup"><span data-stu-id="0e4e5-108">Human operational errors</span></span> 
- <span data-ttu-id="0e4e5-109">Los intrusos malintencionados y empleados descontentos</span><span class="sxs-lookup"><span data-stu-id="0e4e5-109">Malicious hackers and disgruntled employees</span></span> 
- <span data-ttu-id="0e4e5-110">Incidentes en los servicios externos que como resultado la pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="0e4e5-110">Incidents in external services that result in some loss of data</span></span> 

<span data-ttu-id="0e4e5-p102">Debido a que la mayor resistencia en la integridad de los datos significa menos incidentes de daños de datos, Microsoft ha integrado en Office 365 mecanismos de protección para evitar daños de ocurra, así como sistemas y procesos que nos permiten recuperar los datos si lo hace. Comprobaciones y procesos existen dentro de las distintas fases del proceso de lanzamiento de ingeniería para aumentar la resistencia contra daños en los datos, incluidos:</span><span class="sxs-lookup"><span data-stu-id="0e4e5-p102">Because greater resiliency in data integrity means fewer data corruption incidents, Microsoft has built into Office 365 protection mechanisms to prevent corruption from happening, as well as systems and processes that enable us to recover data if it does. Checks and processes exist within the various stages of the engineering release process to increase resiliency against data corruption, including:</span></span>
- <span data-ttu-id="0e4e5-113">Diseño del sistema</span><span class="sxs-lookup"><span data-stu-id="0e4e5-113">System Design</span></span>
- <span data-ttu-id="0e4e5-114">Organización de código y estructura</span><span class="sxs-lookup"><span data-stu-id="0e4e5-114">Code organization and structure</span></span> 
- <span data-ttu-id="0e4e5-115">Revisión de código</span><span class="sxs-lookup"><span data-stu-id="0e4e5-115">Code review</span></span> 
- <span data-ttu-id="0e4e5-116">Pruebas unitarias, pruebas de integración y pruebas del sistema</span><span class="sxs-lookup"><span data-stu-id="0e4e5-116">Unit tests, integration tests, and system tests</span></span>
- <span data-ttu-id="0e4e5-117">Ida y vuelta hilos/puertas de pruebas</span><span class="sxs-lookup"><span data-stu-id="0e4e5-117">Trip wires tests/gates</span></span> 

<span data-ttu-id="0e4e5-p103">Dentro de los entornos de producción de Office 365, la replicación del mismo nivel entre centros de datos garantiza que siempre hay varias copias live de todos los datos. Las secuencias de comandos e imágenes estándares se usan para recuperar servidores pierden y los datos duplicados se usan para restaurar los datos de cliente. Debido a las comprobaciones de resistencia de datos integrada y procesos, Microsoft mantiene las copias de seguridad sólo de la documentación de Office 365 información del sistema (incluida la documentación relacionada con la seguridad), de uso de la replicación integrada en SharePoint Online y nuestro código interno herramienta de repositorio, depósito de origen. Documentación del sistema se almacena en SharePoint Online y depósito de origen contiene las imágenes de sistema y de aplicación. SharePoint Online y depósito de origen, use el control de versiones y se replican en casi en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="0e4e5-p103">Within Office 365 production environments, peer replication between datacenters ensures that there are always multiple live copies of any data. Standard images and scripts are used to recover lost servers, and replicated data is used to restore customer data. Because of the built-in data resiliency checks and processes, Microsoft maintains backups only of Office 365 information system documentation (including security-related documentation), using built-in replication in SharePoint Online and our internal code repository tool, Source Depot. System documentation is stored in SharePoint Online, and Source Depot contains system and application images. Both SharePoint Online and Source Depot use versioning and are replicated in near real-time.</span></span> 
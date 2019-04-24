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
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262832"
---
# <a name="dealing-with-data-corruption-in-office-365"></a>Tratar los daños en los datos en Office 365

Uno de los aspectos desafiantes de la ejecución de un servicio en la nube a gran escala es cómo controlar los daños en los datos, dado el gran volumen de datos y sistemas independientes. Los daños en los datos pueden deberse a:
- Errores de aplicaciones o de infraestructura, que dañan parte o todo el estado de la aplicación 
- Problemas de hardware que producen datos perdidos o la incapacidad de leer datos 
- Errores operativos humanos 
- Hackers malintencionados y empleados descontentos 
- Incidentes en servicios externos que resultan en alguna pérdida de datos 

Debido a que una mayor resistencia en la integridad de los datos significa menos incidentes de corrupción de datos, Microsoft ha integrado en los mecanismos de protección de Office 365 para evitar que se produzcan daños, así como sistemas y procesos que nos permiten recuperar datos si es así. Las comprobaciones y procesos existen en las distintas fases del proceso de lanzamiento de ingeniería para aumentar la resistencia contra daños en los datos, entre los que se incluyen:
- Diseño del sistema
- Estructura y organización del código 
- Revisión de código 
- Pruebas unitarias, pruebas de integración y pruebas del sistema
- Pruebas/puertas de cables de viaje 

Dentro de los entornos de producción de Office 365, la replicación del mismo nivel entre centros de datos garantiza que siempre habrá varias copias activas de todos los datos. Las imágenes y los scripts estándar se usan para recuperar los servidores perdidos y los datos replicados se usan para restaurar los datos del cliente. Debido a las comprobaciones y procesos integrados de resistencia de datos, Microsoft solo mantiene copias de seguridad de la documentación del sistema de información de Office 365 (incluida la documentación relacionada con la seguridad) mediante la replicación integrada en SharePoint Online y nuestro código interno Repository Tool, Source Depot. La documentación del sistema se almacena en SharePoint Online y Source Depot contiene imágenes del sistema y de la aplicación. SharePoint Online y Source Depot usan el control de versiones y se replican casi en tiempo real. 
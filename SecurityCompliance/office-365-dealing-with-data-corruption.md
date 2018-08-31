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
# <a name="dealing-with-data-corruption-in-office-365"></a>Tratar con daños en los datos en Office 365

Uno de los aspectos difíciles de ejecutar un servicio de nube a gran escala es cómo controlar daños en los datos, dado el gran volumen de datos y sistemas independientes. Pueden deberse a daños en los datos:
- Errores de aplicación o infraestructura, dañar todo o parte del estado de la aplicación 
- Problemas de hardware que se crean en pérdida de datos o la imposibilidad de leer datos 
- Errores operativos humanos 
- Los intrusos malintencionados y empleados descontentos 
- Incidentes en los servicios externos que como resultado la pérdida de datos 

Debido a que la mayor resistencia en la integridad de los datos significa menos incidentes de daños de datos, Microsoft ha integrado en Office 365 mecanismos de protección para evitar daños de ocurra, así como sistemas y procesos que nos permiten recuperar los datos si lo hace. Comprobaciones y procesos existen dentro de las distintas fases del proceso de lanzamiento de ingeniería para aumentar la resistencia contra daños en los datos, incluidos:
- Diseño del sistema
- Organización de código y estructura 
- Revisión de código 
- Pruebas unitarias, pruebas de integración y pruebas del sistema
- Ida y vuelta hilos/puertas de pruebas 

Dentro de los entornos de producción de Office 365, la replicación del mismo nivel entre centros de datos garantiza que siempre hay varias copias live de todos los datos. Las secuencias de comandos e imágenes estándares se usan para recuperar servidores pierden y los datos duplicados se usan para restaurar los datos de cliente. Debido a las comprobaciones de resistencia de datos integrada y procesos, Microsoft mantiene las copias de seguridad sólo de la documentación de Office 365 información del sistema (incluida la documentación relacionada con la seguridad), de uso de la replicación integrada en SharePoint Online y nuestro código interno herramienta de repositorio, depósito de origen. Documentación del sistema se almacena en SharePoint Online y depósito de origen contiene las imágenes de sistema y de aplicación. SharePoint Online y depósito de origen, use el control de versiones y se replican en casi en tiempo real. 
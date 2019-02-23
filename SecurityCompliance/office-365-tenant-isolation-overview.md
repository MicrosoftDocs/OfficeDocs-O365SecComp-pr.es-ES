---
title: Aislamiento de inquilinos en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Un resumen de cómo Microsoft aplica el aislamiento de inquilino para Office 365.
ms.openlocfilehash: dceff3b73ac01d3e0422a190d450ee28f7fdfb27
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220280"
---
# <a name="tenant-isolation-in-office-365"></a>Aislamiento de inquilinos en Office 365

Una de las principales ventajas de la informática en la nube es el concepto de una infraestructura compartida común en numerosos clientes a la vez, lo que lleva a economías de escala. Este concepto se denomina *multiempresa*. Microsoft funciona continuamente para garantizar que las arquitecturas multiinquilinos de nuestros servicios en la nube admitan la seguridad de ámbito empresarial, la confidencialidad, la privacidad, la integridad y los estándares de disponibilidad.

Los servicios en la nube de Microsoft se han diseñado teniendo en cuenta las importantes inversiones y experiencias obtenidas de la [informática digna de confianza](https://www.microsoft.com/en-us/twc/default.aspx) y el [ciclo de vida de desarrollo de seguridad](http://www.microsoft.com/security/sdl/default.aspx), por la hipótesis de que todos los inquilinos son potencialmente hostiles para todos otros inquilinos y hemos implementado medidas de seguridad para evitar que las acciones de un inquilino afecten a la seguridad o el servicio de otro inquilino, u obtenga acceso al contenido de otro inquilino.

Los dos objetivos principales de mantener el aislamiento de inquilino en un entorno multiempresa son:
1.  Evitar la fuga o el acceso no autorizado a contenido de clientes entre inquilinos; y
2.  Evitar que las acciones de un inquilino afecten negativamente al servicio para otro espacio empresarial

Se han implementado varias formas de protección a través de Office 365 para evitar que los clientes pongan en peligro los servicios o las aplicaciones de Office 365 o que obtengan acceso no autorizado a la información de otros inquilinos o del sistema Office 365, incluidos:
- El aislamiento lógico del contenido del cliente dentro de cada inquilino para los servicios de Office 365 se logra a través de la autorización de Azure Active Directory y el control de acceso basado en roles.
- SharePoint Online proporciona mecanismos de aislamiento de datos en el nivel de almacenamiento.
- Microsoft usa una rigurosa seguridad física, detección en segundo plano y una estrategia de cifrado de varias capas para proteger la confidencialidad y la integridad del contenido del cliente. Todos los centros de recursos de Office 365 tienen controles de acceso biométricos, con la mayoría de los que requieren impresiones de Palm para obtener acceso físico. Además, todos los empleados de Microsoft en Estados Unidos deben realizar correctamente una comprobación de antecedentes estándar como parte del proceso de contratación. Para obtener más información acerca de los controles usados para el acceso administrativo en Office 365, consulte [office 365 Administrative Access Controls](office-365-administrative-access-controls-overview.md).
- Office 365 usa tecnologías de servicio que cifran el contenido del cliente en reposo y en tránsito, incluidos BitLocker, el cifrado por archivo, la seguridad de la capa de transporte (TLS) y el protocolo de seguridad de Internet (IPsec). Para obtener información específica sobre el cifrado en Office 365, consulte [tecnologías de cifrado de datos en office 365](office-365-encryption-in-the-microsoft-cloud-overview.md).

Juntas, las protecciones de la lista anterior proporcionan controles sólidos de aislamiento lógico que proporcionan protección contra amenazas y mitigación equivalente a la que proporciona el aislamiento físico por sí solo.

## <a name="related-links"></a>Vínculos relacionados
- [Aislamiento y Control de acceso en Azure Active Directory](office-365-isolation-in-azure-active-directory.md)
- [Aislamiento del inquilino en Office Graph y Delve](office-365-isolation-in-graph-and-delve.md)
- [Aislamiento de inquilino en búsqueda de Office 365](office-365-isolation-in-office-365-search.md)
- [Aislamiento del inquilino en Office 365 Video](office-365-isolation-in-office-365-video.md)
- [Límites de recursos](office-365-resource-limits.md)
- [Supervisar y probar los límites de inquilinos](office-365-monitoring-and-testing.md)
- [Aislamiento y Control de acceso en Office 365](office-365-isolation-in-office-365.md)
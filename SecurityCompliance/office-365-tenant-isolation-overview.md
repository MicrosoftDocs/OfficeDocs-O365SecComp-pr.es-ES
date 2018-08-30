---
title: Aislamiento de inquilinos en Office 365
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
description: Un resumen de cómo Microsoft aplica el aislamiento de inquilinos para Office 365.
ms.openlocfilehash: fcf66ee65c2a4cfdf73ae0eac77f54bd555d059d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536259"
---
# <a name="tenant-isolation-in-office-365"></a>Aislamiento de inquilinos en Office 365

Una de las principales ventajas de cloud computing es el concepto de una infraestructura compartida común a través de numerosos clientes simultáneamente, lo que lleva a economías de escala. Este concepto se denomina *multiempresa*. Microsoft trabaja continuamente para asegurarse de que las arquitecturas de varios inquilinos de nuestros servicios de nube compatible con los estándares de seguridad, confidencialidad, privacidad, integridad y disponibilidad de nivel de empresa.

En función de las inversiones significativas y la experiencia obtenida con [Trustworthy Computing](https://www.microsoft.com/en-us/twc/default.aspx) y el [Ciclo de vida de desarrollo de seguridad](http://www.microsoft.com/security/sdl/default.aspx), se diseñaron con la suposición de que todos los inquilinos son potencialmente adversas para todos los servicios de nube de Microsoft otros inquilinos y nos hemos implementado medidas de seguridad para evitar que las acciones de un inquilino desde que afectan a la seguridad o el servicio de otro inquilino o acceso al contenido de otro inquilino.

Los dos objetivos principales de mantenimiento de aislamiento de inquilinos en un entorno de varios inquilino son:
1.  Impide la fuga de o acceso no autorizado a contenido de cliente en inquilinos; y
2.  Evitar que las acciones de un inquilino de afectar negativamente el servicio para otro inquilino

Se han implementado varias formas de protección en todo Office 365 para evitar que a los clientes de servicios de Office 365 comprometer o aplicaciones o para obtener acceso no autorizado a la información de otros inquilinos o del sistema de Office 365 propiamente dicha, incluidos:
- Aislamiento lógico de contenido de cliente dentro de cada inquilino para servicios de Office 365 se consigue a través de autorización de Azure Active Directory y control de acceso basado en roles.
- SharePoint Online proporciona mecanismos de aislamiento de datos en el nivel de almacenamiento.
- Microsoft utiliza seguridad física riguroso, el filtrado de fondo y una estrategia de varios niveles de cifrado para proteger la confidencialidad y la integridad del contenido del cliente. Todos los centros de datos de Office 365 tienen controles de acceso biométrica, con más si se requiere imprime mano tener acceso físico. Además, los empleados de Microsoft en todos los Estados Unidos están necesario para completar correctamente una comprobación de fondo estándar como parte del proceso de contratación. Para obtener más información sobre los controles utilizados para el acceso administrativo en Office 365, vea [Controles de acceso administrativo de Office 365](office-365-administrative-access-controls-overview.md).
- Office 365 usa tecnologías del servicio que cifrar el contenido del cliente en reposo y en tránsito, incluidos BitLocker, cifrado por archivo, seguridad de capa de transporte (TLS) y protocolo de seguridad de Internet (IPsec). Para obtener información específica acerca del cifrado en Office 365, vea [Tecnologías de cifrado de datos en Office 365](office-365-encryption-in-the-microsoft-cloud-overview.md).

Juntos, las protecciones citadas proporcionan controles de aislamiento lógico eficaz que proporcionan protección contra amenazas y mitigación equivalente a la que proporcionado por el aislamiento físico por sí solo.

## <a name="related-links"></a>Vínculos relacionados
- [Aislamiento y Control de acceso en Azure Active Directory](office-365-isolation-in-azure-active-directory.md)
- [Inquilino aislamiento en Office Graph y Delve](office-365-isolation-in-graph-and-delve.md)
- [Aislamiento de inquilino en búsqueda de Office 365](office-365-isolation-in-office-365-search.md)
- [Aislamiento del inquilino en Office 365 Video](office-365-isolation-in-office-365-video.md)
- [Límites de recursos](office-365-resource-limits.md)
- [Supervisar y probar los límites de inquilinos](office-365-monitoring-and-testing.md)
- [Aislamiento y Control de acceso en Office 365](office-365-isolation-in-office-365.md)
---
title: Controles de aislamiento de Office 365
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
description: 'Resumen: una explicación de los controles de aislamiento en Office 365.'
ms.openlocfilehash: 6f5980ae25b412cbbccc20ec3b5726b5a4ceed86
ms.sourcegitcommit: 7b5e4a7a51f3cdd741deb77a2d60a18e2316618d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/01/2019
ms.locfileid: "33520690"
---
# <a name="office-365-isolation-controls"></a>Controles de aislamiento de Office 365 

Microsoft funciona continuamente para garantizar que la arquitectura multiempresa de Office 365 admite la seguridad de nivel empresarial, la confidencialidad, la privacidad, la integridad, los [estándares](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)locales, internacionales y de disponibilidad. La escala y el alcance de los servicios proporcionados por Microsoft hacen que sea difícil y no económico administrar Office 365 con una interacción humana importante. Los servicios de Office 365 se proporcionan a través de varios centros de datos distribuidos globalmente, cada uno de ellos muy automatizado, con pocas operaciones que requieran un toque humano o cualquier acceso al contenido del cliente. Nuestro personal es compatible con estos servicios y centros de datos mediante herramientas automatizadas y acceso remoto extremadamente seguro. Para ver algunos detalles sobre cómo se operan los servicios a gran escala en Office 365, [mire a segundo plano en office 365 para profesionales de ti](https://channel9.msdn.com/Events/SharePoint-Conference/2014/SPC202).

Office 365 está formado por varios servicios que proporcionan una funcionalidad empresarial importante y contribuyen a la experiencia completa de Office 365. Cada uno de estos servicios es independiente y está diseñado para integrarse entre sí.

Office 365 está diseñado con los siguientes principios:

 - ** [Arquitectura orientada a servicios](https://msdn.microsoft.com/library/aa480021.aspx):** diseño y desarrollo de software en forma de servicios interoperables que proporcionan una funcionalidad empresarial bien definida.
 - **[Garantía de seguridad operativa](http://www.microsoft.com/download/details.aspx?id=40872):** un marco que incorpora la información obtenida a través de diversas funciones exclusivas de Microsoft, incluido el [ciclo de vida de desarrollo de seguridad](https://www.microsoft.com/sdl/default.aspx)de Microsoft, la seguridad de [Microsoft Centro de respuesta](https://technet.microsoft.com/library/dn440717.aspx)y conocimiento profundo del panorama de la amenaza de Cybersecurity.

Los servicios de Office 365 interoperan entre sí, pero se diseñan e implementan para que se puedan implementar y operar como servicios autónomos, independientes entre sí. Microsoft segrega los deberes y las áreas de responsabilidad de Office 365 para reducir las oportunidades de modificación no autorizada o accidental o un mal uso de los activos de la organización. Office 365 Teams tienen roles definidos como parte de un mecanismo completo de control de acceso basado en roles.

## <a name="customer-content-isolation"></a>Aislamiento de contenido de cliente

Todo el contenido de los clientes de un espacio empresarial se aísla de los otros inquilinos y de los datos de operaciones y sistemas usados en la administración de Office 365. Se implementan varias formas de protección a través de Office 365 para minimizar el riesgo de poner en peligro cualquier aplicación o servicio de Office 365. Varias formas de protección también evitan el acceso no autorizado a la información de los inquilinos o del propio sistema Office 365.

Para obtener información sobre cómo Microsoft implementa el aislamiento lógico de los datos de inquilino en Office 365, vea [aislamiento de inquilinos en office 365](office-365-tenant-isolation-overview.md).

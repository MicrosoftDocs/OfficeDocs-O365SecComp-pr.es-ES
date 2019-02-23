---
title: Controles de aislamiento de Office 365
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
description: 'Resumen: una explicación de los controles de aislamiento en Office 365.'
ms.openlocfilehash: a6ff2b11ea02334a6c47317cbb77b8d47207b552
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217320"
---
# <a name="office-365-isolation-controls"></a>Controles de aislamiento de Office 365 

Microsoft funciona continuamente para garantizar que la arquitectura multiempresa de Office 365 admite la seguridad de nivel empresarial, la confidencialidad, la privacidad, la integridad y los [estándares](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)de disponibilidad, así como los estándares locales e internacionales. Teniendo en cuentan la escala y el alcance de los servicios proporcionados por Microsoft, sería difícil y no económico administrar Office 365 si se necesitara una interacción humana importante. Los servicios de Office 365 se proporcionan a través de varios centros de datos distribuidos de forma global, en un modo altamente automatizado, donde muy pocas operaciones del centro de datos requieren un toque humano e incluso menos operaciones requieren acceso al contenido del cliente. Nuestro personal es compatible con estos servicios y centros de datos con herramientas automatizadas y acceso remoto extremadamente seguro. Para ver algunos detalles sobre cómo se operan los servicios a gran escala en Office 365, [mire a segundo plano en office 365 para profesionales de ti](https://channel9.msdn.com/Events/SharePoint-Conference/2014/SPC202).

Office 365 está formado por varios servicios que proporcionan una funcionalidad empresarial importante y contribuyen a la experiencia completa de Office 365. Cada uno de estos servicios está diseñado para ser independiente e integrarse entre sí. Office 365 está diseñado con los principios de una [arquitectura orientada a servicios](https://msdn.microsoft.com/library/aa480021.aspx), que se define como el diseño y desarrollo de software en forma de servicios interoperables que proporcionan una funcionalidad empresarial bien definida y [seguridad operativa. Assurance](http://www.microsoft.com/download/details.aspx?id=40872), un marco que incorpora los conocimientos adquiridos a través de una amplia variedad de funciones exclusivas de Microsoft, como el [ciclo de vida de desarrollo de seguridad](https://www.microsoft.com/sdl/default.aspx)de Microsoft, el centro de respuesta de seguridad de [Microsoft](https://technet.microsoft.com/library/dn440717.aspx)y Deep conciencia del panorama de la amenaza de Cybersecurity.

Los servicios de Office 365 interoperan entre sí, pero están diseñados e implementados para que se puedan implementar y operar como servicios autónomos, independientes entre sí. Microsoft segrega los deberes y las áreas de responsabilidad de Office 365 para reducir las oportunidades de modificación no autorizada o accidental o un mal uso de los activos de la organización. Office 365 Teams tienen roles definidos como parte de un mecanismo completo de control de acceso basado en roles.

## <a name="customer-content-isolation"></a>Aislamiento de contenido de cliente
Todo el contenido del cliente que pertenece a un inquilino se aísla de otros inquilinos y de las operaciones y los datos de sistema usados en la administración de Office 365. Se han implementado varias formas de protección a través de Office 365 para minimizar el riesgo de poner en peligro cualquier aplicación o servicio de Office 365, o cualquier obtención de acceso no autorizado a la información de los inquilinos o del sistema Office 365. Para obtener información sobre cómo Microsoft implementa el aislamiento lógico de los datos de inquilino en Office 365, vea [aislamiento de inquilinos en office 365](office-365-tenant-isolation-overview.md).

---
title: Controles de aislamiento de Office 365
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
description: 'Resumen: Una explicación de los controles de aislamiento dentro de Office 365.'
ms.openlocfilehash: 3a5c06d0675a4503d9f5e5edd58535688fb9180a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536856"
---
# <a name="office-365-isolation-controls"></a>Controles de aislamiento de Office 365 

Microsoft trabaja continuamente para asegurarse de que la arquitectura multiempresa de Office 365 admite la seguridad de nivel de empresa, confidencialidad, disponibilidad, integridad y privacidad de [los estándares](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons), así como los estándares locales e internacionales. Dado que la escala y el ámbito de los servicios proporcionados por Microsoft, sería difícil y que no sean económicas para administrar Office 365 si la interacción humana significativa eran necesaria. Servicios de Office 365 se proporcionan a través de varios distribuida globalmente centros de datos, de una manera altamente automatizado, donde muy pocas operaciones de centro de datos requieren un toque humano, y operaciones incluso menos requieren acceso al contenido del cliente. Nuestro personal es compatible con estos servicios y centros de datos mediante herramientas automatizadas y acceso remoto de alta seguridad. Para algunos de los detalles acerca de cómo se utilizan servicios a gran escala en Office 365, vea [una mirada en segundo plano en Office 365 para profesionales de TI](https://channel9.msdn.com/Events/SharePoint-Conference/2014/SPC202).

Office 365 está formado por varios servicios que proporcionan la funcionalidad de importantes para el negocio y contribuyan a toda la experiencia de Office 365. Cada uno de estos servicios está diseñado para ser autónomos y para integrar con entre sí. Office 365 está diseñada con los principios de una [Arquitectura orientada a servicios](https://msdn.microsoft.com/library/aa480021.aspx), que se define como el diseño y desarrollo de software en forma de servicios interoperables que proporciona funcionalidad de negocio bien definidos y [seguridad operativa Assurance](http://www.microsoft.com/download/details.aspx?id=40872), un marco de trabajo que incorpore el conocimiento obtenido a través de una variedad de funcionalidades que son exclusivas de Microsoft, incluidos el [Ciclo de vida de desarrollo de seguridad](https://www.microsoft.com/sdl/default.aspx)de Microsoft, el [Centro de respuestas de seguridad de Microsoft](https://technet.microsoft.com/library/dn440717.aspx)y análisis conocimiento de las amenazas de la ciberseguridad.

Servicios de Office 365 interoperan entre sí, pero están diseñados e implementados por lo que puede ser implementados y que se emplean como servicios autónomos, independientes entre sí. Microsoft aísla los derechos y las áreas de responsabilidad para Office 365 reducir las oportunidades para su modificación no autorizado o no intencionado o mal uso de los activos de la organización. Equipos de Office 365 han definido funciones como parte de un mecanismo de control de acceso basado en roles completa.

## <a name="customer-content-isolation"></a>Aislamiento del contenido del cliente
Todo el contenido del cliente que pertenecen a un inquilino se aísla de otros inquilinos y de los datos de las operaciones y los sistemas usados en la administración de Office 365. Se han implementado varias formas de protección en todo Office 365 a fin de minimizar el riesgo de compromiso de cualquier servicio de Office 365 o una aplicación o cualquier obtención de acceso no autorizado a la información de los inquilinos o el propio sistema de Office 365. Para obtener información acerca de cómo Microsoft implementa el aislamiento lógico de datos de inquilinos dentro de Office 365, vea [Aislamiento de inquilinos en Office 365](office-365-tenant-isolation-overview.md).

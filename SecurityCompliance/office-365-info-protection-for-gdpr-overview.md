---
title: Información general de Information Protection de Office 365 para RGPD
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Obtenga información general de Office 365 Information Protection para RGPD. Aprenda a descubrir, clasificar, proteger y vigilar los datos personales.
ms.openlocfilehash: 5f10b8c19a2a0d3fe5ace8bcfe8cf6f64c30308f
ms.sourcegitcommit: 15983a08a4ae9c2050344172c7e957830ce3867e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2019
ms.locfileid: "30373861"
---
# <a name="overview-of-office-365-information-protection-for-gdpr"></a>Información general de Information Protection de Office 365 para RGPD

Esta solución muestra cómo proteger datos confidenciales que se almacenan en servicios de Office 365. Incluye recomendaciones para descubrir, clasificar, proteger y supervisar datos personales. Esta solución usa el Reglamento general de protección de datos (RGPD) como ejemplo, pero se puede aplicar el mismo proceso para lograr el cumplimiento con muchas otras normativas.

RGPD regula la recopilación, el almacenamiento, el procesamiento y el uso compartido de datos personales. Los datos personales se definen muy globalmente en el RGPD como los datos que se refieren a una persona física identificada o identificable que reside de la Unión Europea (UE).

Artículo 4: definiciones

> “datos personales” se refiere a cualquier información sobre una persona física identificada o identificable (“interesado”); una persona identificable natural es una que puede identificarse, directa o indirectamente, especialmente con referencia a un identificador, con un nombre, un número de identificación, datos de ubicación, un identificador en línea o uno o más elementos específicos físicos, fisiológicos, genéticos, mentales, económicos, culturales o de identidad social de esa persona natural;

Esta solución está pensada para ayudar a las organizaciones a descubrir y proteger los datos personales en Office 365 que podrían estar sujetos al RGPD. No se ofrece como una certificación de cumplimiento RGPD. Las organizaciones son responsables del cumplimiento de su propio RGPD y se recomienda que consulten a los equipos legales y de cumplimiento o busquen asesoramiento de terceros especializados en cumplimiento.

[Evaluación de RGPD](https://assessment.microsoft.com/gdpr-compliance) es una herramienta de autoevaluación rápida y en línea disponible sin costo para ayudar a su organización a revisar su nivel de preparación para cumplir con el RGPD general (<http://aka.ms/gdprassessment>).

## <a name="assess-and-manage-your-compliance-risk"></a>Evaluar y administrar los riesgos de cumplimiento

El primer paso para el cumplimiento de RGPD es evaluar si el RGPD se aplica a su organización y, si es así, en qué medida. Este análisis incluye comprender los datos de los procesos de su organización y dónde se encuentran.

### <a name="step-1--use-compliance-manager-to-view-the-regulation-requirements-and-track-your-progress"></a>Paso 1: Usar el Administrador de cumplimiento para ver los requisitos de regulación y realizar un seguimiento del progreso

El Administrador de cumplimiento proporciona herramientas para realizar un seguimiento, implementar y administrar los controles de auditoría para ayudar a su organización a lograr el cumplimiento con varios estándares, incluido el RGPD.

![Usar el Administrador de cumplimiento para ver los requisitos y seguir el progreso](Media/Overview-image1.png)

Para obtener más información, consulte [Usar el Administrador de cumplimiento en el Portal de confianza de servicios](https://support.office.com/es-ES/article/Use-Compliance-Manager-in-the-Service-Trust-Portal-Preview-5756d342-5af9-4496-82e8-4dd50fa39942). 

### <a name="step-2--use-content-search-and-sensitive-information-types-to-find-personal-data"></a>Paso 2: Usar la Búsqueda de contenido y los tipos de información confidencial para buscar datos personales 

Descubra los datos personales en su entorno sujetos a la RGPD. Use la Búsqueda de contenido con tipos de información confidencial para:

-   Buscar e informar sobre la ubicación de datos personales.

-   Optimizar los tipos de datos confidenciales y otras consultas para encontrar todos los datos personales en su entorno.

![Usar la Búsqueda de contenido y los tipos de información confidencial para buscar datos personales](Media/Overview-image2.png)

Los tipos de información confidencial definen cómo el proceso automatizado reconoce tipos específicos de información como números de tarjeta de crédito y números de estado del servicio. Este artículo contiene un conjunto que puede usar como punto de partida. Pronto habrá muchos más tipos de información confidencial datos personales en los países de la UE.

Para obtener más información, consulte [Buscar y encontrar datos personales](search-for-and-find-personal-data.md). 

## <a name="classify-protect-and-monitor-personal-data-in-office-365-and-other-saas-apps"></a>Clasificar, proteger y vigilar los datos personales en Office 365 y otras aplicaciones SaaS

Algunas de las funciones que se usan para la protección de información en Office 365 también pueden usarse para proteger datos confidenciales de otras aplicaciones SaaS.

![Clasificar, proteger y vigilar datos personales](Media/Overview-image3.png)

Esta ilustración se describe con el resto en esta sección (los pasos 3 a 5).

### <a name="step-3--decide-if-you-want-to-use-labels-in-addition-to-sensitive-information-types"></a>Paso 3: Elegir si desea usar etiquetas además de los tipos de información confidencial

Los tipos de información confidencial son una forma de clasificación. Consulte [Diseñar un esquema de clasificación de datos personales](architect-a-classification-schema-for-personal-data.md), para decidir si también desea implementar etiquetas. Para aplicar etiquetas, consulte [Aplicar etiquetas a los datos personales de Office 365](apply-labels-to-personal-data-in-office-365.md).

En la ilustración, las etiquetas y los tipos de información confidencial funcionan en Office 365. Próximamente, podrá usarlos con Cloud App Security para buscar datos confidenciales en otras aplicaciones SaaS como Box y Salesforce.

### <a name="step-4--protect-personal-data-in-office-365"></a>Paso 4: Proteger datos personales en Office 365 

La protección de datos personales empieza con la prevención de pérdida de datos de Office 365. Hay varias otras funciones que se recomiendan para proteger el acceso a datos personales, como el cifrado de mensajes de Office 365 para el correo electrónico.

Estas protecciones pueden enfocarse a conjuntos de datos específicos:

-   Permisos de bibliotecas y sitios

-   Directivas de uso compartido externo de nivel de sitio

-   Directivas de acceso a dispositivos de nivel de sitio

La protección de acceso a Office 365 y otros servicios de nube incluye:

-   Protección de acceso a dispositivo e identidad en Enterprise Mobility + Security (EMS)

-   Privileged Access Management

-   Funciones de seguridad de Windows 10

Para obtener más información sobre cómo aplicar protección, consulte [Aplicar la protección de datos personales en Office 365](apply-protection-to-personal-data-in-office-365.md).

### <a name="step-5--monitor-for-leaks-of-personal-data"></a>Paso 5: Supervisar pérdidas de datos personales

Los informes de prevención de pérdida de datos de Office 365 proporcionan el mayor nivel de detalle para supervisar datos confidenciales. Puede configurar alertas automatizadas e investigar infracciones mediante el registro de auditoría de Office 365. Cloud App Security extiende la capacidad de buscar y supervisar datos confidenciales a otros proveedores de SaaS. Para obtener más información sobre estas herramientas, consulte [Supervisar infracciones de datos personales](monitor-for-leaks-of-personal-data.md).

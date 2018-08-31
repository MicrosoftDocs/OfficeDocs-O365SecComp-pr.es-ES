---
title: Introducción a las directivas de administración de información
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/16/2014
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- WSU150
- SPO160
- OSU150
- MET150
ms.assetid: 63a0b501-ba59-44b7-a35c-999f3be057b2
description: Una directiva de administración de información es un conjunto de reglas para un tipo de contenido. Información de directivas de administración permiten a las organizaciones al control y realizar un seguimiento de cosas como ¿durante cuánto tiempo se conserva el contenido o qué acciones que los usuarios puede realizar con dicho contenido. Directivas de administración de información pueden ayudar a las organizaciones a cumplir las reglamentaciones gubernamentales o legales, o simplemente pueden aplicar procesos empresariales internos.
ms.openlocfilehash: 9ec64cd7e015acc6a7d8da324ba18cf74405cc71
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536092"
---
# <a name="introduction-to-information-management-policies"></a>Introducción a las directivas de administración de información

Una directiva de administración de información es un conjunto de reglas para un tipo de contenido. Información de directivas de administración permiten a las organizaciones al control y realizar un seguimiento de cosas como ¿durante cuánto tiempo se conserva el contenido o qué acciones que los usuarios puede realizar con dicho contenido. Directivas de administración de información pueden ayudar a las organizaciones a cumplir las reglamentaciones gubernamentales o legales, o simplemente pueden aplicar procesos empresariales internos. 
  
Por ejemplo, una organización que debe seguir las regulaciones gubernamentales que requieren que demuestre "controles adecuados" de los resúmenes financieros podría crear información de uno o más directivas de administración que se auditen acciones específicas en la creación y proceso de aprobación de todos los documentos relacionados con archivos financieros.
  
Para obtener información sobre procedimientos, consulte [crear y aplicar directivas de administración de información](create-info-mgmt-policies.md).
  
## <a name="features-of-information-management-policies"></a>Características de directivas de administración de información
<a name="__top"> </a>

Hay cuatro categorías básicas de características de directiva predefinidas que las organizaciones pueden utilizar individualmente o en combinación para administrar contenido y los procesos. 
  
![Tipos de directivas de contenido](media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
La característica de directiva de auditoría ayuda a las organizaciones a analizar cómo se usan los sistemas de administración de contenido mediante el registro de eventos y operaciones que se realizan en documentos y elementos de lista. Puede configurar la característica de directiva de auditoría para registrar eventos, como cuando se edita un documento o elemento, ver, proteger, desprotegido, eliminados, o se cambian sus permisos. Toda la información de auditoría se almacena en un solo registro de auditoría en el servidor, y los administradores de sitios pueden ejecutar informes en él. 
  
La característica de directiva de caducidad ayuda a las organizaciones a eliminar o quitar el contenido obsoleto de sus sitios de forma trazable. Esto ayuda a administrar el costo y los riesgos asociados con la retención de contenido obsoleto. Puede configurar una directiva de caducidad para especificar que ciertos tipos de contenido caducan en una fecha determinada o dentro de un período de tiempo después de que el documento se creó o modificó por última vez.
  
Las organizaciones también pueden crear e implementar características de directiva personalizadas para satisfacer necesidades específicas. Por ejemplo, una organización de fabricación es posible que desee definir una directiva de administración de información para todos los documentos de especificación de diseño de productos de borrador que impide a los usuarios impriman copias de estos documentos en impresoras no seguras. Para definir este tipo de directiva de administración de información, puede crear e implementar una característica de directiva de restricción de impresión que puede agregarse a la directiva de administración de información relevante para el tipo de contenido de especificación de diseño del producto.
  
## <a name="locations-to-use-an-information-management-policy"></a>Ubicaciones para usar una directiva de administración de información
<a name="__toc340213528"> </a>

Para implementar una directiva de administración de información, debe agregarlo a una lista, biblioteca o tipo de contenido en un sitio. La ubicación donde crear o agregar una directiva de administración de información afecta a la amplitud se aplica la directiva o ampliamente cómo puede usarse. Puedes:
  
 **Crear una directiva de colección de sitios y, a continuación, agregue esta directiva para un tipo de contenido, la lista o la biblioteca** Puede crear una directiva de colección de sitios de la lista de directivas en el sitio de nivel superior de una colección de sitios. Después de crear una directiva de colección de sitios, se puede exportar para que los administradores de otras colecciones de sitios pueden importarlo a su lista de directivas. Creación de una directiva de colección de sitios exportable permite estandarizar las directivas de administración de información a través de los sitios de la organización. 
  
Al agregar una directiva de colección de sitios a un tipo de contenido de sitio, y se agrega una instancia de ese tipo de contenido de sitio a una lista o biblioteca, el propietario de dicha lista o biblioteca no puede modificar la directiva de colección de sitios para la lista o biblioteca. Adición de una directiva de colección de sitios a un tipo de contenido de sitio es una buena forma de garantizar directivas de colección de ese sitio se aplican en cada nivel de la jerarquía de sitios.
  
![Vínculo de plantilla de directiva de tipo de contenido en la página Configuración del sitio](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
 **Crear una directiva de administración de información para un tipo de contenido de sitio en la Galería de tipos de contenido de sitio del sitio de nivel superior y, a continuación, agregar ese tipo de contenido a una o varias listas o bibliotecas** Puede crear también una directiva de administración de información directamente para un tipo de contenido de sitio y, a continuación, asociar una instancia de ese tipo de contenido de sitio a varias listas o bibliotecas. Si crea una directiva de administración de la información de este modo, todos los elementos de la colección de sitios de ese tipo de contenido o un tipo de contenido que herede de ese tipo de contenido tiene la directiva. Sin embargo, si crea una directiva de administración de información directamente para un tipo de contenido de sitio, es más difícil volver a usar esta directiva de administración de información en otras colecciones de sitios, debido a que no se puede exportar las directivas que se crean de este modo. 
  
![Vínculo de tipos de contenido de sitio en la página Configuración del sitio](media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
![Vínculo de directiva de administración de información en la página de configuración de un tipo de contenido de sitio](media/15d83a34-6c8f-4b6e-b6ee-e9b0a70cbb4b.png)
  
Nota para controlar qué directivas se utilizan en una colección de sitios, los administradores de colección de sitios pueden deshabilitar la capacidad de establecer características de directiva directamente en un tipo de contenido. Cuando esta restricción está en vigor, los usuarios que crean tipos de contenido están limitados a seleccionar las directivas de la lista de directivas de colección de sitios.
  
 **Crear una directiva de administración de información para una lista o biblioteca** Si su organización necesita aplicar una directiva de administración de información específica a un conjunto muy limitado de contenido, puede crear una directiva de administración de información que se aplica únicamente a una lista o biblioteca individual. Este método de creación de una directiva de administración de información es el menos flexible, debido a que la directiva se aplica únicamente a una ubicación, y no puede exportarse o reutilizarse para otras ubicaciones. Sin embargo, en ocasiones, es posible que necesita crear directivas de administración de información única con aplicabilidad limitada para solucionar situaciones específicas. 
  
![Vínculo de las directivas de administración de información en la página de configuración de biblioteca de documentos](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
Notas 
  
Puede crear una directiva de administración de información para una lista o biblioteca únicamente si esa lista o biblioteca no admite varios tipos de contenido. Si una lista o biblioteca admite varios tipos de contenido, debe definir una directiva de administración de información para cada tipo de contenido de lista individual que está asociado a esa lista o biblioteca. (Instancias de un tipo de contenido de sitio que están asociadas con una lista o biblioteca específicas se conocen como tipos de contenido de lista).
  
Para controlar qué directivas se utilizan en una colección de sitios, los administradores de colección de sitios pueden deshabilitar la capacidad de establecer características de directiva directamente en una lista o biblioteca. Cuando esta restricción está en vigor, los usuarios que administran listas o bibliotecas están limitados a seleccionar las directivas de la lista de directivas de colección de sitios.
  
[Una directiva de administración de información es un conjunto de reglas para un tipo de contenido. Información de directivas de administración permiten a las organizaciones al control y realizar un seguimiento de cosas como ¿durante cuánto tiempo se conserva el contenido o qué acciones que los usuarios puede realizar con dicho contenido. Directivas de administración de información pueden ayudar a las organizaciones a cumplir las reglamentaciones gubernamentales o legales, o simplemente pueden aplicar procesos empresariales internos. Por ejemplo, una organización que debe seguir las regulaciones gubernamentales que requieren que demuestre "controles adecuados" de los resúmenes financieros podría crear información de uno o más directivas de administración que se auditen acciones específicas en la creación y proceso de aprobación de todos los documentos relacionados con archivos financieros. Para obtener información sobre procedimientos, vea Crear y aplicar directivas de administración de información.](intro-to-info-mgmt-policies.md#__top)
  


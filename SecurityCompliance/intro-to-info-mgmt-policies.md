---
title: Introduction to information management policies (Introducción a las directivas de administración de la información)
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/16/2014
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- WSU150
- SPO160
- OSU150
- MET150
ms.assetid: 63a0b501-ba59-44b7-a35c-999f3be057b2
ms.collection:
- M365-security-compliance
description: Una directiva de administración de información es un conjunto de reglas para un tipo de contenido. Las directivas de administración de información permiten a las organizaciones controlar y hacer un seguimiento de cosas como cuánto tiempo se mantiene el contenido o qué acciones pueden realizar los usuarios con ese contenido. Las directivas de administración de información pueden ayudar a las organizaciones a cumplir normas legales o gubernamentales, o simplemente pueden forzar la aplicación de procesos empresariales internos.
ms.openlocfilehash: a19b773a8944fa29c06b29e1928cb88e96cf5a7f
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152612"
---
# <a name="introduction-to-information-management-policies"></a>Introduction to information management policies (Introducción a las directivas de administración de la información)

Una directiva de administración de información es un conjunto de reglas para un tipo de contenido. Las directivas de administración de información permiten a las organizaciones controlar y hacer un seguimiento de cosas como cuánto tiempo se mantiene el contenido o qué acciones pueden realizar los usuarios con ese contenido. Las directivas de administración de información pueden ayudar a las organizaciones a cumplir normas legales o gubernamentales, o simplemente pueden forzar la aplicación de procesos empresariales internos. 
  
Por ejemplo, una organización que debe seguir las regulaciones gubernamentales que requieren que demuestren "controles adecuados" de sus informes financieros puede crear una o varias directivas de administración de la información que auditen acciones específicas en la creación y proceso de aprobación para todos los documentos relacionados con los archivos financieros.
  
Para obtener información sobre procedimientos, vea [crear y aplicar directivas de administración de información](create-info-mgmt-policies.md).
  
## <a name="features-of-information-management-policies"></a>Características de las directivas de administración de la información
<a name="__top"> </a>

Hay cuatro categorías básicas de características de directiva predefinidas que las organizaciones pueden usar de forma individual o en combinación para administrar el contenido y los procesos. 
  
![Tipos de directivas de contenido](media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
La característica de directiva de auditoría ayuda a las organizaciones a analizar cómo se usan los sistemas de administración de contenido mediante el registro de eventos y operaciones que se realizan en documentos y elementos de lista. Puede configurar la característica de directiva de auditoría para registrar eventos como cuando un documento o elemento se modifica, se ve, se protege, se desprotege, se elimina o se modifica su permiso. Toda la información de auditoría se almacena en un único registro de auditoría en el servidor y los administradores del sitio pueden ejecutar informes en ella. 
  
La característica de directiva de expiración ayuda a las organizaciones a eliminar o quitar contenido obsoleto de sus sitios de forma coherente y de fácil seguimiento. Esto le ayuda a administrar el costo y el riesgo asociados con la retención de contenido no actualizado. Puede configurar una directiva de expiración para especificar que determinados tipos de contenido expiran en una fecha determinada o en un período de tiempo después de que el documento se haya creado o modificado por última vez.
  
Las organizaciones también pueden crear e implementar características de directivas personalizadas para satisfacer necesidades específicas. Por ejemplo, es posible que una organización de fabricación desee definir una directiva de administración de información para todos los borradores de documentos de especificación de diseño de producto que prohíbe a los usuarios imprimir copias de estos documentos en impresoras no seguras. Para definir este tipo de directiva de administración de la información, puede crear e implementar una característica de directiva de restricción de impresión que se puede Agregar a la Directiva de administración de la información pertinente para el tipo de contenido especificación de diseño de producto.
  
## <a name="locations-to-use-an-information-management-policy"></a>Ubicaciones para usar una directiva de administración de la información
<a name="__toc340213528"> </a>

Para implementar una directiva de administración de la información, debe agregarla a una lista, biblioteca o tipo de contenido en un sitio. La ubicación en la que se crea o agrega una directiva de administración de la información afecta a la amplitud con la que se aplica la Directiva o la frecuencia con que se puede usar. Puede:
  
 **Crear una directiva de colección de sitios y, a continuación, agregar esta directiva a un tipo de contenido, lista o biblioteca** Puede crear una directiva de colección de sitios en la lista de directivas en el sitio de nivel superior de una colección de sitios. Después de crear una directiva de colección de sitios, puede exportarla para que los administradores de otras colecciones de sitios puedan importarla en su lista de directivas. La creación de una directiva de colección de sitios que se puede exportar permite estandarizar las directivas de administración de la información en todos los sitios de la organización. 
  
Cuando se agrega una directiva de colección de sitios a un tipo de contenido de sitio y se agrega una instancia de ese tipo de contenido de sitio a una lista o biblioteca, el propietario de dicha lista o biblioteca no puede modificar la Directiva de colección de sitios de la lista o biblioteca. La adición de una directiva de colección de sitios a un tipo de contenido de sitio es una buena forma de garantizar que las directivas de la colección de sitios se aplican en todos los niveles de la jerarquía del sitio.
  
![Vínculo de plantilla de directiva de tipo de contenido en la página Configuración del sitio](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
 **Crear una directiva de administración de información para un tipo de contenido de sitio en la galería de tipos de contenido de sitio del sitio de nivel superior y, a continuación, agregar ese tipo de contenido a una o más listas o bibliotecas** También puede crear una directiva de administración de información directamente para un tipo de contenido de sitio y, a continuación, asociar una instancia de ese tipo de contenido de sitio con varias listas o bibliotecas. Si crea una directiva de administración de la información de esta manera, todos los elementos de la colección de sitios de ese tipo de contenido o de un tipo de contenido que hereden de ese tipo de contenido tienen la Directiva. Sin embargo, si crea una directiva de administración de información directamente para un tipo de contenido de sitio, es más difícil reutilizar esta directiva de administración de la información en otras colecciones de sitios, ya que las directivas que se crean de esta manera no se pueden exportar. 
  
![Vínculo tipos de contenido de sitio de la página Configuración del sitio](media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
![Vínculo de directiva de administración de información en la página de configuración de un tipo de contenido de sitio](media/15d83a34-6c8f-4b6e-b6ee-e9b0a70cbb4b.png)
  
Nota para controlar qué directivas se usan en una colección de sitios, los administradores de colecciones de sitios pueden deshabilitar la capacidad de establecer características de directiva directamente en un tipo de contenido. Cuando esta restricción está en vigor, los usuarios que crean tipos de contenido se limitan a seleccionar directivas de la lista de directivas de la colección de sitios.
  
 **Crear una directiva de administración de la información para una lista o biblioteca** Si su organización necesita aplicar una directiva de administración de la información específica a un conjunto muy limitado de contenido, puede crear una directiva de administración de la información que se aplique sólo a una lista o biblioteca individual. Este método de creación de una directiva de administración de la información es el menos flexible, ya que la Directiva se aplica únicamente a una ubicación y no se puede exportar ni volver a usar para otras ubicaciones. Sin embargo, a veces es posible que necesite crear directivas de administración de información únicas con aplicabilidad limitada para solucionar situaciones específicas. 
  
![Vínculo directivas de administración de la información en la página de configuración de la biblioteca de documentos](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
Notas 
  
Puede crear una directiva de administración de información para una lista o biblioteca sólo si dicha lista o biblioteca no admite varios tipos de contenido. Si una lista o biblioteca admite varios tipos de contenido, debe definir una directiva de administración de la información para cada tipo de contenido de lista individual asociado a esa lista o biblioteca. (Las instancias de un tipo de contenido de sitio que están asociadas a una lista o biblioteca específica se conocen como tipos de contenido de lista).
  
Para controlar las directivas que se usan en una colección de sitios, los administradores de colecciones de sitios pueden deshabilitar la capacidad de establecer características de directiva directamente en una lista o biblioteca. Cuando esta restricción está en vigor, los usuarios que administran listas o bibliotecas se limitan a seleccionar directivas de la lista de directivas de la colección de sitios.
  
[Una directiva de administración de la información es un conjunto de reglas para un tipo de contenido. Las directivas de administración de la información permiten a las organizaciones controlar y realizar un seguimiento de elementos como el tiempo que se conserva el contenido o qué acciones pueden realizar los usuarios con ese contenido. Las directivas de administración de la información pueden ayudar a las organizaciones a cumplir con las regulaciones legales o del gobierno, o pueden simplemente exigir procesos empresariales internos. Por ejemplo, una organización que debe seguir las regulaciones gubernamentales que requieren que demuestren "controles adecuados" de sus informes financieros puede crear una o varias directivas de administración de la información que auditen acciones específicas en la creación y proceso de aprobación para todos los documentos relacionados con los archivos financieros. Para obtener información sobre procedimientos, vea crear y aplicar directivas de administración de información.](intro-to-info-mgmt-policies.md#__top)
  


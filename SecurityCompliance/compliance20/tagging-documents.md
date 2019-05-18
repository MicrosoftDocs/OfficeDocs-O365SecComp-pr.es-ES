---
title: Etiquetar documentos en un conjunto de revisión
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: a3b588f4b8e24783cd0d7198ea995f0fd6c8ae3e
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154032"
---
# <a name="tag-documents-in-a-review-set"></a>Etiquetar documentos en un conjunto de revisión

La organización de contenido en un conjunto de revisión es importante para completar varios flujos de trabajo en el proceso de exhibición de documentos electrónicos. Esto incluye:

-  Selección de contenido innecesario

- Identificación del contenido relevante
 
-  Identificación de contenido que debe ser revisado por un experto o un abogado

Cuando expertos, abogados u otros usuarios revisan el contenido de un conjunto de revisión, se pueden capturar sus opiniones relacionadas con el contenido mediante el uso de etiquetas. Por ejemplo, si la intención es deseleccionar contenido innecesario, un usuario puede etiquetar documentos con una etiqueta como "sin respuesta". Una vez que se ha revisado y etiquetado el contenido, se puede crear una búsqueda de conjunto de revisión para excluir cualquier Contenido etiquetado como "sin respuesta", lo que elimina este contenido de los pasos siguientes en el flujo de trabajo de eDiscovery. El panel de etiquetas se puede personalizar para cada caso, de modo que las etiquetas puedan admitir el flujo de trabajo de revisión previsto.

## <a name="tag-types"></a>Tipos de etiquetas

La exhibición avanzada de documentos electrónicos proporciona dos tipos de etiquetas:

- **Etiquetas de opción única** : limita a los usuarios a seleccionar una sola etiqueta dentro de un grupo. Esto puede ser útil para asegurarse de que los usuarios no seleccionan etiquetas conflictivas como "receptivo" y "sin respuesta". 

- **Etiquetas de varias opciones** : permite a los usuarios seleccionar varias etiquetas dentro de un grupo.

## <a name="tag-structure"></a>Estructura de etiquetas

Además de los tipos de etiqueta, la estructura de las etiquetas que se organizan en el panel etiqueta se puede usar para que los documentos de etiquetado sean más intuitivos. Las etiquetas se agrupan por secciones. revisión Set Search admite la capacidad de buscar por etiqueta y por etiqueta. Esto significa que puede crear una búsqueda de conjunto de revisión para recuperar documentos etiquetados con cualquier etiqueta en una sección.

![Secciones de etiquetas en el panel etiqueta](../media/Tagtypes.png)

Las etiquetas se pueden organizar en mayor profundidad si se anidan dentro de una sección. Por ejemplo, si la intención es identificar y etiquetar contenido privilegiado, se puede usar la anidación para dejar claro que un usuario puede etiquetar un documento como "privilegiado" y seleccionar el tipo de privilegio comprobando la etiqueta anidada adecuada.

![Etiquetas anidadas dentro de una sección de etiqueta](../media/Nestingtags.png)

## <a name="applying-tags"></a>Aplicar etiquetas

Hay varias formas de aplicar una etiqueta al contenido.

### <a name="tagging-a-single-document"></a>Etiquetado de un solo documento

Al ver un documento en un conjunto de revisiones, puede mostrar las etiquetas que puede usar una revisión haciendo clic en **Panel de codificación**.

![Haga clic en el panel de etiquetas para mostrar el panel de etiquetas](../media/Singledoctag.png)

Esto le permitirá aplicar etiquetas al documento que se muestra en el visor.

### <a name="bulk-tagging"></a>Etiquetado masivo

La etiquetación en masa se puede realizar seleccionando varios archivos en la cuadrícula de resultados y, a continuación, usando las etiquetas en el **Panel de codificación** , de forma similar a la etiqueta de un único documento. Para realizar un etiquetado masivo, puede seleccionar las etiquetas dos veces; el primer clic aplicará la etiqueta y la segunda se asegurará de que la etiqueta se borre para todos los archivos seleccionados.

![Una captura de pantalla de una descripción de teléfono móvil generada automáticamente](../media/Bulktag.png)

> [!NOTE]
> Cuando se realiza un etiquetado masivo, el panel etiquetado muestra un recuento de archivos que se etiquetan para cada etiqueta del panel.

### <a name="tagging-in-other-review-panels"></a>Etiquetado en otros paneles de revisión

Al revisar los documentos, puede usar los otros paneles de revisión para revisar otras características de los documentos en la cuadrícula de resultados. Esto incluye la revisión de otros documentos relacionados, subprocesos de correo electrónico, Near duplicados y duplicados de hash. Por ejemplo, cuando se revisan documentos relacionados (mediante el panel revisión de **familia de documentos** ), puede reducir significativamente el tiempo de revisión mediante la etiquetación en masa de los documentos relacionados. Por ejemplo, si un mensaje de correo electrónico tiene varios datos adjuntos y desea asegurarse de que toda la familia se etiquete de forma coherente.

Por ejemplo, aquí se muestra cómo mostrar el **Panel de codificación** al usar el panel revisión de **familia de documentos** :

1. Con el panel revisión abierto para un documento seleccionado (por ejemplo, mostrando la lista de contenido relacionado en el panel revisión de **familia de documentos** , haga clic en **documentos de código** en la parte superior del panel revisión actual).

   El panel de codificación se muestra como una ventana emergente.

2. Elija una o más etiquetas para aplicar el documento seleccionado. 

3. Para etiquetar todos los documentos, seleccione todos los documentos en el panel de la **familia de documentos** , haga clic en **documentos de código**y, a continuación, elija las etiquetas que se aplicarán a toda la familia de documentos.

![Captura de pantalla de una descripción de post de medio social generada automáticamente](../media/Relatedtag.png)

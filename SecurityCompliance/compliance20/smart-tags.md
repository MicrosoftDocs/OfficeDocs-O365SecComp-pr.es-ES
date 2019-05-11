---
title: Configuración de etiquetas inteligentes para abogados-detección de privilegios de cliente en eDiscovery avanzado
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 721426f23aec862bcefbd13b8e61415dac3aeb27
ms.sourcegitcommit: aa8ea45d5854f8906714e0a407937585ec7993ad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2019
ms.locfileid: "33951709"
---
# <a name="set-up-smart-tags-for-ml-assisted-review-in-advanced-ediscovery"></a>Configurar etiquetas inteligentes para revisión asistida por ML en eDiscovery avanzado

Las capacidades de aprendizaje de máquina en eDiscovery avanzado están pensadas para facilitar el proceso de toma de decisiones en los documentos. Las etiquetas inteligentes son una forma de incorporar las funciones de aprendizaje de la máquina en donde se registran las decisiones: etiquetas y grupos de etiquetas. Cuando se crea un grupo de etiquetas inteligentes, las decisiones del modelo de los ML asignadas al grupo se mostrarán en línea con las etiquetas del grupo para ayudarle a ver la información en línea, donde el contexto es más lógico.

## <a name="how-to-set-up-a-smart-tag-group"></a>Cómo configurar un grupo de etiquetas inteligentes

1. En un conjunto de revisiones, vaya a **Manage View Set** -> **Manage Tags**.

2. Haga clic en la lista desplegable junto a **Agregar grupo de etiquetas** y seleccione **Agregar grupo de etiquetas inteligentes**.

3. Seleccione el modelo que desea asignar a este grupo. De este modo, se creará una sección de etiqueta y N etiquetas secundarias, donde N es el número de salidas posibles del modelo. Por ejemplo, el modelo de detección de privilegios de abogado-Client tiene dos posibles resultados-privileges y no privileged; al seleccionar este modelo se crearán dos etiquetas secundarias en el conjunto de revisión, cada una correspondiente a una de las posibles salidas.

4. Cambie el nombre del grupo de etiquetas y las etiquetas según su ajuste.

## <a name="how-to-use-a-smart-tag-group"></a>Cómo usar un grupo de etiquetas inteligentes

Al revisar un documento, los resultados del modelo se expondrán junto al valor de etiqueta correspondiente. Por ejemplo, si tiene un grupo de etiquetas inteligentes para la detección de privilegios de clientes de abogados y revisa un documento que el modelo ha decidido que es potencialmente privilegiado, verá el motivo por el que se encuentra junto a la etiqueta correspondiente. Es importante tener en cuenta que la etiqueta no se aplica automáticamente; para todas las necesidades, las etiquetas dentro de un grupo de etiquetas inteligentes actúan exactamente igual que las etiquetas normales, excepto que exponen los resultados del modelo junto a ellos cuando corresponda.
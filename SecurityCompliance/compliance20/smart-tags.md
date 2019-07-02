---
title: Configurar etiquetas inteligentes en la exhibición avanzada de documentos electrónicos
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
ROBOTS: NOINDEX, NOFOLLOW
description: Las etiquetas inteligentes le permiten aplicar las funciones de aprendizaje automático al revisar el contenido en un caso de exhibición avanzada de documentos electrónicos. Use los grupos de etiquetas inteligentes para mostrar los resultados de los modelos de detección de aprendizaje automático, como el modelo de privilegios de clientes de abogados.
ms.openlocfilehash: 68b558cc2282cc388387f8d61825b9ee569ff32a
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "34703833"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a>Configurar etiquetas inteligentes en la exhibición avanzada de documentos electrónicos

Las capacidades de machine learning (ML) en eDiscovery avanzado pueden ayudarle a que el proceso de toma de decisiones sea más eficaz al revisar los documentos de casos en un conjunto de revisión. Las etiquetas inteligentes son una forma de llevar las capacidades de los ML a donde se registran las decisiones: al etiquetar documentos durante la revisión. Al crear un grupo de etiquetas inteligentes, las decisiones que son el resultado del modelo de los ML que ha asociado al grupo de etiquetas inteligentes se muestran en línea con las etiquetas del grupo de etiquetas. Esto ayuda a ver la información de resultados de los ML en línea cuando se están revisando documentos específicos.

## <a name="how-to-set-up-a-smart-tag-group"></a>Cómo configurar un grupo de etiquetas inteligentes

1. En un conjunto de revisiones, haga clic en **administrar conjunto de revisiones** y, a continuación, en **administrar etiquetas**.

2. Haga clic en **Agregar grupo de etiquetas** y, a continuación, seleccione **Agregar grupo de etiquetas inteligentes**.

3. Seleccione el modelo de ML que desea asociar al grupo de etiquetas.
    
   Se crea un grupo de etiquetas y *n* etiquetas secundarias, donde *N* es el número de posibles salidas del modelo. Por ejemplo, el [modelo de detección de privilegios de clientes de abogados](attorney-privilege-detection.md) tiene dos posibles resultados: 

   - **Positivo** : Use para etiquetar documentos que contengan contenido privilegiado con el cliente de abogados.
   
   - **Negativo** : se usa para etiquetar documentos que no contienen contenido privilegiado de clientes.
    
    Si selecciona este modelo, se crea un grupo de etiquetas con dos etiquetas secundarias (una etiqueta secundaria llamada **positivo** y la otra llamada **negativo**) para el conjunto de revisión. En este ejemplo, cada etiqueta secundaria corresponde a uno de los resultados posibles del modelo de detección de privilegios de cliente de abogado.

4. Si lo desea, puede cambiar el nombre del grupo de etiquetas y de las etiquetas secundarias. Por ejemplo, podría cambiar el nombre de la etiqueta **positiva** a **privileged** y la etiqueta **negativa** a **no privileged**.

## <a name="how-to-use-smart-tags"></a>Cómo usar las etiquetas inteligentes

Al revisar un documento, se muestran los resultados del modelo junto a la etiqueta secundaria correspondiente. Por ejemplo, si tiene un grupo de etiquetas inteligentes para la detección de privilegios de clientes y revisa un documento que puede tener privilegios, se mostrará el motivo de dicha conclusión junto a la etiqueta correspondiente. Es importante tener en cuenta que la etiqueta no se aplica automáticamente al documento. El revisor toma la decisión sobre cómo etiquetar el documento.
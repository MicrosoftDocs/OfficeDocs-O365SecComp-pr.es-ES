---
title: Comprender la similitud de documentos en Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: 'Revise cómo el valor de similitud de documentos, el nivel mínimo de semejanza entre dos archivos que se consideran casi duplicados, funciona en eDiscovery avanzado de Office 365. '
ms.openlocfilehash: eb8f07ceedb10bd0152693dd1e82a28797d86a5a
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264162"
---
# <a name="understand-document-similarity-in-office-365-advanced-ediscovery"></a>Comprender la similitud de documentos en Office 365 Advanced eDiscovery

> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
En eDiscovery avanzado, la similitud de documentos es el nivel mínimo de semejanza necesario para que dos documentos se consideren como Near-duplicados.
  
> [!TIP]
> Para la mayoría de las aplicaciones empresariales, se recomienda usar un valor de similitud de 60%-75%. Para un material de reconocimiento óptico de caracteres (OCR) de calidad deficiente, se pueden aplicar valores de similitud inferiores. 
  
> [!NOTE]
> Una vez establecido y ejecutado para un caso determinado, el valor de similitud no se puede cambiar. 
  
Dentro de un conjunto Near-duplicado (ND), es posible que haya documentos con un nivel de semejanza inferior al umbral de similitud. Para que un documento se incorpore a un conjunto ND, debe haber al menos un documento en el ND establecido con un nivel de similitud superior a la similitud. 
  
Por ejemplo, supongamos que la similitud se establece en 80%, el documento F1 es similar al documento F2 en un nivel del 85% y el documento F2 se asemeja al documento F3 en un nivel de 90%. 
  
Sin embargo, el documento F1 puede parecerse al documento F3 en un nivel de solo 70%, que está por debajo del umbral. Sin embargo, en este ejemplo, los documentos F1, F2 y F3 aparecen en el único grupo ND. De forma similar, con un valor de similitud de 80%, podríamos haber creado dos conjuntos, EquiSet-1 y EquiSet-2. EquiSet-1 contiene los documentos E1 y E2. Equiset-2 contiene los documentos F1, F2 y F3. 
  
Los niveles de semejanza se ilustran de la siguiente manera:
  
![Similitud de documentos](media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
SuPongamos que ya se ha insertado otro documento, x1. La semejanza entre x1 y E3 es de 87%. De forma similar, la semejanza entre x1 y F1 es de 92%. Como resultado, EquiSet-1, EquiSet-2 y x1 se combinan ahora en un conjunto ND.
  
![Similitud de documentos](media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> Si hay dos documentos asignados a un conjunto ND, se mantendrán juntos en el mismo conjunto ND, incluso si se agregan documentos adicionales al conjunto o si se combinan los conjuntos. 
  
Una vez que se combinan los conjuntos, el documento dinámico puede cambiar cuando se agregan nuevos documentos a un conjunto. 
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Configuración de las opciones de análisis](set-analyze-options-in-advanced-ediscovery.md)
  
[Configuración de omitir texto](set-ignore-text-in-advanced-ediscovery.md)
  
[Configuración de la configuración avanzada de análisis](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[Visualización de los resultados del análisis](view-analyze-results-in-advanced-ediscovery.md)


---
title: Comprender la similitud de documentos en eDiscovery avanzado de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: 'Revisión de cómo funciona el documento valor similitud, el nivel mínimo de similitud para los dos archivos se considere cerca de duplicados, en la exhibición de documentos electrónicos avanzada de Office 365. '
ms.openlocfilehash: 39cd8c31204f0164f6b52c71fa707253cb22758a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536026"
---
# <a name="understand-document-similarity-in-office-365-advanced-ediscovery"></a>Comprender la similitud de documentos en eDiscovery avanzado de Office 365

> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
En la exhibición de documentos electrónicos avanzada, similitud de documento es el nivel mínimo de similitud necesario para que dos documentos que se considerarán cerca de duplicados.
  
> [!TIP]
> Para la mayoría de las aplicaciones empresariales, se recomienda utilizar un valor de similitud del 60% - 75%. Muy mala calidad reconocimiento óptico de caracteres (OCR) (en inglés), se pueden aplicar los valores más bajos de similitud. 
  
> [!NOTE]
> Una vez que ha establecido y ejecutar para un caso determinado, no se puede cambiar el valor de similitud. 
  
Dentro de un conjunto de duplicados Near (ND), es posible que haya documentos con un nivel de similitud por debajo del umbral de similitud. Para que un documento para unirse a un conjunto de ND, debe haber al menos un documento en el ND establecer con un nivel de la superación del límite de la similitud de similitud. 
  
Por ejemplo, supongamos que la similitud se establece en 80%, documento F1 es similar a documento F2 en un nivel de 85% y documento F2 es similar a documento F3 en un nivel de 90%. 
  
Sin embargo, el documento F1 puede ser similar a documento F3 en un nivel de sólo el 70%, que es por debajo del umbral. No obstante, en este ejemplo, documentos F1, F2 y F3 todos aparecen en la uno ND establecido. De forma similar, con un valor de similitud del 80%, nos podremos ha creado dos conjuntos, EquiSet-1 y EquiSet-2. EquiSet-1 contiene documentos E1 y E2. Equiset-2 contiene documentos F1, F2 y F3. 
  
Los niveles de similitud se ilustran como sigue:
  
![Similitud de documentos](media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
Se supone que el otro documento, X1, ahora se inserta. La similitud entre X1 y E3 es 87%. De forma similar, la similitud entre X1 y F1 es 92%. Como resultado, EquiSet -1, EquiSet -2 y X1 ahora se combinan en uno ND establecer.
  
![Similitud de documentos](media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> Si los dos documentos están asignados a un conjunto de ND, seguirán siendo juntos en el mismo conjunto de ND, documentos incluso si adicionales se agregan al conjunto o si se combinan los conjuntos. 
  
Después de que se combinan conjuntos, puede cambiar el documento de la tabla dinámica cuando se agregan nuevos documentos a un conjunto. 
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Configurar las opciones de análisis](set-analyze-options-in-advanced-ediscovery.md)
  
[Configuración de omitir el texto](set-ignore-text-in-advanced-ediscovery.md)
  
[Análisis de la opción Configuración avanzada](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[Ver los resultados del análisis](view-analyze-results-in-advanced-ediscovery.md)


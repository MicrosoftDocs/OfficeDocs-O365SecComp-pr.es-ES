---
title: Establecer opciones avanzadas de analizar en eDiscovery avanzado de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a797682f-ad85-4c08-a354-3850ba2237ee
description: 'Obtenga información acerca de cómo configurar opciones avanzadas, como casi duplicados, subprocesos de correo electrónico y temas, para el proceso de análisis en la exhibición avanzada de documentos electrónicos de Office 365. '
ms.openlocfilehash: d8dfb9f3ecfcda0f267dfccdc716eda40fe450b2
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220090"
---
# <a name="set-analyze-advanced-settings-in-office-365-advanced-ediscovery"></a>Establecer opciones avanzadas de analizar en eDiscovery avanzado de Office 365

> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
EDiscovery avanzado proporciona parámetros avanzados predeterminados para la configuración del módulo de análisis. En el procedimiento siguiente se describe la configuración que se puede especificar.
  
1. En la **ficha \> preparar \> la configuración de ANALYZE** , haga clic en **Configuración avanzada** (en la parte inferior de la página). Se muestra el siguiente panel. 
    
    ![Establecer la configuración avanzada del análisis](media/c9ea3017-e19a-456b-a742-c3d07121a3f6.png)
  
2. En **parámetros casi duplicados y**de subprocesos de correo electrónico, seleccione valores para las siguientes opciones, según sea necesario:
    
  - **Número mínimo de palabras**: número mínimo de palabras, por debajo del cual no se envía un archivo para análisis casi duplicados. 
    
  - **Número máximo de palabras**: número máximo de palabras, por encima de las cuales no se envía un archivo para análisis casi duplicados.
    
  - **Similitud de correo electrónico**: el nivel mínimo de semejanza de dos correos electrónicos se considerará similar. El valor es siempre igual a o mayor que el de la similitud del documento. El valor predeterminado es 90%.
    
3. En **los parámetros de los temas**, active la casilla **incluir números en el análisis del tema** para incluir números en el procesamiento de temas durante el análisis. 
    
4. Haga clic en **Guardar**. 
    
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Descripción de la similitud de documentos](understand-document-similarity-in-advanced-ediscovery.md)
  
[Configuración de las opciones de análisis](set-analyze-options-in-advanced-ediscovery.md)
  
[Configuración de omitir texto](set-ignore-text-in-advanced-ediscovery.md)
  
[Visualización de los resultados del análisis](view-analyze-results-in-advanced-ediscovery.md)


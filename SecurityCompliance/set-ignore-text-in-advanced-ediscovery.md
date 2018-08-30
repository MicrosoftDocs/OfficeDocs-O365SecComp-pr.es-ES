---
title: Establecer la opción de omitir el texto para analizar en eDiscovery avanzado de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: 'Obtenga información sobre cómo definir la regla para omitir el texto específico al utilizar los módulos de proceso y analizar en la exhibición de documentos electrónicos avanzada de Office 365.  '
ms.openlocfilehash: eb7e7052979087b7dba98aac3b0c9ab75ec0d02a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536239"
---
# <a name="set-ignore-text-option-for-analyze-in-office-365-advanced-ediscovery"></a>Establecer la opción de omitir el texto para analizar en eDiscovery avanzado de Office 365

> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
La característica de omitir el texto se puede aplicar a todos o cualquiera de los siguientes módulos de exhibición de documentos electrónicos avanzada: analizar (cerca de duplicados, subprocesos de correo electrónico, los temas) y la relevancia. Texto omitido no aparecerán en los archivos que se muestran en la relevancia y los cálculos de análisis descartará el texto omitido.
  
Si la característica de omitir el texto se ha definido previamente para los módulos que ya ha ejecutado, la opción Omitir texto ahora estará protegida frente a la modificación. Sin embargo, aún puede cambiarse la característica de omitir el texto para el módulo de la relevancia en cualquier momento.
  
## <a name="how-ignore-text-filters-are-applied"></a>Cómo se aplican los filtros de omitir texto

Varios filtros de omitir texto se aplican en el orden en que se escribieron. Para cambiar el orden en que se aplican, debe eliminar y volver a escribir en el orden que desee.
  
Por ejemplo, si el contenido de texto es: "EVA de CAROL de ALICE para BOB de DAVE", los siguientes son ejemplos de entradas de omitir el texto y los resultados:
  
||||
|:-----|:-----|:-----|
|**Omitir las entradas de texto** <br/> |**==\>** <br/> |**Resultados** <br/> |
|"ALICE", "BOB ANA"  <br/> |==\>  <br/> |"DAVE EVA"  <br/> |
|"ALICE", "BOB ALICE CAROL"  <br/> |==\>  <br/> |"DAVE BOB CAROL EVA"  <br/> |
   
No se implementa la segunda entrada de texto omitir debido a que la cadena no se encuentra como tal, una vez que se ha aplicado el primer texto omitir.
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a>Usar expresiones regulares al definir Omitir texto

Expresiones regulares compatibles para su uso al definir Omitir texto. Los siguientes son ejemplos de uso y la sintaxis de expresión regular:
  
- Para quitar (omitir) el texto de inicio hasta el final de una línea:
    
     `Begin(.*)$`
    
    donde "Begin" es la aparición de esta cadena en la línea inicial.
    
    Por ejemplo, para el siguiente texto:
    
    **"Ésta es la primera oración y primera línea**
    
    **Ésta es la segunda oración y la segunda línea"**
    
    la expresión Regular first(.\*) $ dará como resultado:
    
    **"Ésta es la**
    
    **Ésta es la segunda oración y la segunda línea"**
    
- Para quitar la declinación de responsabilidades y legales instrucciones que se insertan automáticamente al final de subprocesos de correo electrónico:
    
     `Begin(.|\s)*End`
    
    donde "Begin" y "End" son cadenas únicas al principio y al final de un párrafo de texto ajustado. 
    
    Por ejemplo, la siguiente expresión regular quitará declinación de responsabilidades y declaraciones legales que estaban en el subproceso de correo electrónico entre las cadenas Begin y End:
    
    **Este mensaje contiene información confidencial (. | \s)\*si es necesario la verificación por favor, solicitar una versión de la copia impresa**
    
- Para quitar una renuncia de responsabilidad (incluidos los caracteres especiales): 
    
    Por ejemplo, para el siguiente texto (con la declinación de responsabilidades aquí representado por x): 
    
    **/\*\ Este mensaje contiene información confidencial. xxxx xxxx**
    
    **xxxx xxxx xxxx xxxx xxxx xxxx xxxx**
    
    **Si es necesario, la verificación: xxxx xxxx solicita una versión de la copia impresa. /\*\**
    
    debe ser la expresión regular para quitar la declinación de responsabilidades anterior: 
    
    **\/\\*\\Este mensaje contiene información confidencial\.(. | \s)\* si es necesario la verificación por favor, solicitar una versión de la copia impresa\.\/\\*\\**
    
- Reglas de expresión regular:
    
  - Todos los caracteres que no forman parte del alfabeto excepto espacios, "_" y "-" debe ir precedido por "\".
    
  - El campo eExpression regular puede ser una longitud ilimitada.
    
> [!TIP]
> Para obtener una explicación y detallada sobre la sintaxis de expresiones regulares, consulte: [Lenguaje de expresiones regulares - referencia rápida](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx). 
  
## <a name="define-ignore-text-rule"></a>Definir la regla de omitir texto

1. En la **administrar \> analizar \> analizar las opciones de** ficha, en la sección **Omitir texto** , haga clic en el **+** icono para agregar una regla. 
    
2. En el cuadro de diálogo **Agregar texto omitir** , en el campo **nombre** , escriba un nombre para la regla de texto omitir. 
    
    ![Agregar texto omitido](media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. En el cuadro de **texto** , escriba el texto que se pasen por alto. El campo de texto permite a un número ilimitado de caracteres. 
    
    > [!TIP]
    > Tal como se muestra en la ventana anterior, haga clic en la **bombilla** para ver las instrucciones de sintaxis comunes para la regla de texto omitir. 
  
4. Seleccione la casilla de verificación **distinguir mayúsculas de minúsculas** , si así lo desea. 
    
5. En la lista **aplicar a** , seleccione los módulos de exhibición de documentos electrónicos avanzada en el que se va a aplicar la definición. 
    
6. Si desea que una ejecución de prueba en el texto de ejemplo, escriba el texto de ejemplo en el cuadro de texto de **entrada** y haga clic en **probar**. Los resultados se muestran en el cuadro de texto de **salida** . 
    
7. Haga clic en **Aceptar** para guardar la regla Omitir texto. Se muestra la regla de omitir texto definida. 
    
    ![Establecer el nombre del texto omitido](media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Descripción de la similitud de documento](understand-document-similarity-in-advanced-ediscovery.md)
  
[Configurar las opciones de análisis](set-analyze-options-in-advanced-ediscovery.md)
  
[Análisis de la opción Configuración avanzada](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[Ver los resultados del análisis](view-analyze-results-in-advanced-ediscovery.md)


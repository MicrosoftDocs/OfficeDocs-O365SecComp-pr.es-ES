---
title: Establecer opciones de analizar en eDiscovery avanzado de Office 365
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
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: 'Revise los pasos para configurar las opciones para el proceso de analizar en Office 365 avanzada exhibición de documentos electrónicos, incluidos cerca de duplicados, los subprocesos de correo electrónico y los temas.  '
ms.openlocfilehash: a0ebbadb180321a3094cb1056ed8e0e6500ee66a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536187"
---
# <a name="set-analyze-options-in-office-365-advanced-ediscovery"></a>Establecer opciones de analizar en eDiscovery avanzado de Office 365

> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
En Opciones avanzadas exhibición de documentos electrónicos, establezca las opciones de analizar antes de ejecutar Analyze.
  
## <a name="set-analyze-options"></a>Establecer las opciones de análisis

Open **preparar \> analizar** \> **el programa de instalación**. Se muestra la siguiente ventana.
  
![Establecer las opciones de análisis](media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 **Cerca de duplicados y subprocesos de correo electrónico** Active esta casilla si desea ejecutar el análisis. Se selecciona de forma predeterminada. 
  
 **Similitud de documento** Escriba el valor del umbral Near duplicados o acepte el valor predeterminado de 65%. 
  
 **Temas** Active esta casilla para procesar todos los archivos y asignar los temas a ellos. De forma predeterminada, esta casilla de verificación no está seleccionada. Si desea realizar los temas de procesamiento, especifique las siguientes opciones.
  
- **Número máximo de temas** Introduzca o seleccione un valor para el número de temas para crear. El valor predeterminado es 200. 
    
    > [!NOTE]
    > El aumento del número de temas afecta al rendimiento, así como la capacidad de un tema para generalizar. Cuanto mayor sea el número de temas, más granulares son. Por ejemplo, si un conjunto de 50 temas incluye un tema, como "Baloncesto, cambio, cortar, Lakers"; temas de 300 pueden incluir temas independientes: "Cual insta", "Cortar", "Lakers". Si no tenía ningún conocimiento del tema "Baloncesto" y usar esta característica para ECA, vea el tema "Baloncesto" podría ser útil. Sin embargo, si el procesamiento tenía demasiados temas, es posible que vea nunca la palabra "Baloncesto" y no puede saber que cambio y cortar es una buena temas baloncesto para revisar, en lugar de los elementos que vaya de se inicia y se usa de forma. 
  
- **Temas que se sugiere** Puede sugerir palabras de tema para controlar el procesamiento de temas. Exhibición de documentos electrónicos avanzada se centrarse en estas palabras sugeridas y pruebe a crear uno o varios temas relevantes, en función de la configuración de "Número de temas de Max". 
    
    Por ejemplo, si la palabra sugerida es "computer", y especificó "2" como el "número de temas de Max", intentará avanzada exhibición de documentos electrónicos generar dos temas que se relacionan con la palabra "equipo". Los dos temas podrían ser "software informático" y "hardware del equipo", por ejemplo. 
    
    ![Agregar tema sugerido](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. Para ver, agregar o editar los temas sugeridos, haga clic en **Modificar**.
    
2. En el panel de **temas que se sugiere** , haga clic en el **complemento**![agregar icono](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icono para agregar un tema. En el panel de **tema sugerido de agregar** , agregue las palabras, separadas por comas. 
    
3. En **número de temas**, seleccione un valor para determinar el número de temas de exhibición de documentos electrónicos avanzada intentará generar estas palabras (el valor predeterminado es 1 tema).
    
4. Haga clic en **Guardar** y, a continuación, cierre el cuadro de diálogo. 
    
    > [!NOTE]
    > El número total de temas incluye temas sugeridos. Los temas sugeridos total no puede superar los temas totales. Si hay muchos temas sugeridos con respecto a los temas totales, sólo los temas de "nuevos" unos será detectados por el sistema debido a que la mayoría de los temas se dedicarse a temas sugeridos. 
  
- **Modo** En la lista desplegable, seleccione una opción de **temas** : 
    
  - **Crear y aplicar el modelo de**: calcula los temas por modelos de un segmento de los archivos y, a continuación, distribuye los archivos entre ellos.
    
  - **Crear modelo**: calcula un modelo de temas de un segmento de los archivos. El proceso de aplicación de dividir los archivos se realiza por separado en otro momento.
    
  - **Aplicar modelo**: esta opción sólo se muestra si un modelo se ha creado anteriormente y todavía no se ha aplicado. Esto dividirá los archivos basándose en los temas.
    
También puede [Omitir el conjunto de texto](set-ignore-text-in-advanced-ediscovery.md) y [establecer la configuración avanzada de analizar](set-analyze-advanced-settings-in-advanced-ediscovery.md) para analizar. 
  
Una vez haya configurado estas opciones, haga clic en **analizar** para ejecutar. Se muestran [los resultados de la vista de análisis](view-analyze-results-in-advanced-ediscovery.md) . 
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Descripción de la similitud de documento](understand-document-similarity-in-advanced-ediscovery.md)
  
[Omitir el conjunto de texto](set-ignore-text-in-advanced-ediscovery.md)
  
[Establecer la configuración avanzada del análisis](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[Ver los resultados de análisis](view-analyze-results-in-advanced-ediscovery.md)


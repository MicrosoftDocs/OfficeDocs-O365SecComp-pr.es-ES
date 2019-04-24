---
title: Usar el análisis rápido en Office 365 Advanced eDiscovery
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
ms.assetid: 50580099-3dc0-44a1-a9b6-5ca6d396316b
description: Obtenga información sobre cómo ejecutar el modo de análisis rápido de Office 365 Advanced eDiscovery
ms.openlocfilehash: d8457587c9c1a1237ddc076ce803a46382a04ed8
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264502"
---
# <a name="use-express-analysis-in-office-365-advanced-ediscovery"></a>Usar el análisis rápido en Office 365 Advanced eDiscovery

> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Puede usar el **análisis** rápido para analizar rápidamente un caso y exportar los resultados. 
  
Puede usar el análisis rápido para calcular los subprocesos de correo electrónico y los subprocesos casi duplicados, y calcular temas. También puede establecer determinados parámetros para los temas, la similitud de documentos y los archivos de exportación en la [Configuración avanzada de análisis rápido](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).
  
## <a name="run-express-analysis"></a>Ejecutar el análisis rápido

1. En la ficha **análisis rápido** (1), seleccione un contenedor para habilitar los botones * * Express Analysis * * (2) y **Configuración avanzada** . 
    
    ![Captura de pantalla de la página de análisis de Express](media/60009974-5d1f-4971-8ebe-e5ec74e7fd2a.jpg)
  
2. En **parámetros de análisis**:
    
  - Si desea ejecutar el análisis, marque **calcular Near-duplicados y conversaciones de correo electrónico** . Está seleccionada de forma predeterminada. 
    
  - Marque la casilla **calcular temas** para procesar todos los archivos y asignarles temas. Está seleccionada de forma predeterminada. 
    
3. En **destino de exportación**:
    
  - Consulte **Descargar en** el equipo local para descargar en el equipo local. 
    
  - Si comprueba **exportar a BLOB de Azure definido por el usuario** , también puede especificar una dirección URL de contenedor y un token de SAS. 
    
    > [!NOTE]
    > Una vez que un paquete de exportación se almacena en el BLOB de Azure definido por el usuario, los datos ya no se administran mediante la exhibición avanzada de documentos electrónicos. se administra mediante el BLOB de Azure. Esto significa que, al eliminar el caso, los archivos exportados seguirán en el BLOB de Azure. 
  
  - **Guardar token de SAS para sesión de exportación en el futuro**: si se activa, el token de SAS se cifrará en la base de datos interna de eDiscovery avanzado para su uso en el futuro.
    
    > [!NOTE]
    > Actualmente, el token de SAS expira después de un mes. Si intenta descargar después de más de un mes, deshaga la última sesión y, a continuación, vuelva a exportar. 
  
4. Para iniciar el análisis de Express con la configuración predeterminada, elija **análisis rápido**y aparecerá la página estado de la **tarea** . 
    
    En la **Página estado** de la tarea, puede ampliar las pestañas **proceso**, **analizar** y **exportar** para mostrar detalles sobre la ejecución rápida. 
    
    ![Captura de pantalla de la página de estado de tarea de análisis avanzado de eDiscovery Express](media/bf30ab02-9828-4a6d-a485-0babc2c49ae5.jpg)
  
5. Seleccione la página **Resumen de análisis urgente** para enumerar la información detallada sobre la ejecución. 
    
    En la parte inferior de la página **Resumen de análisis urgente** , elija **Descargar última sesión** para descargar los archivos de análisis (TP) en el equipo local. Primero tendrá que descargar la herramienta de exportación de exhibición de documentos electrónicos y pegar la clave de exportación a la herramienta de exportación de exhibición de documentos electrónicos. 
    
## <a name="advanced-settings-for-express-analysis"></a>Configuración avanzada de análisis rápido
<a name="BK_AdvancedSettings"> </a>

Opcionalmente, puede establecer la **Configuración avanzada** para cambiar los parámetros predeterminados de análisis de Express. 
  
1. En la sección **analizar** : 
    
  - En las **conversaciones de correo electrónico y los duplicaDos Near**, escriba el valor de **similitud del documento** o acepte el valor predeterminado de 65%. 
    
  - En el **número máximo de temas** , escriba o seleccione un valor para el número de temas que se va a crear. El valor predeterminado es 200. 
    
    > [!NOTE]
    > El aumento del número de temas afecta al rendimiento, así como la capacidad de un tema de generalizar. Cuanto mayor sea el número de temas, más granular serán. Por ejemplo, si un conjunto de 50 temas incluye un tema como "baloncesto, podas, Clippers, Lagoros"; 300 temas pueden incluir temas separados: "", "," podadoras "," lago ". Si no ha tenido conocimiento del tema "baloncesto" y usa esta característica para ECA, puede resultar útil ver el tema "baloncesto". Sin embargo, si el procesamiento tenía demasiados temas, es posible que nunca vea la palabra "baloncesto" y que no sepa que las pausas y las Clippers son buenos temas de baloncesto que revisar, en lugar de que se inician y se usan para el pelo. 
  
  - En los **temas sugeridos** , elija **modificar** para sugerir palabras del tema para controlar el procesamiento de temas. EDiscovery avanzado se centrará en estas palabras sugeridas y intentará crear uno o más temas relevantes, en función de la configuración del "número máximo de temas". 
    
    Por ejemplo, si la palabra sugerida es "equipo" y ha especificado "2" como "número máximo de temas", la exhibición avanzada de documentos electrónicos intentará generar dos temas relacionados con la palabra "equipo". Por ejemplo, los dos temas podrían ser "software de equipo" y "hardware de equipo".
    
    ![Agregar tema sugerido](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
  - **Modo** En la lista desplegable, seleccione una opción de **temas** : 
    
  - **Crear y aplicar modelo**: calcula los temas por modelos de un segmento de los archivos y, a continuación, distribuye los archivos entre ellos.
    
  - **Create Model**: calcula un modelo de temas a partir de un segmento de los archivos. El proceso de aplicar divisiones de archivos se realiza por separado en otro momento.
    
  - **Aplicar modelo**: esta opción solo se muestra si un modelo se ha creado anteriormente y todavía no se ha aplicado. Se dividirán los archivos según los temas.
    
2. En la sección **exportar** : 
    
1. En el **Seleccione lote de exportación**:
    
  - En la lista **exportar lote** , seleccione el nombre del lote o exportar resultados al lote de exportación 01, (el lote predeterminado). 
    
  - Para exportar los resultados de los nuevos archivos que agregó a un caso existente, continúe con el lote actual. Para crear una sesión en el lote, seleccione el mismo número de lote y haga clic en **crear sesión de exportación** puede usar esta opción para exportar los mismos parámetros que el lote anterior, de forma incremental. 
    
  - Para exportar a un nuevo lote, haga **** ![clic en agregar](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icono Agregar y escriba un nuevo nombre en **nombre de lote** (o acepte el valor predeterminado) y una descripción en **Descripción del lote**. Haga clic en **Aceptar**.
    
  - Para editar un nombre de lote o una descripción, seleccione el nombre en **lote de exportación**, haga](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)clic en **Editar** ![icono Editar y, a continuación, modifique los campos.
    
    > [!NOTE]
    > Después de ejecutar sesiones para un lote de exportación, no se pueden eliminar. Además, solo algunos parámetros pueden editarse una vez ejecutada la primera sesión. 
  
  - Para crear un lote de exportación duplicado **** ![, elija duplicar lote de exportación cree un](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) icono de exportación de lote duplicado y escriba un nombre y una descripción para el lote duplicado en el panel. 
    
  - Para eliminar un lote de exportación, elija **eliminar** ![eliminar lote de exportación](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).
    
  - Para ver el historial de un lote, seleccione icono ![](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)de historial de vista de **historial por lotes** .
    
2. En definir p? **opulation:** seleccione **incluir sólo los archivos** que superen la puntuación de recorte de relevancia o refinar el **lote de exportación** si desea ajustar la configuración del lote de exportación. Si selecciona **incluir sólo los archivos**de la puntuación de recorte de la relevancia, el **problema** está habilitado y, si la puntuación de relevancia del archivo es superior a la puntuación de corte para el problema seleccionado, el archivo se exportará. El archivo se exportará a menos que el filtro " **para revisión** " lo excluya. Si selecciona refinar **lote de exportación**, los botones de opción desduplicación y **filtrar por "para revisión"** están habilitados. **** Si elige desduplicación, los archivos duplicados se filtrarán de acuerdo con la Directiva definida: [nivel de caso (predeterminado): de cada conjunto de archivos duplicados en todo el caso, se desduplicarán todos los archivos menos uno. **** Nivel de custodio: de cada conjunto de archivos duplicados del mismo custodio, se desduplicarán todos menos un archivo. Hay disponible un registro de todos los archivos duplicados en la salida de la exportación. Si elige **filtrar por ' para revisión '** , seleccione **modificar en metadatos** para escribir la configuración del campo **' para revisión '**. Seleccione **incluir archivos de entrada**para incluir los archivos de origen en el contenido del paquete. Puede desactivar esta opción para acelerar el proceso de exportación. Tenga en cuenta que los archivos nativos se exportarán en cualquier caso.
    
3. En **definir metadatos**, seleccione una de las siguientes opciones de la lista **exportar plantilla** (una vez por sesión). 
    
  - **Standard**: conjunto básico de elementos de datos, metadatos y propiedades. Use esta opción si ya se procesó la importación de datos en eDiscovery avanzado y los datos de exportación se cargan en un sistema que ya contiene los archivos. De forma predeterminada, las columnas de plantilla de exportación se crean y se rellenan.
    
  - **All**: conjunto completo de metadatos estándar, incluidos todos los datos de procesamiento, así como los resultados del análisis y la relevancia. Esta plantilla es necesaria cuando la exhibición avanzada de documentos electrónicos realiza el procesamiento y los datos de archivos se cargan en un sistema externo por primera vez.
    
  - **Problemas**: seleccione **todos los problemas** o seleccione un asunto concreto que haya creado. 
    
Elija **Aceptar**para guardar la configuración avanzada, **restaurar** los valores predeterminados para usar los valores predeterminados o **Cancelar** para cancelar la configuración avanzada. 
  
## <a name="see-also"></a>Vea también
<a name="BK_AdvancedSettings"> </a>

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)


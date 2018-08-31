---
title: Usar análisis rápido en eDiscovery avanzado de Office 365
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
ms.assetid: 50580099-3dc0-44a1-a9b6-5ca6d396316b
description: Obtenga información sobre cómo ejecutar el modo de análisis Express de exhibición de documentos electrónicos avanzada de Office 365
ms.openlocfilehash: a71e6775b1116e805e455815dca53a727d887809
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536060"
---
# <a name="use-express-analysis-in-office-365-advanced-ediscovery"></a>Usar análisis rápido en eDiscovery avanzado de Office 365

> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Puede usar **Express análisis** para analizar rápidamente un caso y exportar los resultados. 
  
Puede usar análisis express para calcular cerca de duplicados y subprocesos de correo electrónico y calcular los temas. También puede establecer determinados parámetros para temas, similitud de documento y los archivos de exportación en la [Configuración avanzada para el análisis de Express](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).
  
## <a name="run-express-analysis"></a>Ejecutar el análisis de Express

1. En la ficha **análisis Express** (1), seleccione un contenedor para habilitar la ** Express análisis ** (2) y los botones de **Configuración avanzada** . 
    
    ![Captura de pantalla de la página de análisis de Express](media/60009974-5d1f-4971-8ebe-e5ec74e7fd2a.jpg)
  
2. En los **parámetros de análisis**:
    
  - Comprobar **calcular cerca de duplicados y subprocesos de correo electrónico** si desea ejecutar el análisis. Se selecciona de forma predeterminada. 
    
  - Comprobar **Calcular temas** para procesar todos los archivos y asignar los temas a ellos. Se selecciona de forma predeterminada. 
    
3. En la **exportación de destino**:
    
  - Compruebe la **descarga en el equipo local** para descargar en su equipo local. 
    
  - Si marca **Exportar a blob Azure definidas por el usuario** también puede especificar un token de dirección URL y SAS de contenedor. 
    
    > [!NOTE]
    > Una vez que se almacena un paquete de exportación para el usuario definido Azure blob, los datos ya no se administran mediante avanzada exhibición de documentos electrónicos. se administra mediante el blob de Azure. Esto significa que si se elimina el caso, los archivos exportados seguirá estando en el blob de Azure. 
  
  - **Guardar SAS símbolo (token) de sesión de exportación futuras**: si está activado, el token de SAS se cifrarán en la base de datos interna de la exhibición de documentos avanzadas para un uso futuro.
    
    > [!NOTE]
    > Actualmente, el token de SAS expira después de un mes. Si se intenta descargar después de más de un mes que tenga que deshacer la última sesión, a continuación, exportar de nuevo. 
  
4. Para iniciar el análisis express con predeterminada configuración, elija **Express análisis**y se mostrará la página de **estado de la tarea** 
    
    En la página de **estado de la tarea** se pueden expandir las fichas de **proceso**, **analizar** y **Exportar** para mostrar detalles acerca de la ejecución de express. 
    
    ![Captura de pantalla de avanzada página de estado de tarea de exhibición de documentos electrónicos Express análisis](media/bf30ab02-9828-4a6d-a485-0babc2c49ae5.jpg)
  
5. Elija la página **Resumen de análisis de Express** para obtener información detallada acerca de la ejecución de la lista. 
    
    En la parte inferior de la página **Resumen de análisis de Express** , elija **Descargar la última sesión** para descargar el tp de los archivos de análisis en el equipo local. En primer lugar deberá descargar la herramienta de exportación de exhibición de documentos electrónicos y pegue la clave de exportación para la herramienta de exportación de exhibición de documentos electrónicos. 
    
## <a name="advanced-settings-for-express-analysis"></a>Configuración avanzada para el análisis de Express
<a name="BK_AdvancedSettings"> </a>

Opcionalmente puede establecer la **Configuración avanzada** para cambiar los parámetros de análisis de Express de forma predeterminada. 
  
1. En la sección **analizar** : 
    
  - En el **próximo duplicados y subprocesos de correo electrónico**, escriba el valor de **similitud de documento** o acepte el valor predeterminado de 65%. 
    
  - En el **número máximo de temas** Introduzca o seleccione un valor para el número de temas para crear. El valor predeterminado es 200. 
    
    > [!NOTE]
    > El aumento del número de temas afecta al rendimiento, así como la capacidad de un tema para generalizar. Cuanto mayor sea el número de temas, más granulares son. Por ejemplo, si un conjunto de 50 temas incluye un tema, como "Baloncesto, cambio, cortar, Lakers"; temas de 300 pueden incluir temas independientes: "Cual insta", "Cortar", "Lakers". Si no tenía ningún conocimiento del tema "Baloncesto" y usar esta característica para ECA, vea el tema "Baloncesto" podría ser útil. Sin embargo, si el procesamiento tenía demasiados temas, es posible que vea nunca la palabra "Baloncesto" y no puede saber que cambio y cortar es una buena temas baloncesto para revisar, en lugar de los elementos que vaya de se inicia y se usa de forma. 
  
  - En los **temas que se sugiere** elija **Modificar** para sugerir palabras de tema para controlar el procesamiento de temas. Exhibición de documentos electrónicos avanzada se centrarse en estas palabras sugeridas y pruebe a crear uno o varios temas relevantes, en función de la configuración de "Número de temas de Max". 
    
    Por ejemplo, si la palabra sugerida es "computer", y especificó "2" como el "número de temas de Max", intentará avanzada exhibición de documentos electrónicos generar dos temas que se relacionan con la palabra "equipo". Los dos temas podrían ser "software informático" y "hardware del equipo", por ejemplo.
    
    ![Agregar tema sugerido](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
  - **Modo** En la lista desplegable, seleccione una opción de **temas** : 
    
  - **Crear y aplicar el modelo de**: calcula los temas por modelos de un segmento de los archivos y, a continuación, distribuye los archivos entre ellos.
    
  - **Crear modelo**: calcula un modelo de temas de un segmento de los archivos. El proceso de aplicación de dividir los archivos se realiza por separado en otro momento.
    
  - **Aplicar modelo**: esta opción sólo se muestra si un modelo se ha creado anteriormente y todavía no se ha aplicado. Esto dividirá los archivos basándose en los temas.
    
2. En la sección **Exportar** : 
    
1. En la **sección de exportación Select**:
    
  - En la lista **Exportar por lotes** , seleccione el nombre del lote o exportar los resultados a la sección de exportación 01, (el lote de forma predeterminada). 
    
  - Para exportar los resultados de los archivos nuevos que ha agregado a un caso existente, continúe con el lote actual. Para crear una sesión en el lote, seleccione el mismo número de lote y haga clic en **crear exportación sesión** puede usar esta opción para exportar los mismos parámetros como el lote anterior, de manera incremental. 
    
  - Para exportar a un nuevo lote, haga clic en **Agregar**![agregar icono](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) y especifique un nuevo nombre en **nombre de lote** (o acepte el valor predeterminado) y una descripción en la **Descripción de lote**. Haga clic en **Aceptar**.
    
  - Para editar un nombre de proceso por lotes o una descripción, seleccione el nombre de **exportación por lotes**, haga clic en **Editar** ![icono Editar](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)y, a continuación, modifique los campos.
    
    > [!NOTE]
    > Una vez ejecutado el sesiones de una sección de exportación, no se puede eliminar. Además, se pueden editar sólo algunos parámetros una vez que se ejecuta la primera sesión. 
  
  - Para crear un lote de exportación duplicados, elija **por lotes de exportación de duplicado**![crear un icono de proceso por lotes de exportación duplicados](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) y escriba un nombre y una descripción para el lote de duplicados en el panel. 
    
  - Para eliminar una sección de exportación, elija **Eliminar**![eliminar un icono de exportación de lote](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).
    
  - Para ver el historial de un lote, elija **Historial por lotes**![icono de vista de historial](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).
    
2. En definir p **opulation:** seleccione **incluir solo los archivos por encima de la puntuación de relevancia corte** o **por lotes de exportación de refinar** si desea ajustar la configuración de la sección de exportación. Si selecciona **incluir sólo archivos por encima de la puntuación de relevancia corte**, a continuación, se habilita el **problema** y, si la puntuación de relevancia del archivo es mayor que la puntuación de límite para el problema seleccionado, a continuación, se exporta el archivo. El archivo se exportará a menos que lo excluye la ' filtro **para su revisión** . Si selecciona **por lotes de exportación de refinar**, a continuación, la **desduplicación** y **Filter by 'Para revisión' campo** se habilitan los botones de opción. Si elige **la desduplicación**, a continuación, los archivos duplicados se se filtran-out según la directiva definida: [Case nivel (valor predeterminado): de cada conjunto de archivos duplicados en el caso todo, será desaprovisionamiento duped todos menos un archivo. Nivel de custodia: de cada conjunto de archivos duplicados de la misma custodia, será desaprovisionamiento duped todos menos un archivo. Un registro de todos los archivos duplicados está disponible en los resultados de la exportación. Si elige **filtrar por 'para revisión'** campo, seleccione **modificar en metadatos** para escribir la configuración de campo **'para revisión'**. Seleccione **incluir los archivos de entrada**para incluir los archivos de origen en el contenido del paquete. Puede desactivar esta opción para acelerar el proceso de exportación. Tenga en cuenta que se exportará los archivos nativos en cualquier caso.
    
3. En **definir metadatos**, seleccione entre las siguientes opciones en la lista **plantilla de exportación** (una vez por sesión). 
    
  - **Estándar**: conjunto básico de propiedades, metadatos y elementos de datos. Use esta opción cuando importar datos ya se procesan en la exhibición de documentos electrónicos avanzada y exportar datos se carguen a un sistema que ya contiene los archivos. De forma predeterminada, se crean las columnas de plantilla de exportación y se rellena.
    
  - **Todos los**: conjunto completo de metadatos estándar, incluidos todos los datos de procesamiento, así como las puntuaciones de análisis y la relevancia. Esta plantilla se requiere cuando exhibición de documentos electrónicos avanzada realiza el procesamiento y datos de archivo se carguen a un sistema externo por primera vez.
    
  - **Problemas**: seleccione **Todos los problemas** o seleccione un problema determinado que haya creado. 
    
Elija **Aceptar**, para guardar la configuración avanzada, **restaurar la configuración predeterminada** para utilizar los valores predeterminados o **Cancelar** para cancelar la configuración de la configuración avanzada. 
  
## <a name="see-also"></a>Vea también
<a name="BK_AdvancedSettings"> </a>

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)


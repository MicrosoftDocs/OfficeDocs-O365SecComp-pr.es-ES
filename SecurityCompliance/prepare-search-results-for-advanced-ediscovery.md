---
title: Preparar los resultados de búsqueda para la exhibición avanzada de documentos electrónicos de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportWithZoom
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 0b6fac2d-8627-4b05-9df0-03609db6248b
description: Obtenga información sobre cómo preparar los resultados de una búsqueda de contenido en el centro &amp; de seguridad y cumplimiento de Office 365 para un análisis más avanzado con la herramienta Advanced eDiscovery.
ms.openlocfilehash: 04de96064f400f8055d0e477bf41ed1c7cb1b35f
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223849"
---
# <a name="prepare-search-results-for-office-365-advanced-ediscovery"></a>Preparar los resultados de búsqueda para la exhibición avanzada de documentos electrónicos de Office 365

Una vez que se ejecuta correctamente una búsqueda asociada a un caso de exhibición de &amp; documentos electrónicos en el centro de seguridad y cumplimiento de Office 365, puede preparar los resultados de la búsqueda para un análisis más avanzado con Office 365 Advanced eDiscovery, que le permite analizar grandes conjuntos de datos no estructurados y reducir la cantidad de datos que son relevantes para un caso legal. Las características avanzadas de eDiscovery incluyen:
  
- **Reconocimiento óptico de caracteres** : al preparar los resultados de la búsqueda para la exhibición avanzada de documentos electrónicos, la funcionalidad de reconocimiento óptico de caracteres (OCR) extrae automáticamente el texto de las imágenes e incluye esto con los resultados de la búsqueda que se cargan en EDiscovery avanzado para el análisis. OCR es compatible con archivos sueltos, datos adjuntos de correo electrónico e imágenes incrustadas. Esto le permite aplicar las capacidades de análisis de texto de eDiscovery avanzado (casi duplicados, subprocesamiento de correo electrónico, temas y codificación de predicción) al contenido de texto de los archivos de imagen. EDiscovery avanzado el OCR admite los siguientes formatos para los archivos de imagen:

    - GIF
    - JPEG
    - JPEG
    - PNG
    - TIFF
    
- **Detección de casi duplicados** : le permite estructurar la revisión de los datos de forma más eficaz, por lo que una persona revisa un grupo de documentos similares. Esto ayuda a evitar que varios revisores tengan que ver diferentes versiones del mismo documento. 
    
- **Subprocesamiento de correo electrónico** : le ayuda a identificar los mensajes únicos en un subproceso de correo electrónico para que pueda centrarse solo en la nueva información de cada mensaje. En una cadena de correo electrónico, el segundo mensaje contiene el primer mensaje. Del mismo modo, los mensajes posteriores contienen todos los mensajes anteriores. El subprocesamiento de correo electrónico elimina la necesidad de revisar todos los mensajes en un hilo de correo electrónico. 
    
- **Temas** : Ayude a obtener información valiosa sobre sus datos más allá de las estadísticas de búsqueda de palabras clave. Los temas ayudan a las investigaciones mediante la agrupación de documentos relacionados para que pueda ver los documentos en contexto. Al usar los temas, puede ver los temas relacionados de un conjunto de documentos, determinar cualquier solapamiento y, a continuación, identificar las secciones cruzadas de los datos relacionados. 
    
- **Codificación predictiva** : le permite entrenar al sistema sobre lo que está buscando, permitiéndole tomar decisiones (sobre si algo es relevante o no) en un pequeño conjunto de documentos. EDiscovery avanzado aplicará ese aprendizaje (en función de las instrucciones) al analizar todos los documentos del conjunto de datos. Basándose en ese aprendizaje, la exhibición avanzada de documentos electrónicos proporciona una clasificación de relevancia para que pueda decidir qué documentos se deben revisar en función del documento que sea más probable que sea relevante para el caso. 
    
- **Exportar datos para las aplicaciones de revisión** : puede exportar datos de eDiscovery avanzado y Office 365 una vez que haya completado el análisis y reducido el conjunto de datos. El paquete de exportación incluye un archivo CSV que contiene las propiedades de los metadatos de contenido y análisis exportados. Este paquete de exportación se puede importar a una aplicación de revisión de eDiscovery. 
    
## <a name="before-you-begin"></a>Antes de empezar

- Para analizar los datos de un usuario con la exhibición avanzada de documentos electrónicos, el usuario (el custodio de los datos) debe tener asignada una licencia de Office 365 E5. Como alternativa, se puede asignar una licencia independiente de eDiscovery avanzado a los usuarios con una licencia de Office 365 E1 o E3. Los administradores y los responsables de cumplimiento que se asignan a los casos y usan la exhibición avanzada de documentos electrónicos para analizar los datos no necesitan una licencia E5. 
    
- Debe ser administrador de exhibición de documentos electrónicos o administrador de exhibición de documentos electrónicos en &amp; el centro de seguridad y cumplimiento de Office 365 para preparar los resultados de búsqueda para la exhibición avanzada de documentos electrónicos. Un administrador de exhibición de documentos electrónicos es miembro del grupo de roles eDiscovery Manager. Un administrador de eDiscovery también es miembro del grupo de roles eDiscovery Manager, pero se le han asignado privilegios de exhibición de documentos electrónicos adicionales. Para obtener instrucciones sobre cómo asignar permisos de administrador de eDiscovery, vea el paso 1 de [los casos de eDiscovery en el centro de seguridad _AMP_ cumplimiento de Office 365](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).
    
## <a name="step-1-prepare-search-results-for-advanced-ediscovery"></a>Paso 1: preparar los resultados de búsqueda para la exhibición avanzada de documentos electrónicos

Puede preparar los resultados de una búsqueda asociada a un caso de exhibición de documentos electrónicos. Al preparar los resultados de búsqueda para la exhibición avanzada de documentos electrónicos, los datos se cargan y se almacenan temporalmente en un área de almacenamiento única de Windows Azure en la nube de Microsoft. En este punto, la funcionalidad OCR extrae el texto de las imágenes de los resultados de búsqueda. En el [paso 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery), este texto y los demás datos de los resultados de la búsqueda se cargan en el caso de la exhibición avanzada de documentos electrónicos.
  
1. En el Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **eDiscovery** para mostrar la lista de casos en su organización. 
    
2. Haga clic en **abrir** junto al caso en el que desea preparar los resultados de búsqueda para el análisis en la exhibición avanzada de documentos electrónicos. 
    
3. En la página **principal** del caso, haga clic en **Buscar**y, a continuación, seleccione la búsqueda.
    
4. En el panel de detalles, en **analizar resultados con exhibición avanzada**de documentos electrónicos, haga clic en **preparar resultados para el análisis**.
    
    > [!NOTE]
    > Si los resultados de la búsqueda son de hace más de 7 días, se le solicitará que actualice los resultados de la búsqueda. 
  
5. En la página **Preparar resultados para el análisis**, haga lo siguiente:  
    
    - Elija si desea preparar elementos indexados, elementos indexados y sin indexar o solo elementos sin indexar para el análisis en la exhibición avanzada de documentos electrónicos.
    
    - Elija si desea incluir todas las versiones de los documentos que se encuentran en SharePoint que cumplen los criterios de búsqueda. Esta opción solo aparece si los orígenes de contenido de la búsqueda incluyen sitios.
    
    - Especifique si desea que un mensaje de notificación se envíe (o se copie) a un usuario cuando se complete el proceso de preparación y los datos estén listos para ser procesados en eDiscovery avanzado.
    
6. Haga clic en **Preparar**.
    
    Los resultados de la búsqueda están preparados para el análisis con eDiscovery avanzado.
    
7. En el panel de detalles, haga clic en **comprobar el estado de preparación** para mostrar información sobre el proceso de preparación. Una vez finalizado el proceso de preparación, puede ir al caso en la exhibición avanzada de documentos electrónicos para procesar los datos para el análisis. 
    
## <a name="step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery"></a>Paso 2: agregar los datos de los resultados de la búsqueda al caso en eDiscovery avanzado
<a name="step2"> </a>

Una vez finalizada la preparación, el siguiente paso es ir a la exhibición avanzada de documentos electrónicos y cargar los datos de los resultados de la búsqueda (que se han cargado en un área de almacenamiento de Azure en la nube de Microsoft) en el caso de la exhibición avanzada de documentos electrónicos. Como se ha explicado anteriormente, para tener acceso a eDiscovery avanzado, debe ser administrador de &amp; eDiscovery en el centro de seguridad y cumplimiento o un administrador en eDiscovery avanzado.
  
> [!NOTE]
> El tiempo que tardan los datos del centro de &amp; cumplimiento de seguridad en estar disponible para agregar a un caso en eDiscovery avanzado varía en función del tamaño de los resultados de la búsqueda de exhibición de documentos electrónicos. 
  
1. En el Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **eDiscovery** para mostrar la lista de casos en su organización. 
    
2. Haga clic en **abrir** junto al caso en el que desea cargar datos en la exhibición avanzada de documentos electrónicos. 
    
3. En la **página principal** del caso, haga clic en **eDiscovery avanzado**. 
    
    ![Haga clic en cambiar a exhibición avanzada de documentos electrónicos para abrir el caso en eDiscovery avanzado.](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    Se muestra la barra de progreso **conectarse a la exhibición avanzada de** documentos electrónicos. Cuando está conectado a la exhibición avanzada de documentos electrónicos, se muestra una lista de contenedores en la página de configuración del caso. 
    
    ![El caso se muestra en la exhibición avanzada de documentos electrónicos](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     Estos contenedores representan los resultados de búsqueda que ha preparado para el análisis en la exhibición avanzada de documentos electrónicos en el paso 1. Tenga en cuenta que el nombre del contenedor tiene el mismo nombre que la búsqueda en el caso del centro &amp; de seguridad y cumplimiento. Los contenedores de la lista son los que ha preparado. Si un usuario diferente ha preparado los resultados de búsqueda para la exhibición avanzada de documentos electrónicos, los contenedores correspondientes no se incluirán en la lista. 
    
4. Para cargar los datos de resultados de búsqueda de un contenedor en el caso de eDiscovery avanzado, seleccione un contenedor y, a continuación, haga clic en **procesar**.
    
## <a name="next-steps"></a>Pasos siguientes

Una vez que se agregan los resultados de una búsqueda de exhibición de documentos electrónicos a un caso, el siguiente paso consiste en usar las herramientas avanzadas de eDiscovery para analizar los datos e identificar el contenido que responde a un caso legal específico. Para obtener información sobre el uso de la exhibición avanzada de documentos electrónicos, vea [Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md).
  
## <a name="more-information"></a>Más información

Los mensajes de correo electrónico cifrados con RMS que se incluyan en los resultados de la búsqueda se descifrarán cuando los prepare para el análisis en la exhibición avanzada de documentos electrónicos. Esta capacidad de descifrado está habilitada de forma predeterminada para los miembros del grupo de roles eDiscovery Manager. Esto se debe a que el rol de administración desCifrar RMS se asigna a este grupo de roles. Tenga en cuenta lo siguiente en lo que se recifran los mensajes de correo electrónico:
  
- Actualmente, esta capacidad de descifrado no incluye contenido cifrado de sitios de SharePoint y OneDrive para la empresa. Cuando se exportan, solo se descifrarán los mensajes de correo electrónico cifrados con RMS.
    
- Si un mensaje de correo electrónico cifrado con RMS tiene datos adjuntos (como un documento u otro mensaje de correo electrónico) que también están cifrados, solo se descifrará el mensaje de correo electrónico de nivel superior.
    
- Si necesita impedir que un usuario descifre mensajes cifrados con RMS al preparar los resultados de búsqueda para analizarlos en eDiscovery avanzado, tendrá que crear un grupo de roles personalizado (copiando el grupo de roles integrado eDiscovery Manager) y, a continuación, quitar el RMS DesCifrar el rol de administración del grupo de roles personalizado. A continuación, agregue la persona que no desea que descifre los mensajes como miembro del grupo de roles personalizado.

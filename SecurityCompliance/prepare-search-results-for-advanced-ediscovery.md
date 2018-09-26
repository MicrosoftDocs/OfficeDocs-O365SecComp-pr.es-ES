---
title: Preparar los resultados de búsqueda para la exhibición avanzada de documentos electrónicos de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/10/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportWithZoom
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 0b6fac2d-8627-4b05-9df0-03609db6248b
description: Obtenga información sobre cómo preparar los resultados de una búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento para realizar un análisis con la herramienta de exhibición de documentos electrónicos avanzadas.
ms.openlocfilehash: f5b10ac7fcfa67f67618c936000832b9bdb7d533
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038313"
---
# <a name="prepare-search-results-for-office-365-advanced-ediscovery"></a>Preparar los resultados de búsqueda para la exhibición avanzada de documentos electrónicos de Office 365

Después de una búsqueda en la que está asociado con un caso de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento se ejecuta correctamente, puede preparar los resultados de búsqueda para realizar un análisis con Office 365 avanzada exhibición de documentos electrónicos, que permite analizar grandes, datos no estructurados establecen y reducen la cantidad de datos que es relevantes para un caso legal. Las características de exhibición de documentos electrónicos avanzada incluyen:
  
- **Reconocimiento óptico de caracteres** - cuando se preparan los resultados de búsqueda avanzada exhibición de documentos electrónicos, la funcionalidad de reconocimiento óptico de caracteres (OCR) automáticamente extrae el texto de imágenes y se incluye con los resultados de búsqueda que se cargan en a Exhibición de documentos electrónicos avanzada para el análisis. Reconocimiento óptico de caracteres es compatible con archivos sueltos, datos adjuntos de correo electrónico e imágenes incrustadas. Esto permite aplicar las capacidades de texto analítico de eDiscovery avanzada (cerca de duplicados, subprocesos de correo electrónico, los temas y codificación predictivo) para el contenido de texto en los archivos de imagen. 
    
- **Detección de casi duplicados** - le permite estructurar la revisión de datos de forma más eficaz, por lo que una persona revisa un grupo de documentos similares. Esto ayuda a evitar que varios revisores tener que ver las diferentes versiones del mismo documento. 
    
- **Correo electrónico threading** - le ayudará a identificar los mensajes en un subproceso de correo electrónico únicos por lo que puede centrarse en sólo la información nueva en cada mensaje. En un subproceso de correo electrónico, el segundo mensaje contiene el primer mensaje. Del mismo modo, los mensajes posteriores contienen todos los mensajes anteriores. Subprocesos de correo electrónico, quitan la necesidad de revisar todos los mensajes en su totalidad en un subproceso de correo electrónico. 
    
- **Los temas** - le ayudarán a obtener información valiosa acerca de los datos más allá de sólo las estadísticas de búsqueda de palabra clave. Los temas ayudan a investigaciones mediante la agrupación de documentos relacionados para que puedan ver los documentos en contexto. Cuando el uso de temas, puede ver los temas relacionados para un conjunto de documentos, determinar cualquier superposición y, a continuación, identificar secciones de datos relacionados. 
    
- **Codificación predictivo** - permite a entrenar al sistema en lo está buscando, por lo que le permite tomar decisiones (sobre si algo es relevante o no) en un conjunto reducido de documentos. Exhibición de documentos electrónicos avanzada, a continuación, aplica esa aprendizaje (según su orientación) al análisis de todos los documentos en el conjunto de datos. En función de ese aprendizaje, exhibición de documentos electrónicos avanzada proporciona una clasificación de relevancia para que pueda decidir qué documentos para revisar en función de qué documento tienen más probabilidades de ser relevantes para el caso. 
    
- **Exportar datos para revisión las aplicaciones** - puede exportar datos de exhibición de documentos electrónicos avanzada y Office 365 después de haber completado el análisis y reduce el conjunto de datos. El paquete de exportación incluye un archivo CSV que contiene las propiedades desde el contenido exportado y los metadatos de análisis. Este paquete de exportación, a continuación, se puede importar a una aplicación de revisión de exhibición de documentos electrónicos. 
    
## <a name="before-you-begin"></a>Antes de empezar

- Para analizar los datos de un usuario mediante la exhibición de documentos electrónicos avanzada, el usuario (la custodia de los datos) debe estar asignado una licencia de Office 365 E5. Como alternativa, se pueden asignar una licencia independiente de exhibición de documentos electrónicos avanzada a los usuarios con una licencia de Office 365 E1 o E3. Los administradores y responsables del cumplimiento normativo que se asignan a los casos y utilizan eDiscovery avanzada para analizar datos no necesitan una licencia de E5. 
    
- Tiene que ser un administrador de exhibición de documentos electrónicos o un administrador de la seguridad de Office 365 de exhibición de documentos electrónicos &amp; centro de cumplimiento para preparar los resultados de búsqueda de exhibición de documentos electrónicos avanzada. Un administrador de exhibición de documentos electrónicos es un miembro del grupo de roles de administrador de exhibición de documentos electrónicos. Una exhibición de documentos electrónicos administrador también es miembro del grupo de roles de administrador de exhibición de documentos electrónicos, pero se ha asignado privilegios de exhibición de documentos electrónicos adicionales. Para obtener instrucciones acerca de cómo asignar permisos de administrador de exhibición de documentos electrónicos, vea el paso 1 en [los casos de exhibición de documentos electrónicos en el centro de cumplimiento y seguridad de Office 365](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).
    
## <a name="step-1-prepare-search-results-for-advanced-ediscovery"></a>Paso 1: Preparar los resultados de la exhibición de documentos electrónicos avanzada de búsqueda

Puede preparar los resultados de una búsqueda en la que está asociado con un caso de exhibición de documentos electrónicos. Al preparar los resultados de búsqueda para la exhibición de documentos electrónicos avanzada, los datos se cargan y almacena temporalmente en un área de almacenamiento de Windows Azure único en la nube de Microsoft. En este punto es que la funcionalidad de reconocimiento óptico de caracteres extrae el texto de las imágenes en los resultados de búsqueda. En [paso 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery), el texto y la búsqueda de otra datos de los resultados se cargan en el caso de exhibición de documentos electrónicos avanzada.
  
1. En el Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **eDiscovery** para mostrar la lista de casos en su organización. 
    
2. Junto al caso de que se va a preparar los resultados de búsqueda para el análisis de exhibición de documentos electrónicos avanzada, haga clic en **Abrir** . 
    
3. En la página **principal** para el caso, haga clic en **Buscar**y, a continuación, seleccione la búsqueda.
    
4. En el panel de detalles, en **los resultados de analizar con eDiscovery avanzada**, haga clic en **los resultados de la preparación para el análisis**.
    
    > [!NOTE]
    > Si los resultados de la búsqueda son de hace más de 7 días, se le solicitará que actualice los resultados de la búsqueda. 
  
5. En la página **Preparar resultados para el análisis**, haga lo siguiente:  
    
    - Elija esta opción para preparar los elementos indizados, elementos indizados y no indizados o sólo los elementos sin indizar para el análisis de exhibición de documentos electrónicos avanzada.
    
    - Elija si desea incluir todas las versiones de los documentos que se encuentra en SharePoint que cumple los criterios de búsqueda. Esta opción aparece únicamente si los orígenes de contenido para la búsqueda incluye sitios.
    
    - Especifique si desea que un mensaje de notificación enviado (o copia) a una persona cuando se complete el proceso de preparación y los datos están listos para ser procesado en la exhibición de documentos electrónicos avanzada.
    
6. Haga clic en **Preparar**.
    
    Los resultados de búsqueda estén preparados para análisis con avanzadas exhibición de documentos electrónicos.
    
7. En el panel de detalles, haga clic en **Comprobar estado de preparación** para mostrar información acerca del proceso de preparación. Cuando finalice el proceso de preparación, puede ir al caso de exhibición de documentos electrónicos avanzada para procesar los datos para su análisis. 
    
## <a name="step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery"></a>Paso 2: Agregar los datos de los resultados de búsqueda para el caso de exhibición de documentos electrónicos avanzada
<a name="step2"> </a>

Cuando finalice la preparación, el siguiente paso es ir a la exhibición de documentos electrónicos avanzada y cargar los datos de los resultados de búsqueda (que se han cargado en un área de almacenamiento de Azure en la nube de Microsoft) en el caso de exhibición de documentos electrónicos avanzada. Como ya se explica, para tener acceso a la exhibición de documentos electrónicos avanzada tiene que ser un administrador en la seguridad de exhibición de documentos electrónicos &amp; centro de cumplimiento o un administrador de exhibición de documentos electrónicos avanzada.
  
> [!NOTE]
> El tiempo necesario para los datos de la seguridad &amp; centro de cumplimiento para que estén disponibles para agregar a un caso de exhibición de documentos electrónicos avanzada varía según el tamaño de los resultados de la búsqueda de exhibición de documentos electrónicos. 
  
1. En el Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **eDiscovery** para mostrar la lista de casos en su organización. 
    
2. Junto al caso de que se desea cargar los datos en a en la exhibición de documentos electrónicos avanzada, haga clic en **Abrir** . 
    
3. En la **página principal** del caso, haga clic en **eDiscovery avanzado**. 
    
    ![Haga clic en cambiar para exhibición de documentos electrónicos avanzada para abrir el caso de exhibición de documentos electrónicos avanzada](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    Se muestra la barra de progreso **que se conectan a la exhibición de documentos electrónicos avanzada** . Cuando está conectado a la exhibición de documentos electrónicos avanzada, se muestra una lista de contenedores en la página del programa de instalación para el caso. 
    
    ![Se muestra el caso de exhibición de documentos electrónicos avanzada](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     Estos contenedores representan los resultados de búsqueda que ha preparado para el análisis de exhibición de documentos electrónicos avanzada en el paso 1. Tenga en cuenta que el nombre del contenedor tiene el mismo nombre que la búsqueda en el caso de la seguridad &amp; centro de cumplimiento. Los contenedores de la lista son los que ha preparado. Si un usuario diferente preparado los resultados de búsqueda de exhibición de documentos electrónicos avanzada, los contenedores correspondientes no se incluirán en la lista. 
    
4. Para cargar los datos de resultados de búsqueda de un contenedor en el caso de exhibición de documentos electrónicos avanzada, seleccione un contenedor y, a continuación, haga clic en **proceso**.
    
## <a name="next-steps"></a>Pasos siguientes

Después de los resultados de una exhibición de documentos electrónicos búsqueda se agregan a un caso, el siguiente paso consiste en usar las herramientas de exhibición de documentos electrónicos avanzada para analizar los datos e identificar el contenido que responde a un caso legal específico. Para obtener información acerca del uso de exhibición de documentos electrónicos avanzada, vea [Office 365 avanzada exhibición de documentos electrónicos](office-365-advanced-ediscovery.md).
  
## <a name="more-information"></a>Más información

Todos los mensajes de correo electrónico cifrados de RMS que se incluyen en los resultados de búsqueda se descifrarán al prepararse para el análisis de exhibición de documentos electrónicos avanzada. Esta capacidad de descifrado está habilitada de forma predeterminada para los miembros del grupo de roles de administrador de exhibición de documentos electrónicos. Esto es debido a que la función de administración de RMS descifrar se asigna a este grupo de funciones. Tenga en cuenta sobre descifrar mensajes de correo electrónico lo siguiente:
  
- Actualmente, esta capacidad de descifrado no incluye contenido cifrado de SharePoint y OneDrive para sitios de negocio. Solo los mensajes de correo electrónico cifrados de RMS se descifrarán al exportar a ellos.
    
- Si un mensaje de correo electrónico cifrados RMS tiene datos adjuntos (como un documento o en otro mensaje de correo electrónico) también se cifran, se descifrarán sólo el mensaje de correo electrónico de nivel superior.
    
- Si necesita impedir que alguien descifrar mensajes cifrados mediante RMS cuando la preparación de los resultados de búsqueda para el análisis de exhibición de documentos electrónicos avanzada, tendrá que crear un grupo de roles personalizados (copiando el grupo de roles de administrador de exhibición de documentos integrado) y, a continuación, quite el RMS Descifrar la función de administración del grupo de funciones personalizado. A continuación, agregue a la persona que no desea descifrar mensajes como un miembro del grupo de roles personalizados.

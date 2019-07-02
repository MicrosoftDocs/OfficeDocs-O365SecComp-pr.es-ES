---
title: Configuración de la detección de privilegios de clientes de abogado en eDiscovery avanzado
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
description: Participe y use el modelo de detección de privilegios de clientes de abogados para usar la detección de contenido privilegiado basada en aprendizaje de máquina al revisar el contenido en un caso de exhibición avanzada de documentos electrónicos.
ms.openlocfilehash: 16a6a215484c35d20fbe071cac033133270b7ea6
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "34703916"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a>Configuración de la detección de privilegios de clientes de abogado en eDiscovery avanzado

Uno de los aspectos más importantes y costosos de la fase de revisión de cualquier proceso de eDiscovery es la revisión de los documentos para obtener un contenido privilegiado. La exhibición avanzada de documentos electrónicos proporciona detección de contenido privilegiado basada en aprendizaje automático para que este proceso sea más eficaz. Esta característica se denomina *detección de privilegios de cliente de abogado*.

> [!NOTE]
> Debe participar en el modelo de detección de privilegios de cliente de abogado para poder usarlo. Consulte el [paso 1](#step-1-opt-in-to-attorney-client-privilege-detection) para obtener instrucciones.

## <a name="how-does-it-work"></a>¿Cómo funciona?

Cuando se habilita la detección de privilegios de clientes de abogados, el modelo de detección de privilegios de cliente-cliente procesa todos los documentos de un conjunto de revisión cuando se [analizan los datos](analyzing-data-in-review-set.md) del conjunto de revisión. El modelo busca dos cosas:

- Contenido privilegiado: el modelo usa el aprendizaje automático para determinar la probabilidad de que el documento incluya contenido que sea legal por naturaleza.

- Participantes: como parte de la configuración de la detección de privilegios de clientes de abogados, tiene que enviar una lista de abogados para su organización. A continuación, el modelo compara los participantes del documento con la lista de abogados para determinar si un documento tiene al menos un participante del abogado.

El modelo genera las siguientes tres propiedades para cada documento:

- **AttorneyClientPrivilegeScore** : la probabilidad de que el documento sea legal en su naturaleza; los valores de la puntuación están comprendidos entre **0** y **1**.

- **HasAttorney** : esta propiedad se establece en **true** si uno de los participantes del documento aparece en la lista de abogados; de lo contrario, el valor es **false**. El valor también se establece en **false** si la organización no ha cargado una lista de abogados.

- **IsPrivilege** : esta propiedad se establece en **true** si el valor de **AttorneyClientPrivilegeScore** está por encima del umbral *o* si el documento tiene un participante del abogado; de lo contrario, el valor se establece en **false**.

Estas propiedades (y sus valores correspondientes) se agregan a los metadatos de archivo de los documentos en un conjunto de revisión, como se muestra en la siguiente captura de pantalla:

![Abogado-propiedades de privilegio de cliente mostradas en metadatos de archivo](../media/AeDAttorneyClientPrivilegeMetadata.png)

Estas tres propiedades también se pueden buscar dentro de un conjunto de revisión. Para obtener más información, consulte [consultar los datos de un conjunto de revisión](review-set-search.md).

## <a name="set-up-the-attorney-client-privilege-detection-model"></a>Configuración del modelo de detección de privilegios de clientes de abogados

Para habilitar el modelo de detección de privilegios de clientes de abogados, su organización tiene que optar y, a continuación, cargar una lista de abogados.

### <a name="step-1-opt-in-to-attorney-client-privilege-detection"></a>Paso 1: participar en la detección de privilegios de clientes y abogados

Como se mencionó anteriormente, el modelo de detección de privilegios de cliente de abogado está en versión preliminar. Por lo tanto, una persona del administrador de eDiscovery de la organización (un miembro del subgrupo de administradores de eDiscovery en el grupo de roles de eDiscovery Manager) debe participar para que el modelo esté disponible en los casos de eDiscovery avanzado.

1. En el centro de seguridad & cumplimiento, vaya a **ediscovery > la exhibición avanzada**de documentos electrónicos.

2. En la Página principal de **EDiscovery avanzado** , en el icono **configuración** , haga clic en **configurar características experimentales**.

   ![Haga clic en "configurar características experimentales"](../media/AeDExperimentalFeatures.png)

3. En la ficha **características experimentales** , haga clic en la **opción administrar privilegios de cliente de abogado**.

4. En la página de control flotante de **privilegios de cliente** , haga clic en el botón de alternancia para activar la característica y, a continuación, haga clic en **Guardar**.

### <a name="step-2-upload-a-list-of-attorneys-optional"></a>Paso 2: cargar una lista de abogados (opcional)

Para sacar el máximo partido del modelo de detección de privilegios de clientes de abogados y clientes que **** se ha descrito **** anteriormente, se recomienda cargar una lista de direcciones de correo electrónico para el Abogados y personal legal que trabajan para su organización. 

Para cargar una lista de abogados para su uso por parte del modelo de detección de privilegios de clientes de abogados:

1. Cree un archivo. csv (sin una fila de encabezado) y agregue la dirección de correo electrónico de cada persona apropiada en una línea independiente. Guarde este archivo en el equipo local.

2. En la Página principal de **EDiscovery avanzado** , en el icono **configuración** , haga clic en **configurar características experimental**y, a continuación, haga clic en **administrar la configuración de privilegios de cliente o abogado**.

   Se muestra la página de **privilegios abogado-Client** y se activa el botón de alternancia **detección de privilegios de clientes o abogados** .

   ![Abogado-página desplegable de privilegios de cliente](../media/AeDUploadAttorneyList.png)

3. Haga clic en **examinar** y, a continuación, busque y seleccione el archivo. csv que creó en el paso 1.

4. Haga clic en **Guardar** para cargar la lista de abogados.

## <a name="use-the-attorney-client-privilege-detection-model"></a>Usar el modelo de detección de privilegios de cliente de abogado

Siga los pasos descritos en esta sección para usar la detección de privilegios de clientes de abogados para documentos en un conjunto de revisión.

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a>Paso 1: crear un grupo de etiquetas inteligentes con un modelo de detección de privilegios de clientes de abogados

Una de las principales formas de ver los resultados de la detección de privilegios de clientes de abogados en el proceso de revisión consiste en usar un grupo de etiquetas inteligentes. Un grupo de etiquetas inteligentes indica los resultados de la detección de privilegios de clientes de abogados y muestra los resultados en línea junto a las etiquetas en un grupo de etiquetas inteligentes. Esto le permite identificar rápidamente los documentos potencialmente privilegiados durante la revisión del documento. Además, también puede usar las etiquetas del grupo de etiquetas inteligentes para etiquetar los documentos como privilegiados o sin privilegios. Para obtener más información acerca de las etiquetas inteligentes, consulte [configurar las etiquetas inteligentes en la exhibición avanzada de](smart-tags.md)documentos electrónicos.

1. En el conjunto de revisiones que contiene los documentos que analizó en el paso 1, haga clic en **administrar conjunto de revisiones** y, a continuación, haga clic en **administrar etiquetas**.
 
2. En **etiquetas**, haga clic en el vínculo desplegable junto a **Agregar grupo** y, a continuación, haga clic en **Agregar grupo de etiquetas inteligentes**.

   ![Haga clic en "Agregar grupo de etiquetas inteligentes"](../media/AeDCreateSmartTag.png)

3. En la página **Elija un modelo para la etiqueta inteligente** , haga clic en **seleccionar** junto a **abogado-Client privilegio**.

   Se muestra un grupo de etiquetas con el **privilegio abogado-Client** . Contiene dos etiquetas secundarias denominadas **positivo** y **negativo**, que corresponden a los posibles resultados generados por el modelo.

   ![Grupo de etiquetas inteligentes abogado-privilegio de cliente](../media/AeDAttorneyClientSmartTagGroup.png)

3. Cambie el nombre del grupo de etiquetas y las etiquetas según corresponda para su revisión. Por ejemplo, puede cambiar el nombre de **positivo** a **privilegiado** y de **negativo** a **no privilegiado**.

### <a name="step-2-analyze-a-review-set"></a>Paso 2: analizar un conjunto de revisión

Al analizar los documentos de un conjunto de revisiones, también se ejecutará el modelo de detección de privilegios de clientes de abogados y las propiedades correspondientes (que se describen en[¿Cómo funciona?](#how-does-it-work) se agregarán a todos los documentos del conjunto de revisión. Para obtener más información acerca del análisis de datos en el conjunto de revisiones, consulte [analizar datos en un conjunto de revisión en EDiscovery avanzado](analyzing-data-in-review-set.md).

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a>Paso 3: usar el grupo de etiquetas inteligentes para revisar el contenido privilegiado

Después de analizar el conjunto de revisión y configurar las etiquetas inteligentes, el siguiente paso es revisar los documentos. Si el modelo ha determinado que el documento tiene potencialmente privilegios, la etiqueta inteligente correspondiente en el **Panel de etiquetado** indicará los siguientes resultados generados por la detección de privilegios de cliente abogado:

- Si el documento tiene contenido que puede ser legal por naturaleza, el **contenido legal** de la etiqueta se muestra junto a la etiqueta inteligente correspondiente (que, en este caso, es la etiqueta **positiva** predeterminada).

- Si el documento tiene un participante que se encuentra en la lista de abogados de la organización, el **abogado** se muestra junto a la etiqueta inteligente correspondiente (que, en este caso, también es la etiqueta **positiva** predeterminada).

- Si el documento tiene contenido que puede ser legal por naturaleza *y* se ha encontrado un participante en la lista de abogados, se muestran las etiquetas de **contenido legal** y **abogados** . 

Si el modelo determina que un documento no tiene contenido legal por naturaleza o que no contiene un participante de la lista de abogados, no se muestra ninguna etiqueta en el panel de etiquetado.

Por ejemplo, en las siguientes capturas de pantallas se muestran dos documentos; el primero incluye contenido que es legal por naturaleza y tiene un participante en la lista de abogados; la segunda contiene ninguno y, por lo tanto, no muestra ninguna etiqueta.

![Documento con etiquetas de abogados y contenido legal](../media/AeDTaggingPanelLegalContentAttorney.png)

![Documento sin etiquetas](../media/AeDTaggingPanelNegative.png)

Después de revisar un documento para ver si contiene contenido privilegiado, puede etiquetar el documento con la etiqueta adecuada.
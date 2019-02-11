---
title: Agregar a custodia a un caso de exhibición de documentos electrónicos avanzada (vista previa)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 88d2e64f4e1fb519955d8970b34e9670fb18d3f8
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706111"
---
# <a name="add-custodians-to-an-advanced-ediscovery-preview-case"></a>Agregar a custodia a un caso de exhibición de documentos electrónicos avanzada (vista previa)

Uso de exhibición de documentos electrónicos avanzada (vista previa), puede aprovechar la herramienta de administración integrada de custodia para coordinar los flujos de trabajo alrededor de administración de custodia y la identificación de los orígenes de datos relevantes, custodia dentro de un caso. Cuando se agrega una custodia, puede identificar automáticamente el sistema y realizar suspensiones en su buzón de Exchange principal y OneDrive para el sitio de negocio. Como dirigir la detección, también es posible que descubrir y asignar los buzones de correo adicionales o sitios que una custodia tener acceso en el pasado o los equipos que una custodia es un miembro de hoy.

Use el siguiente flujo de trabajo para agregar y administrar a custodia en los casos de exhibición de documentos electrónicos avanzada (vista previa) en el centro de cumplimiento de seguridad &. 

## <a name="step-1-identify-potential-custodians"></a>Paso 1: Identificar posible custodia

El primer paso es identificar a la custodia adecuada para su caso. Para agregar a custodia a un caso, debe ser un miembro de la exhibición de documentos electrónicos los administradores o el grupo de roles de administradores de exhibición de documentos electrónicos.   

Para agregar a custodia a un caso de exhibición de documentos electrónicos avanzada (vista previa) existente:

1. Desde la página de **exhibición de documentos electrónicos avanzada (vista previa)** , vaya a su caso.
 
2. Después de haber seleccionado un caso, vaya a la ficha de **custodia** y haga clic en **+ custodia de agregar**. 
 
3. Elija a la custodia que desea agregar a las mayúsculas y minúsculas. Puede iniciar escribiendo para buscar y seleccionar los usuarios de Azure Active Directory su organización.
 
4. Tras finalizar la lista de custodia, haga clic en **siguiente** para comenzar a identificar los posibles orígenes de datos. 
   
## <a name="optional-step-2-select-custodian-data-sources"></a>(Opcional) Paso 2: Seleccione orígenes de datos de custodia

Después de agregar a un caso de custodia, puede sacar provecho de Office 365 para ayudarle a identificar y conservar los orígenes de datos de custodia principal. Es el paso siguiente de este flujo de trabajo seleccionar los orígenes de datos que pertenecen a la custodia especificado en el paso 1. 

Para identificar los orígenes de datos de custodia: 

1. Para cada custodia, seleccione **Exchange** si le gustaría que el sistema para identificar y agregar el buzón principal de la custodia de automáticamente. 
 
2. Para cada custodia, seleccione **OneDrive** si le gustaría que el sistema para identificar automáticamente y agregar principal OneDrive para la dirección URL de la custodia. 

    Una vez haya realizado las selecciones, sistema intentará automáticamente identificar los orígenes de datos y agregarlos a su caso.
 
4. Haga clic en **siguiente** para comenzar la asignación de orígenes de datos adicionales a su custodia.

## <a name="optional-step-3-map-additional-data-sources"></a>(Opcional) Paso 3: Asignar orígenes de datos adicionales

Dependiendo del caso, es posible que desee agregar buzones de correo que es posible que ha usado la custodia determinada en el pasado, grupos donde actualmente es un miembro de custodia o sitios que una custodia tenía acceso a en el pasado. Además de los orígenes de datos principal de custodia, puede agregar otros orígenes de datos de Office 365 a custodia o sacar provecho de Office 365 para ayudar a identificar los orígenes de datos potencialmente relevantes así como. 

Para asignar los buzones de correo, sitios o los equipos a custodia específica:
1. Seleccione la **actualización** para asignar las ubicaciones de contenido, como los buzones de correo, los sitios y de los equipos, a una custodia específica. 

2. En el menú desplegable, especifique lo siguiente:
   
  -  **Los buzones de Exchange** - haga clic en **Elegir usuarios, grupos o equipos** y, a continuación, haga clic en **Elegir usuarios, grupos o equipos de** nuevo. Para especificar los buzones de correo para asignar a la custodia seleccionada, use el cuadro de búsqueda para encontrar buzones de usuario y grupos de distribución. También puede asignar el buzón asociado para un grupo de Office 365 o un Microsoft Team. Seleccione el usuario, el grupo, la casilla de verificación de equipo, haga clic en **Elegir**y, a continuación, haga clic en **Listo**.

      > [!NOTE]
      > Al hacer clic en Elegir usuarios, grupos o equipos para especificar los buzones de correo, el selector de buzón de correo que se muestra está vacío. Este comportamiento está diseñado para mejorar el rendimiento. Para agregar personas a esta lista, escriba un nombre (un mínimo de 3 caracteres) en el cuadro de búsqueda.
     
   - **Sitios de SharePoint** : haga clic en **Elegir sitios** y, a continuación, haga clic en **sitios de elija** nuevo para especificar SharePoint y OneDrive adicionales para sitios de negocio que le gustaría usar para asignar a la custodia seleccionada. También puede agregar la dirección URL del sitio de SharePoint para un grupo de Office 365 o un Microsoft Team. Escriba la dirección URL para cada sitio que desee asignar. Haga clic en **Elegir**y, a continuación, haga clic en **Listo**.
   - **Los equipos de Microsoft** : haga clic en **Elegir los equipos** y, a continuación, haga clic en **Elegir los equipos** de nuevo para ver una lista de grupos de Microsoft Team que la custodia es un miembro de hoy. Seleccione los equipos que le gustaría usar para agregar a su custodia. Una vez seleccionado, el sistema automáticamente identificará seleccionar & que el sitio de SharePoint y el buzón de grupo asociado asociado a ese Microsoft Team. Haga clic en **Elegir**y, a continuación, haga clic en **Listo**.
        
      > [!NOTE]
      > Para agregar adicionales Teams Microsoft, debe agregar por separado el buzón de correo y el sitio de SharePoint como se indicó anteriormente.

Cuando haya terminado de asignación de los orígenes, puede ver el totales buzones, sitios y los equipos para la custodia que acaba de agregar. Cuando haya finalizado los orígenes de datos relevantes de custodia específica, esta asignación se mantiene y extendida para la colección de exhibición de documentos electrónicos, procesamiento y los flujos de trabajo de revisión. 

## <a name="optional-step-4-place-custodians-on-hold"></a>(Opcional) Paso 4: Lugar custodia en espera

 Tras finalizar la custodia y orígenes de datos que desea agregar a su caso, opcionalmente puede colocar algunos o todos los de su custodia en espera. Cuando se realiza una custodia en espera, el contenido asignado a ese usuario se mantiene hasta que se suelte a la custodia desde las mayúsculas y minúsculas o hasta que se elimine la suspensión. En algunos casos, es posible que desee agregar a custodia a un caso sin colocarlos en suspensión. 

Para colocar el seleccionado custodia y orígenes de datos en espera:

1. Compruebe las selecciones de custodia y seleccione el checkox para realizar a cada custodia en espera. Una vez que una custodia se pondrá en espera, se creará automáticamente una directiva de retención de custodia que contiene custodia todos los orígenes. Si la opción no está activada, los orígenes de datos de custodia & seleccionado se agregará a las mayúsculas y minúsculas, pero no se conservará el contenido.

2. Vaya a la ficha **contiene** y seleccione la **Directiva de retención de custodia**. 

3. Haga clic en **Editar** para ver todos los orígenes de datos de custodia seleccionado.

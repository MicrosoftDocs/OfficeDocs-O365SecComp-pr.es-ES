---
title: Trabajar con las comunicaciones de exhibición de documentos electrónicos avanzada (vista previa)
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
ms.openlocfilehash: b27d6cca0382b18123cae4106f77ce0dcdf5e525
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608409"
---
# <a name="working-with-communications-in-advanced-ediscovery-preview"></a>Trabajar con las comunicaciones de exhibición de documentos electrónicos avanzada (vista previa)

Exhibición de documentos electrónicos avanzada (vista previa) permite que los departamentos legales a simplificar sus procesos alrededor de seguimiento y distribución de notificaciones de retención legal. La característica de comunicaciones de custodia permite que los departamentos legales administrar y automatizar sus procesos de retención legal toda--de notificaciones, avisos y escalaciones--todo en un solo lugar.

## <a name="what-is-a-legal-hold-notification"></a>¿Qué es una notificación de retención legal?

Un aviso de retención legal (también conocido como un *litigio suspensión*) es una notificación enviada desde el departamento legal de la organización a los empleados, personal contingente u otro custodia de datos. Estas notificaciones indicar a custodia para conservar la información almacenada electrónicamente (ESI), así como cualquier material que puede ser pertinente para un asunto legal activo o inminente. Equipos legales deben saber que cada custodia ha recibido, leer y entiende y acordados cumplir con las instrucciones proporcionadas.

## <a name="the-legal-hold-notification-process"></a>El departamento jurídico mantenga el proceso de notificación

Una organización tiene un derecho para conservar información relevante cuando aprende una inminente litigio o investigación legales. Con el fin de cumplir con sus requisitos de conservación, la organización debe informar inmediatamente custodia posible sobre su derecho a conservar información relevante. 

Con avanzadas exhibición de documentos electrónicos (vista previa), los equipos legales pueden crear y personalizar su flujo de trabajo de notificación de retención legal. La característica de custodia Communications permite a los equipos legales configurar los siguientes avisos y flujos de trabajo:

1. **Tenga en cuenta emisión**: un aviso de retención legal es emitido (o inició) por una notificación del departamento jurídico de custodia que es posible que tienen información relevante sobre el asunto de mayúsculas y minúsculas. Este aviso indica a esos custodia para conservar cualquier información que podría ser necesarios para la detección. 
   
2.  **Tenga en cuenta re-emisión**: durante un caso, custodia puede requerirse para conservar más o menos información que anteriormente se se le indique. Para este escenario, puede actualizar el aviso de suspensión existente y volver a la asuntos a su custodia.

3.  **Tenga en cuenta versión**: una vez que se resuelve un asunto y la custodia ya no está sujeto a un derecho de conservación, se puede anular la custodia para que la información es ya no se conservan si no sea necesario. Además, su custodia recibirá una notificación que ya no están bajo a un jurado conservación y con pendientes instrucciones acerca de cómo reanudar su actividad.

4. **Avisos y escalaciones**: en algunas instancias, simplemente emitir un aviso no es suficiente para satisfacer los requerimientos de descubrimiento legal. Con cada notificación, los equipos legales pueden programar un conjunto de flujos de trabajo de aviso y escalación automáticamente seguimiento con custodia no responde.

    - **Avisos**: después de haberse emitido un aviso de retención legal o volver a emitir a un conjunto de custodia, una organización puede configurar avisos para custodia no responde de la alerta. 

    - **Escalaciones**: en algunos casos, si una custodia permanece no responde incluso después de un conjunto de avisos, el equipo legal puede configurar un flujo de trabajo de escalación para notificar a la custodia y su administrador.

## <a name="role-groups-and-permissions"></a>Permisos y grupos de roles 

Equipos legales pueden controlar y su actividad de caso con grupos de funciones relacionadas con la exhibición de documentos electrónicos y los permisos en el centro de cumplimiento de seguridad & de segmento. 

Para crear y administrar las notificaciones de retención legal, un usuario debe ser parte de los grupos de roles siguientes:

- **exhibición de documentos electrónicos Manager** - los miembros de este grupo de funciones puede crear y administrar casos de exhibición de documentos electrónicos. Puede agregar y quitar a miembros, coloque custodia y ubicaciones de contenido en espera, administración las notificaciones de retención legal, crean y edición las búsquedas de contenido asociados con un caso, exportación los resultados de una búsqueda de contenido y preparación los resultados de búsqueda para el análisis en Opciones avanzadas exhibición de documentos electrónicos (vista previa). Existen dos subgrupos en este grupo de funciones. La diferencia entre estos subgrupos se basa en el ámbito.

  - **exhibición de documentos electrónicos Manager** - puede ver y administrar los casos de exhibición de documentos electrónicos que creen o están un miembro de. Si la exhibición de documentos electrónicos otro administrador crea un caso, pero no agrega una segunda eDiscovery Manager como un miembro de ese caso, la segunda eDiscovery Manager no podrá ver o abrir el caso en la página de exhibición de documentos electrónicos en el centro de cumplimiento de seguridad &. exhibición de documentos electrónicos los administradores también puede tener acceso a sus casos de exhibición de documentos electrónicos avanzada (vista previa) para realizar tareas de análisis.

  - **exhibición de documentos electrónicos administrador** - puede realizar todas las tareas de administración de casos que puede realizar un administrador de exhibición de documentos electrónicos. Además, un administrador de exhibición de documentos electrónicos puede:
    
    - Ver todos los casos que se enumeran en la página Exhibición de documentos electrónicos.
    - Administrar cualquier caso de la organización después de agregarse ellos mismos como un miembro de las mayúsculas y minúsculas.
    - Acceso a datos de mayúsculas y minúsculas en Avanzadas exhibición de documentos electrónicos (vista previa) para cualquier caso en la organización.

Para obtener más información, vea [asignar permisos de exhibición de documentos electrónicos en el centro de cumplimiento de seguridad de Office 365 &](../assign-ediscovery-permissions.md).
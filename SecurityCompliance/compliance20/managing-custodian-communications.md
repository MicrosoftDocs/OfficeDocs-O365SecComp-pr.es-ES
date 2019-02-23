---
title: Trabajar con comunicaciones en eDiscovery avanzado (versión preliminar)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 92ad9179d5d62fdf25c1ae78e9c367f509bf6ccf
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214260"
---
# <a name="work-with-communications-in-advanced-ediscovery-preview"></a>Trabajar con comunicaciones en eDiscovery avanzado (versión preliminar)

La exhibición avanzada de documentos electrónicos (versión preliminar) permite que los departamentos jurídicos simplifiquen sus procesos en torno al seguimiento y la distribución de notificaciones de retención legal. La característica de comunicaciones de custodios permite a los departamentos legales administrar y automatizar sus procesos de retención legal completos, desde notificaciones, avisos y escalaciones, todo en un mismo punto.

## <a name="what-is-a-legal-hold-notification"></a>¿Qué es una notificación de retención legal?

Un aviso de suspensión legal (también conocido como retención por *juicio*) es una notificación enviada desde el departamento jurídico de una organización a los empleados, el personal contingente u otros custodios de datos. Estas notificaciones indican a los custodios que deben conservar la información almacenada electrónicamente (ESI), así como cualquier material que pueda ser relevante para un asunto legal activo o inminente. Los equipos jurídicos deben saber que cada custodio ha recibido, leído y comprendido, y acordado cumplir con las instrucciones indicadas.

## <a name="the-legal-hold-notification-process"></a>El proceso de notificación de retención legal

Una organización tiene un deber de preservar la información relevante cuando se aprende sobre un litigio inminente o una investigación reguladora. Para cumplir con los requisitos de conservación, la organización debe informar inmediatamente a los custodios de sus obligaciones de preservar la información pertinente. 

Con eDiscovery avanzado (versión preliminar), los equipos legales pueden crear y personalizar el flujo de trabajo de notificación de retención legal. La característica de comunicaciones de custodios permite a los equipos legales configurar los siguientes avisos y flujos de trabajo:

1. **Aviso de emisión**: un aviso de suspensión legal se emite (o inicia) mediante una notificación del departamento jurídico a los custodios que puedan tener información relevante sobre el caso. Este aviso instruye a los custodios para que conserven toda la información que pueda ser necesaria para la detección. 
   
2.  **Aviso de reemisión**: durante un caso, es posible que se necesiten custodios para conservar más o menos información de la que se indicó anteriormente. Para este escenario, puede actualizar el aviso de suspensión existente y volver a enviarlo a los custodios.

3.  **Aviso de publicación**: una vez que se resuelve un problema y el custodio ya no está sujeto a un derecho de preservación, el custodio puede liberarse para que la información deje de conservarse si no es necesario. Además, se notificará a su custodio que ya no se encuentran en el derecho de conservación y con instrucciones pendientes sobre cómo reanudar su actividad.

4. **Avisos y escalaciones**: en algunos casos, solo emitir un aviso no es suficiente para satisfacer los requisitos de detección legales. Con cada notificación, los equipos legales pueden programar un conjunto de flujos de trabajo de Reminder y remisión para realizar un seguimiento automático de los administradores que no responden.

    - **Recordatorios**: una vez que se ha emitido o vuelto a emitir un aviso de suspensión legal a un conjunto de custodios, una organización puede configurar avisos para alertar a los custodios que no responden. 

    - **Escalaciones**: en algunos casos, si un custodio sigue sin responder incluso después de un conjunto de recordatorios, el equipo jurídico puede configurar un flujo de trabajo de escalado para notificar al custodio y a su administrador.

## <a name="role-groups-and-permissions"></a>Grupos de roles y permisos 

Los equipos legales pueden controlar y segmentar su actividad de caso mediante el uso de grupos de roles y permisos relacionados con la exhibición de documentos electrónicos en el centro de seguridad & cumplimiento. 

Para crear y administrar notificaciones de retención legal, un usuario debe formar parte de los siguientes grupos de roles:

- **Administrador de eDiscovery** : los miembros de este grupo de roles pueden crear y administrar casos de eDiscovery. Pueden agregar y quitar miembros, ubicar custodios y ubicaciones de contenido en retención, administrar notificaciones de retención legal, crear y editar búsquedas de contenido asociadas a un caso, exportar los resultados de una búsqueda de contenido y preparar los resultados de la búsqueda para su análisis en opciones avanzadas. eDiscovery (versión preliminar). Hay dos sub-grupos en este grupo de roles. La diferencia entre estos subgrupos se basa en el ámbito.

  - **Administrador de exhibición** de documentos electrónicos: puede ver y administrar los casos de exhibición de documentos electrónicos que crean o de los que son miembros. Si otro administrador de exhibición de documentos electrónicos crea un caso pero no agrega un segundo administrador de eDiscovery como miembro de ese caso, el segundo administrador de eDiscovery no podrá ver ni abrir el caso en la página de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento. los administradores de eDiscovery también pueden tener acceso a sus casos en eDiscovery avanzado (versión preliminar) para realizar tareas de análisis.

  - **Administrador de exhibición** de documentos electrónicos: puede realizar todas las tareas de administración de casos que puede realizar un administrador de exhibición de documentos electrónicos. Además, un administrador de eDiscovery puede:
    
    - Ver todos los casos que se enumeran en la página Exhibición de documentos electrónicos.
    - Administrar cualquier caso en la organización después de que se agreguen como miembro del caso.
    - Obtenga acceso a los datos de caso en eDiscovery avanzado (versión preliminar) para cualquier caso en la organización.

Para obtener más información, vea [asignar permisos de exhibición de documentos electrónicos en el centro de seguridad _AMP_ cumplimiento de Office 365](../assign-ediscovery-permissions.md).
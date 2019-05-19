---
title: Trabajar con comunicaciones en eDiscovery avanzado
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
description: La exhibición avanzada de documentos electrónicos facilita la administración del flujo de trabajo de notificación de retención legal alrededor de los custodios de notificación en investigaciones legales.
ms.openlocfilehash: cf5c8f5e932993255bda2cb959657c2c6ded3163
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154912"
---
# <a name="work-with-communications-in-advanced-ediscovery"></a>Trabajar con comunicaciones en eDiscovery avanzado

EDiscovery avanzado permite que los departamentos jurídicos simplifiquen sus procesos en torno al seguimiento y la distribución de notificaciones de retención legal. La herramienta de comunicaciones de custodios permite a los departamentos jurídicos administrar y automatizar todo el proceso de retención legal, desde notificaciones iniciales hasta avisos y escalaciones, todo en una ubicación.

## <a name="what-is-a-legal-hold-notification"></a>¿Qué es una notificación de retención legal?

Un aviso de suspensión legal (también conocido como retención por *juicio*) es una notificación enviada desde el departamento jurídico de una organización a los empleados, el personal contingente o los custodios de datos que pueden ser relevantes para una investigación legal. Estas notificaciones indican a los custodios que deben conservar la información almacenada electrónicamente, así como cualquier contenido que pueda ser relevante para un asunto legal activo o inminente. Los equipos jurídicos deben saber que cada custodio ha recibido, leído, entendido y ha aceptado cumplir con las instrucciones indicadas.

## <a name="the-legal-hold-notification-process"></a>El proceso de notificación de retención legal

Una organización tiene un deber de preservar la información relevante cuando se aprende sobre un litigio inminente o una investigación reguladora. Para cumplir con los requisitos de conservación de una investigación, la organización debe informar inmediatamente a los posibles custodios sobre su deber de preservar la información pertinente.

Con la exhibición avanzada de documentos electrónicos, los equipos legales pueden crear y personalizar el flujo de trabajo de notificación de retención legal. La herramienta de comunicaciones de custodios permite a los equipos legales configurar los siguientes avisos y flujos de trabajo:

1. **Aviso de emisión**: un aviso de suspensión legal se emite (o inicia) mediante una notificación del departamento jurídico a los custodios que pueden tener información relevante sobre el caso. Este aviso instruye a los custodios para que conserven toda la información que pueda ser necesaria para la detección.
   
2.  **Aviso de reemisión**: durante un caso, es posible que se necesiten custodios para conservar contenido adicional (o menos contenido) del que se solicitó anteriormente. Para este escenario, puede actualizar la notificación de suspensión existente y volver a emitirla para los custodios.

3.  **Aviso de publicación**: una vez que se ha resuelto el problema y el custodio ya no está sujeto a un requisito de preservación, el custodio puede liberarse desde el caso. Además, puede notificar al custodio que ya no es necesario conservar el contenido y proporcionar instrucciones sobre cómo reanudar la actividad de trabajo normal con respecto a sus datos.

4. **Avisos y escalaciones**: en algunos casos, solo emitir un aviso no es suficiente para satisfacer los requisitos de detección legales. Con cada notificación, los equipos legales pueden programar un conjunto de flujos de trabajo de Reminder y remisión para realizar un seguimiento automático de los administradores que no responden.

    - **Recordatorios**: una vez que se ha emitido o vuelto a emitir un aviso de suspensión legal a un conjunto de custodios, una organización puede configurar avisos para alertar a los custodios que no responden.

    - **Escalaciones**: en algunos casos, si un custodio sigue sin responder incluso después de un conjunto de recordatorios durante un período de tiempo, el equipo jurídico puede configurar un flujo de trabajo de escalado para notificar a los custodios que no responden y a su administrador.

## <a name="role-groups-and-permissions"></a>Grupos de roles y permisos 

Los equipos legales pueden controlar y separar su actividad de caso mediante el uso de grupos de roles y permisos relacionados con la exhibición de documentos electrónicos en el centro de seguridad & cumplimiento. 

Para crear y administrar notificaciones de retención legal, un usuario debe formar parte de los siguientes grupos de roles:

- **Administrador de eDiscovery** : los miembros de este grupo de roles pueden crear y administrar casos de eDiscovery. Pueden agregar y quitar miembros, ubicar custodios y ubicaciones de contenido en retención, administrar notificaciones de retención legal, crear y editar búsquedas de contenido asociadas a un caso, exportar los resultados de una búsqueda de contenido y preparar los resultados de la búsqueda para su análisis en opciones avanzadas. exhibición. Existen dos subgrupos en este grupo de roles. La diferencia entre estos subgrupos se basa en el ámbito.

  - **Administrador de exhibición** de documentos electrónicos: puede ver y administrar los casos de exhibición de documentos electrónicos que crean o de los que son miembros. Si otro administrador de exhibición de documentos electrónicos crea un caso pero no agrega un segundo administrador de eDiscovery como miembro de ese caso, el segundo administrador de eDiscovery no podrá ver ni abrir el caso en la página de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento. los administradores de eDiscovery también pueden acceder a sus casos en eDiscovery avanzado para realizar tareas de análisis.

  - **Administrador de exhibición** de documentos electrónicos: puede realizar todas las tareas de administración de casos que puede realizar un administrador de exhibición de documentos electrónicos. Además, un administrador de exhibición de documentos electrónicos puede:
    
    - Ver todos los casos que se enumeran en la página Exhibición de documentos electrónicos.
    - Administrar cualquier caso en la organización después de que se agreguen como miembro del caso.
    - Obtenga acceso a los datos de caso en eDiscovery avanzado para cualquier caso de la organización.

Para obtener más información, vea [asignar permisos de exhibición de documentos electrónicos en el centro de seguridad _AMP_ cumplimiento](../assign-ediscovery-permissions.md).
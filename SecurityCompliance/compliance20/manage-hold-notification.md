---
title: Administrar las notificaciones de retención
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: fa83a90448250a91d6c2ccbf43588ee18e00619c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32241267"
---
# <a name="manage-hold-notifications"></a>Administrar las notificaciones de retención

Una vez que haya iniciado el flujo de trabajo de la notificación de retención legal, puede aprovechar la exhibición avanzada de documentos electrónicos (vista previa) para realizar un seguimiento del estado de sus comunicaciones. La pestaña comunicaciones muestra todas las notificaciones de retención en el caso de la exhibición avanzada de documentos electrónicos (versión preliminar). Aquí puede ver los detalles, como el número de custodios que se han asignado o que han confirmado el aviso.

## <a name="view-communication-details"></a>Ver detalles de comunicación

### <a name="track-acknowledgements"></a>Rastrear confirmaciones

Una vez que seleccione una comunicación en la ficha **comunicaciones**, puede ver una lista de custodios que han confirmado un aviso de retención. 

### <a name="preview-acknowledgements"></a>Vista previa de confirmaciones

En el control flotante comunicación de detalles, puede obtener una vista previa de los detalles de la comunicación de suspensión legal. En el panel **vista previa** , podrá ver una instantánea rápida del aviso de retención legal, así como la configuración y el contenido de las notificaciones de flujo de trabajo. El panel de vista previa también muestra detalles sobre qué custodios ya han confirmado el aviso.

## <a name="taking-action-on-existing-communications"></a>Realizar acciones en las comunicaciones existentes

### <a name="re-send-a-hold-notice"></a>Volver a enviar un aviso de suspensión

En ocasiones, los custodios pierden el seguimiento de sus correos electrónicos en su trabajo cotidiano. O bien, para un litigio de larga duración, un custodio puede ponerse en contacto con usted y pedirle que vuelva a enviar un aviso. Mientras administra el flujo de trabajo en torno a los avisos de suspensión legal, es posible que deba volver a enviar un aviso para volver a colocarlo en la "parte superior del buzón de un usuario".

Puede volver a enviar un aviso de suspensión a su custodio:
1. Navegue a un caso dentro de **seguridad y cumplimiento de _GT_ Advanced eDiscovery (versión preliminar)**.
2. Una vez que haya seleccionado un caso, vaya a la pestaña **comunicaciones** .
3. Para volver a enviar un aviso de suspensión legal a un custodio, seleccione la comunicación y haga clic en la opción **volver a enviar** .
4. Si un custodio todavía no ha reconocido su notificación de retención, se reiniciará el flujo de aviso y escalado. Si un custodio ya ha confirmado el aviso de retenciones, el custodio recibirá una copia del aviso de retenciones inicial.

> [!NOTE]
> Solo se puede volver a enviar una notificación de suspensión legal a los custodios asignados a la comunicación. 

### <a name="edit-a-communication"></a>Editar una comunicación

#### <a name="update-preservation-requirements"></a>Requisitos de conservación de la actualización
  
A medida que avanza el caso, es posible que se necesiten custodios para conservar más o menos datos de los que se indicó anteriormente. En términos de exhibición de documentos electrónicos, debe volver a emitir el aviso de suspensión con contenido actualizado.

Para actualizar el contenido del aviso de suspensión inicial:

1. Navegue a un caso dentro de **seguridad y cumplimiento de _GT_ Advanced eDiscovery (versión preliminar)**.
2. Una vez que haya seleccionado un caso, vaya a la pestaña **comunicaciones** .
3. Seleccione el aviso de retención que quiera actualizar y haga clic en **Editar**.
4. En Editar flujo de trabajo, seleccione **definir contenido del portal** y actualizar el contenido del aviso. 
5. Haga clic en **Guardar **. Una vez guardado, se enviará el aviso de reemisión a todos los custodios que están actualmente asignados a la notificación de retenciones legales. Además, si se habilitan los avisos de aviso/remisión, estos flujos de trabajo también se reiniciarán. 


#### <a name="update-legal-hold-notifications-and-settings"></a>Actualizar la configuración y las notificaciones de retención legal

Cuando se actualiza el contenido o la configuración del aviso de emisión, publicación, reemisión, aviso o escalado, estos cambios se aplican a todas las comunicaciones futuras generadas por el flujo de trabajo.

## <a name="related-information"></a>Información relacionada 

- [Crear un aviso de suspensión legal](create-hold-notification.md)
    
- [Confirmar una notificación de retención](acknowledge-hold-notification.md)
    
- [Agregar administradores a un caso](add-custodians-to-case.md)
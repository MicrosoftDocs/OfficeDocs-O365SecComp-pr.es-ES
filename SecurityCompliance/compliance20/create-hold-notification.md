---
title: Crear un aviso de retención legal
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
ms.openlocfilehash: 8db5a21f60a1d73c11e28bc2765a95c23646115d
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706081"
---
# <a name="create-a-legal-hold-notice"></a>Crear un aviso de retención legal

Con comunicaciones de custodia de exhibición de documentos electrónicos avanzada (vista previa), las organizaciones pueden administrar su flujo de trabajo alrededor de comunicarse con custodia. A través de la herramienta de comunicaciones, los equipos legales sistemáticamente pueden enviar, recopilar y realizar un seguimiento de las notificaciones de retención legal. El proceso de creación flexible también permite a los equipos personalizar el flujo de trabajo de notificación de espera y el contenido en los anuncios enviados a custodia. 

El artículo describe los pasos del flujo de trabajo de notificación de espera.

## <a name="step-1-specify-communication-details"></a>Paso 1: Especificar detalles de comunicación

El primer paso es especificar los detalles adecuados para avisos de retención legal u otras comunicaciones de custodia. 

1. En el centro de cumplimiento de seguridad &, vaya a la **exhibición de documentos electrónicos > avanzada exhibición de documentos electrónicos (vista previa)** para mostrar la lista de casos de la organización.
   
2. Haga clic en la ficha **comunicaciones** y, a continuación, haga clic en **nueva comunicación**.
   
3. En la página de **comunicación de nombre** , especifique los siguientes detalles de comunicación (obligatorio).

    - **Nombre**: éste es el nombre para la comunicación.
    
    - **Responsable de emisión**: la lista desplegable muestra una lista de miembros de mayúsculas y minúsculas. Cada aviso enviado a custodia se van a enviar en nombre del ordenador emisora especificado.

4. Haga clic en **Siguiente**.

## <a name="step-2-define-the-portal-content"></a>Paso 2: Definir el contenido del portal

A continuación, puede crear y agregar el contenido de la notificación de espera. En la página de **contenido del portal de definir** en el Asistente para **crear comunicaciones** , especifique el contenido de la notificación de espera. Este contenido se anexará automáticamente a los avisos de emisión, vuelva a emitir, aviso y escalación. Además, este contenido aparecerá en el Portal de cumplimiento de normas de custodia. 

Para crear el contenido del portal:

1. Tipo (o cortar y paster de otro documento) aviso de la suspensión en el cuadro de edición para el contenido del portal. 

2. Insertar combinación variables en el aviso para personalizar el aviso y compartir el Portal de cumplimiento de normas de custodia.

3. Haga clic en **Siguiente**.

  >[!Tip]
  >Para obtener que más información acerca de cómo puede personalizar el contenido y el formato del contenido del portal, vea [usar el Editor de comunicaciones](using-communications-editor.md).

## <a name="step-3-set-the-required-notifications"></a>Paso 3: Establecer las notificaciones necesarias

Una vez que haya definido el contenido de la notificación de espera, puede configurar los flujos de trabajo alrededor de envío y administración del proceso de notificación. Las notificaciones son mensajes de correo electrónico que se envían a notificar y el seguimiento con custodia. Cada agregado a la comunicación de custodia recibirán la misma notificación. 

Para configurar y enviar un aviso de suspensión, debe incluir la emisión, Re-emisión y las notificaciones de la versión.

### <a name="issuance-notification"></a>Notificación de emisión 

Una vez creada la comunicación, la **Notificación de emisión** se inicia por el ordenador emitir especificado. La notificación de emisión es la primera comunicación enviada a la custodia para informar sobre sus obligaciones de conservación. 

Para crear una notificación de emisión:

1. En el icono de **emisión** , haga clic en **Editar**.
   
2. Si es necesario, agregar miembros casos adicionales o personal para los campos **Cc** y **CCO** . Para agregar varios usuarios a estos campos, separe las direcciones de correo electrónico con un punto y coma.
   
3. Especifique el **asunto** de la notificación (obligatorio).
   
4. Especificar el contenido o las instrucciones adicionales que le gustaría usar para proporcionar a la custodia (obligatorio). Tenga en cuenta que el contenido del portal que haya definido en el paso 2 se agrega al final de la notificación de emisión. 
   
5. Haga clic en **Guardar** 

### <a name="re-issuance-notification"></a>Notificación de emisión de RE 

Medida que avanza el caso, custodia es posible que sea necesario para conservar los datos adicionales o menor que anteriormente se le indique. Después de actualizar el contenido de la notificación de espera, la notificación de emisión de re las alertas a la custodia acerca de los cambios a sus obligaciones de conservación.

Para crear una notificación de emisión de re: 

1. En el mosaico **publicó de nuevo** , haga clic en **Editar**.
   
2. Si es necesario, agregar miembros casos adicionales o personal para los campos **Cc** y **CCO** . Para agregar varios usuarios a estos campos, separe las direcciones de correo electrónico con un punto y coma.
   
3. Especifique el **asunto** de la notificación (obligatorio).
   
4. Especificar el contenido o las instrucciones adicionales que le gustaría usar para proporcionar a la custodia (obligatorio). Tenga en cuenta que el contenido del portal que haya definido en el paso 2 se agrega al final de la notificación de re-emisión.
   
5. Haga clic en **Guardar**.

>[!Note]
>Si se modifica una notificación de espera, la notificación de emisión de re se enviarán automáticamente a todos los custodia asignada para el aviso de. Una vez que se envía la notificación, custodia le pedirá que vuelva a confirmar su aviso de suspensión. Si ha configurado los flujos de trabajo de cualquier aviso o escalación, estos se también volver a iniciar. 

### <a name="release-notification"></a>Notificación de versión

Después de que se resuelve un asunto o si custodia ya no está sujeto a conservar el contenido, puede liberar la custodia de un caso. Si la custodia emitió anteriormente un aviso de suspensión, la notificación de versión puede usarse para custodia de alerta que se han liberado de sus obligaciones.

Para crear una notificación de versión: 

1. En el icono de **versión** , haga clic en **Editar**.
   
2. Si es necesario, agregar miembros casos adicionales o personal para los campos **Cc** y **CCO** . Para agregar varios usuarios a estos campos, separe las direcciones de correo electrónico con un punto y coma.
   
3. Especifique el **asunto** de la notificación (obligatorio).
   
4. Especificar el contenido o las instrucciones adicionales que le gustaría usar para proporcionar a la custodia (obligatorio).
   
5. Haga clic en **Guardar** y vaya al paso siguiente. 

## <a name="optional-step-4-set-the-optional-notifications"></a>(Opcional) Paso 4: Establecer las notificaciones opcionales

De forma opcional, puede simplificar el flujo de trabajo para seguir copia de seguridad con custodia no responde por escalación y aviso automatizada de creación y programación las notificaciones.

### <a name="reminders"></a>Avisos

Una vez ha enviado una notificación de espera, puede seguimiento con custodia no responde mediante la definición de un flujo de trabajo de aviso. 

Para programar avisos:

1. En el icono de **aviso** , haga clic en **Editar**.
   
2. Habilitar el flujo de trabajo de **aviso** al activar la alternancia de **estado** (obligatorio).
   
3. Especifique el **intervalo de aviso (en días)** (obligatorio). Esto es el número de días que se esperará antes de enviar las notificaciones de aviso primera y seguimiento. Por ejemplo, si establece el intervalo de aviso a 7 días, a continuación, el primer aviso se enviará 7 días después de la notificación de espera se emitió inicialmente. Todos los avisos subsiguientes también se enviará cada 7 días.
   
4. Especifique el **número de avisos** (obligatorio). Este campo especifica cuántos avisos para enviar a custodia reactivar con capacidad de respuesta. Por ejemplo, si establece el número de avisos a 3, custodia recibirían un máximo de 3 avisos. Después de custodia reconoce la notificación de la suspensión, ya no se van a enviar los avisos a ese usuario.
   
5. Especifique el **asunto** de la notificación (obligatorio). 
   
6. Especificar el contenido o las instrucciones adicionales que le gustaría usar para proporcionar a la custodia (obligatorio). Tenga en cuenta que el contenido del portal que haya definido en el paso 2 se agrega al final de la notificación de aviso.
   
7. Haga clic en **Guardar** y vaya el paso siguiente.

### <a name="escalations"></a>Escalaciones 

En algunas situaciones, puede ser necesario obtener otras maneras de seguimiento con custodia no responde. Si una custodia no confirmar una notificación de espera después de recibir el número especificado de avisos, el equipo legal puede especificar un flujo de trabajo para enviar automáticamente un aviso de escalación a la custodia y su director.

Para programar extensiones:

1. En el icono de **escalación** , haga clic en **Editar**.
   
2. Habilitar el flujo de trabajo de **escalación** activando la alternancia de **estado** .
   
3. Especifique el **intervalo de escalación (en días)** (obligatorio). 
   
4. Especifique el **número de escalaciones** (obligatorio). Este campo especifica cuántos extensiones para enviar a custodia reactivar con capacidad de respuesta. Por ejemplo, si se establece el número de extensiones en 3, a continuación, un aviso de escalación se enviará a la custodia y su administrador de un máximo de 3 veces. Después de custodia reconoce la notificación de la suspensión, escalaciones ya no se enviarán. 
   
5. Especifique el **asunto** de la notificación (obligatorio). 
   
6. Especificar el contenido o las instrucciones adicionales que le gustaría usar para proporcionar a la custodia (obligatorio). Tenga en cuenta que el contenido del portal que haya definido en el paso 2 se agrega al final de la notificación de escalación.
   
7. Haga clic en **Guardar** y vaya el paso siguiente.
   
## <a name="step-5-assign-custodians"></a>Paso 5: Asignar custodia 

Una vez que haya establecido el contenido para las notificaciones, seleccione la custodia para enviar las notificaciones a. 

Para agregar a custodia:

1. Asignar a custodia a la comunicación haciendo clic en la casilla de verificación junto a su nombre.

    Una vez creada la comunicación, el flujo de trabajo de notificación se aplicará automáticamente a la custodia seleccionado.
   
2. Haga clic en **siguiente** para revisar la configuración de las comunicaciones y los detalles.
 
>[!NOTE]
>Sólo se puede agregar a custodia que se han agregado a las mayúsculas y minúsculas y no han sido enviado otra notificación dentro de las mayúsculas y minúsculas.

## <a name="step-6-review-settings"></a>Paso 6: Configuración de revisión

Después de revisar la configuración y haga clic en **Enviar** para completar la comunicación, el sistema iniciará automáticamente el flujo de trabajo de comunicación mediante el envío de la notificación de emisión.
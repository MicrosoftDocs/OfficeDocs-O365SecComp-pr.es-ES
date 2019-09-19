---
title: Buscar y liberar mensajes en cuarentena como usuario de Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 05/19/2018
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
description: 'Como usuario de Office 365, puede administrar sus propios mensajes en cuarentena o de correo no deseado de dos maneras: respondiendo notificaciones de correo no deseado que se le envíen directamente (si el administrador ha configurado esta característica) o mediante la característica de cuarentena de correo no deseado en el Centro de seguridad y cumplimiento.'
ms.openlocfilehash: 20758876dbfe51f47d66c3c1eef4dcb3cee49768
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854584"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a>Buscar y liberar mensajes en cuarentena como usuario de Office 365

Como usuario de Office 365, puede administrar los mensajes que se pusieron en cuarentena en lugar de recibirlos de dos maneras: [respondiendo a notificaciones de correo no deseado que se le envíen directamente](use-spam-notifications-to-release-and-report-quarantined-messages.md) (si el administrador lo ha configurado) o usando el Centro de seguridad y cumplimiento. 
  
> [!NOTE]
> Si es administrador, puede [administrar mensajes en cuarentena](manage-quarantined-messages-and-files.md) para otros usuarios de su organización. 
  
## <a name="view-messages-that-were-sent-to-quarantine-instead-of-to-you"></a>Ver los mensajes que se han puesto en cuarentena en lugar de recibirlos

1. Inicie sesión en Office 365 y [vaya al Centro de seguridad y cumplimiento](go-to-the-securitycompliance-center.md) usando su cuenta profesional o educativa. 
    
2. A la izquierda, expanda **Administración de amenazas**, elija **Revisión** y luego elija **Cuarentena**.
    
    > [!TIP]
    > Para ir directamente a la página **Cuarentena** del Centro de seguridad y cumplimiento, use esta dirección URL: [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)
  
De forma predeterminada, el Centro de seguridad y cumplimiento muestra todos los mensajes de correo electrónico que se han puesto en cuarentena como correo no deseado. Los mensajes están ordenados de más recientes a más antiguos según la **fecha** en que se recibió el mensaje. **Remitente**, **Asunto** y la fecha de expiración (en **Expira**) también se muestran por cada mensaje. Puede ordenar un campo haciendo clic en el encabezado de la columna correspondiente; haga clic en un encabezado de columna una segunda vez para invertir el criterio de ordenación. 
  
Puede ver una lista de todos los mensajes en cuarentena o puede buscar mensajes específicos filtrando. Solo puede hacer operaciones en masa con un máximo de 100 elementos, los filtros también pueden ayudar a reducir el conjunto de resultados si tiene más de esos. Puede filtrar mensajes por un único motivo de cuarentena rápidamente eligiendo una opción en la lista desplegable. Entre las opciones se incluyen:
  
- Correo identificado como correo no deseado. De forma predeterminada, se muestran los mensajes en cuarentena.
    
- Correo identificado como correo masivo.
    
Cuando encuentre un mensaje en cuarentena específico, haga clic en el mensaje para ver los detalles relacionados con él y realizar acciones. Puede pasar el mensaje a la bandeja de entrada, obtener una vista previa de él, descargarlo o eliminarlo del estado de cuarentena inmediatamente.
  
> [!NOTE]
> Debe tener permisos de administrador en Office 365 para trabajar con mensajes en cuarentena que se enviaron a otros usuarios. 
  
## <a name="to-filter-and-find-quarantined-messages"></a>Para filtrar y buscar mensajes en cuarentena

Si tiene una gran cantidad de elementos en cuarentena, puede reducir el número a un conjunto más manejable con filtros.
  
1. En la página **Cuarentena**, seleccione si desea ver mensajes en cuarentena de **correo no deseado** o **en masa**. 
    
2. En **Ordenar los resultados por**, elija cualquier combinación de condiciones, establezca el filtro adecuado o filtros (no puede usar caracteres comodín en este momento). Hay varias condiciones que puede elegir, incluidas los siguientes:
    
  - **Id. de mensaje** Use esta opción para seleccionar un mensaje específico si conoce el id. de mensaje. 
    
    Por ejemplo, si un usuario de la organización envió un mensaje específico o bien, se le envió un mensaje específico al usuario, y el mensaje nunca llegó al destino, puede buscarlo mediante la característica de seguimiento de mensaje (consulte [Realizar seguimiento de un mensaje y ver resultados](https://go.microsoft.com/fwlink/?LinkId=799737)). Si descubre que el mensaje se envió a cuarentena, quizás porque coincidía con una regla de flujo de correo o se identificó como correo no deseado, lo encontrará fácilmente en estado de cuarentena especificando su id. de mensaje. Asegúrese de incluir la cadena completa de id. de mensaje. Esta podría incluir corchetes angulares (\<\>), por ejemplo:
    
    \<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com\>
    
  - **Dirección de correo electrónico del remitente** Elija filtrar por una única dirección de correo electrónico del remitente. 
    
  - **Dirección de correo electrónico del destinatario** Elija filtrar por una única dirección de correo electrónico del destinatario. 
    
  - **Asunto** Escriba el asunto de una dirección de correo electrónico que desea buscar. 
    
  - **Intervalo de fechas** Puede filtrar por la fecha en que se envió el mensaje a la cuarentena. Puede especificar la fecha o un intervalo de fechas, incluida la hora. 
    
  - **Fecha de expiración** Para filtrar por fecha de expiración, elija **Filtro avanzado**. Puede seleccionar que el mensaje se elimine del estado de cuarentena en las próximas 24 horas (**Hoy**), en las próximas 48 horas (**Próximos 2 días**) o en la próxima semana (**Próximos 7 días**), o puede seleccionar un intervalo de tiempo personalizado.
    
    > [!IMPORTANT]
    > De forma predeterminada, los mensajes de correo no deseado y en masa se conservan en cuarentena durante 30 días. Sin embargo, este período de tiempo es configurable y puede que su administrador haya establecido un período de retención de cuarentena diferente. Cuando Office 365 elimina un mensaje en cuarentena, no puede recuperarlo. 
  
## <a name="view-details-for-a-specific-message"></a>Ver detalles de un mensaje específico

Después de seleccionar un mensaje, verá un resumen de las propiedades del mensaje en un panel del lado derecho de la página.
  
- **Id. de mensaje:** identificador único del mensaje. 
    
- **Dirección del remitente:** persona que envió el mensaje. 
    
- **Recibido:** fecha en que se recibió el mensaje. 
    
- **Asunto:** texto de la línea de asunto del mensaje. 
    
- **Motivo de la cuarentena:** Muestra si un mensaje se ha identificado como **Correo no deseado** o **Masivo**.
    
- **Expira:** fecha en la que se eliminará el mensaje de la cuarentena. 
    
- **Fecha de liberación para:** todas las direcciones de correo electrónico (si corresponde) para las que el mensaje se ha liberado. 
    
- **Todavía no se ha liberado para: **. todas las direcciones de correo electrónico (si corresponde) para las que el mensaje no se ha liberado aún. Puede elegir **Liberar** si desea liberar el mensaje para la bandeja de entrada (más información sobre cómo liberar mensajes en la siguiente sección). 
    
Para obtener más información sobre el mensaje, elija una de las siguientes opciones:
  
- **Ver encabezado del mensaje** Seleccione esta opción para ver el texto del encabezado del mensaje. Copie el texto del encabezado del mensaje en el portapapeles para analizar el encabezado en profundidad y luego elija **Analizador de encabezados de mensaje de Microsoft** para desplazarse hasta el Analizador de conectividad remoto (haga clic y elija Abrir en una nueva pestaña si no desea dejar que Office 365 complete esta tarea). Pegue el encabezado del mensaje en la página de la sección del Analizador de encabezados de mensaje y seleccione Analizar encabezados. 
    
- **Vista previa del mensaje** Le permite ver versiones sin procesar o HTML del texto del cuerpo del mensaje. En la vista HTML, los vínculos se deshabilitan. 
    
## <a name="manage-your-quarantined-messages"></a>Administrar los mensajes en cuarentena

Después de seleccionar un mensaje o un grupo de mensajes, tiene varias opciones para administrar los mensajes en cuarentena.
  
- No hacer nada. Si decide no hacer nada, Office 365 eliminará el mensaje automáticamente al vencimiento. Recuerde que cuando Office 365 elimina un mensaje en cuarentena, no puede recuperarlo.
    
- **Liberar mensaje** Libera un mensaje (o un conjunto de mensajes) en cuarentena para que se envíe a la bandeja de entrada. Cuando libera un mensaje, tiene la opción de enviar el mensaje a Microsoft para analizarlo. 
    
    Si decide enviar un mensaje, también denominado informar de un mensaje como un falso positivo, el mensaje se notifica al Equipo de análisis de correo no deseado de Microsoft. El equipo evalúa y analiza los mensajes de falso positivo y, según los resultados del análisis, puede ajustar las reglas de filtro de contenido de correo no deseado de todo el servicio para dejar pasar estos mensajes.
    
- **Descargar mensaje** Le permite descargar el mensaje como un archivo .eml. Después de descargar un mensaje, puede revisar el archivo .eml con el cliente de correo electrónico antes de liberar el mensaje. 
    
- **Eliminar de cuarentena** Elimina el mensaje inmediatamente del estado de cuarentena sin liberar el mensaje para la bandeja de entrada. 
    


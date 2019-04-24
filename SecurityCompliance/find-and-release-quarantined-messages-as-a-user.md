---
title: Buscar y liberar mensajes en cuarentena como un usuario en Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/19/2018
ms.audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
description: 'Como usuario de Office 365, puede administrar sus propios mensajes de correo no deseado en cuarentena de dos maneras: respondiendo a las notificaciones de correo no deseado que se le envían directamente (si el administrador ha configurado esta característica) o mediante la característica de cuarentena de correo &amp; no deseado en el cumplimiento de seguridad Datacenter.'
ms.openlocfilehash: acbf862f05a9282a26444b738400d29c03d07f1f
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255208"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a>Buscar y liberar mensajes en cuarentena como un usuario en Office 365

Como usuario de Office 365, puede administrar los mensajes que se enviaron a la cuarentena en lugar de enviarlos de dos maneras: respondiendo [a las notificaciones de correo no deseado que se le envían directamente](use-spam-notifications-to-release-and-report-quarantined-messages.md) (si el administrador ha configurado esto) o mediante el &amp; centro de seguridad y cumplimiento. 
  
> [!NOTE]
> Si es administrador, puede [administrar los mensajes en cuarentena](manage-quarantined-messages-and-files.md) para otros usuarios de su organización. 
  
## <a name="view-messages-that-were-sent-to-quarantine-instead-of-to-you"></a>Ver los mensajes que se enviaron a la cuarentena en lugar de a usted

1. Inicie sesión en Office 365 y [vaya al centro de seguridad y cumplimiento](go-to-the-securitycompliance-center.md) con su cuenta profesional o educativa. 
    
2. En la parte izquierda, expanda **Administración de amenazas**, seleccione **revisar**y, a continuación, haga clic **en cuarentena**.
    
    > [!TIP]
    > Para ir directamente a la página **cuarentena** en el centro &amp; de seguridad y cumplimiento, use esta dirección URL: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)
  
De forma predeterminada, el &amp; centro de seguridad y cumplimiento muestra todos los mensajes de correo electrónico que se han puesto en cuarentena como correo no deseado. Los mensajes se ordenan de más reciente a más antiguo en función de la **fecha** en que se recibió el mensaje. El **remitente**, el **asunto**y la fecha de caducidad (en **Expires** ) también se muestran para cada mensaje. Puede ordenar por un campo haciendo clic en el encabezado de columna correspondiente; Haga clic en un encabezado de columna por segunda vez para invertir el criterio de ordenación. 
  
Puede ver una lista de todos los mensajes en cuarentena, o bien puede buscar mensajes específicos mediante filtros. Solo puede realizar operaciones masivas en un máximo de 100 elementos, por lo que el filtrado también puede ayudar a reducir el conjunto de resultados si tiene más de eso. Puede filtrar rápidamente los mensajes por una única razón de cuarentena eligiendo una opción de la lista desplegable. Las opciones son:
  
- Correo identificado como correo no deseado. Estos mensajes en cuarentena se muestran de forma predeterminada.
    
- Correo identificado como correo masivo.
    
Una vez que haya encontrado un mensaje en cuarentena específico, haga clic en el mensaje para ver los detalles del mismo y emprender acciones. Puede liberar el mensaje al buzón de correo, obtener una vista previa del mensaje, descargar el mensaje o eliminar el mensaje de la cuarentena inmediatamente.
  
> [!NOTE]
> Debe tener permisos de administrador en Office 365 para trabajar con los mensajes en cuarentena que se enviaron a otros usuarios. 
  
## <a name="to-filter-and-find-quarantined-messages"></a>Para filtrar y buscar mensajes en cuarentena

Si tiene muchos elementos en cuarentena, puede reducir el número a un conjunto administrable si los filtra.
  
1. En la página **cuarentena** , elija si desea ver los mensajes de **correo electrónico** **masivo** o en cuarentena. 
    
2. En **ordenar resultados por**, elija una combinación de condiciones estableciendo el filtro o filtros apropiados (no se pueden usar caracteres comodín en este momento). Hay varias condiciones que puede elegir, entre las que se incluyen las siguientes:
    
  - **Identificador de mensaje** Use esta para seleccionar un mensaje específico cuando conoce el identificador del mensaje. 
    
    Por ejemplo, si un usuario envía un mensaje específico o está destinado a un usuario de su organización, pero nunca llegó a su destino, puede buscar el mensaje mediante un seguimiento de mensajes (consulte [ejecutar un seguimiento de mensajes y ver los resultados](https://go.microsoft.com/fwlink/?LinkId=799737)). Si descubre que el mensaje se envió a la cuarentena, quizá porque coincidía con una regla de flujo de correo o se identificó como correo no deseado, puede encontrar fácilmente este mensaje en cuarentena especificando su identificador de mensaje. Asegúrese de incluir la cadena completa de Id. de mensaje. Esto puede incluir corchetes angulares\<\>(), por ejemplo:
    
    \<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com\>
    
  - **Dirección de correo electrónico del remitente** Elija filtrar por una sola dirección de correo electrónico del remitente. 
    
  - **Dirección de correo electrónico del destinatario** Elija filtrar por una sola dirección de correo electrónico de destinatarios. 
    
  - **Asunto** Escriba el asunto de la dirección de correo electrónico que desea buscar. 
    
  - **Intervalo de fechas** Puede elegir filtrar por la fecha en la que se envió el mensaje a cuarentena. Puede especificar la fecha o un intervalo de fechas, incluida la hora. 
    
  - **Fecha** de expiración Para filtrar por fecha de expiración, elija **filtro avanzado**. Puede seleccionar mensajes que se eliminarán de la cuarentena en las próximas 24 horas ( **hoy**), en el siguiente 48 horas ( **próximos 2 días**), en la próxima semana ( **próximos 7 días**), o puede seleccionar un intervalo de tiempo personalizado.
    
    > [!IMPORTANT]
    > De forma predeterminada, los mensajes de correo no deseado y masivos se mantienen en cuarentena durante 30 días. Sin embargo, este período de tiempo se puede configurar y es posible que el administrador haya establecido un período de retención de cuarentena diferente. Cuando Office 365 elimina un mensaje de la cuarentena, no puede recuperarlo. 
  
## <a name="view-details-for-a-specific-message"></a>Ver detalles de un mensaje específico

Después de seleccionar un mensaje, verá un resumen de las propiedades del mensaje en un panel del lado derecho de la página.
  
- **Identificador del mensaje:** El identificador único del mensaje. 
    
- **Dirección del remitente:** Quién envió el mensaje. 
    
- **Recibido:** La fecha en que se recibió el mensaje. 
    
- **Asunto:** Texto de la línea de asunto del mensaje. 
    
- **Motivo de cuarentena:** Muestra si un mensaje se ha identificado como **correo no deseado** o **masivo**.
    
- **Expires:** La fecha en la que se eliminará el mensaje de la cuarentena. 
    
- **Lanzado a:** Todas las direcciones de correo electrónico (si las hay) en las que se ha lanzado el mensaje. 
    
- **Todavía no se ha lanzado a:** Todas las direcciones de correo electrónico (si las hay) en las que no se ha lanzado el mensaje. Puede elegir **lanzar** si desea liberar el mensaje en su buzón (más información sobre cómo publicar mensajes en la sección siguiente). 
    
Puede obtener incluso más detalles sobre el mensaje eligiendo una de las siguientes opciones:
  
- **Ver el encabezado del mensaje** Elija esta opción para ver el texto del encabezado del mensaje. Para analizar el encabezado en profundidad, copie el texto del encabezado del mensaje en el portapapeles y, a continuación, elija **analizador de encabezados de mensajes de Microsoft** para ir al analizador de conectividad remota (haga clic con el botón secundario y elija Abrir en una nueva pestaña si no desea dejar Office 365 para completar esta tarea). Pegue el encabezado del mensaje en la página en la sección analizador de encabezados de mensaje y elija analizar encabezados. 
    
- **Vista previa del mensaje** Permite ver versiones RAW o HTML del texto del cuerpo del mensaje. En la vista HTML, los vínculos están deshabilitados. 
    
## <a name="manage-your-quarantined-messages"></a>Administrar los mensajes en cuarentena

Después de seleccionar un mensaje o un grupo de mensajes, tiene varias opciones para administrar los mensajes en cuarentena.
  
- No ejecutar ninguna acción. Si decide no hacer nada, el mensaje será eliminado automáticamente por Office 365 automáticamente tras la expiración. Recuerde que, cuando Office 365 elimina un mensaje de la cuarentena, no puede recuperarlo.
    
- **Liberar mensaje** Liberar un mensaje en cuarentena (o un conjunto de mensajes) para que el mensaje se envíe a su buzón de correo. Al liberar un mensaje, tiene la opción de informar al mensaje a Microsoft para que lo analice. 
    
    Cuando decide informar de un mensaje, también denominado notificar un mensaje como falso positivo, el mensaje se notifica al equipo de análisis de correo no deseado de Microsoft. El equipo evalúa y analiza los mensajes falsos positivos y, según los resultados del análisis, las reglas de filtro de contenido de correo no deseado de todo el servicio pueden ajustarse para permitir el paso de estos mensajes.
    
- **Mensaje de descarga** Permite descargar el mensaje como archivo. eml. Una vez que haya descargado un mensaje, puede revisar el archivo. eml mediante su cliente de correo electrónico antes de publicar el mensaje. 
    
- **Quitar de cuarentena** Elimina el mensaje inmediatamente de cuarentena sin liberar el mensaje al buzón de correo. 
    


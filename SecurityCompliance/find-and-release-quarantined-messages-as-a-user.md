---
title: Buscar y liberar mensajes en cuarentena como un usuario en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/19/2018
ms.audience: Consumer/IW
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
description: 'Como un usuario de Office 365, puede administrar sus propios mensajes en cuarentena de correo no deseado en una de estas dos formas: mediante responde a las notificaciones que se envían directamente de correo no deseado (si el administrador ha configurado esta característica), o mediante la característica de cuarentena de spam en la seguridad &amp; cumplimiento Centro.'
ms.openlocfilehash: 728273838d9e592e17638638258f481830bc0bbe
ms.sourcegitcommit: f7fff49ae0b1c3056faa58d73c1070cb4e638fbf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25018894"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a>Buscar y liberar mensajes en cuarentena como un usuario en Office 365

Como un usuario de Office 365, se pueden administrar los mensajes que se envían a cuarentena en lugar de recibido en una de estas dos formas: [responde a las notificaciones de correo no deseado enviado directamente](use-spam-notifications-to-release-and-report-quarantined-messages.md) (si el administrador ha configurado esta), o mediante la seguridad &amp; centro de cumplimiento. 
  
> [!NOTE]
> Si usted es un administrador, puede [administrar los mensajes en cuarentena](manage-quarantined-messages-and-files.md) para otras personas en su organización. 
  
## <a name="view-messages-that-were-sent-to-quarantine-instead-of-to-you"></a>Ver los mensajes que se envían a cuarentena en lugar de a usted

1. Inicie sesión en Office 365 y [vaya al centro de cumplimiento y seguridad](go-to-the-securitycompliance-center.md) con su cuenta de trabajo o escuela. 
    
2. A la izquierda, expanda **Administración de amenaza**, elija la **revisión**y, a continuación, elija la **cuarentena**.
    
    > [!TIP]
    > Para ir directamente a la página de **cuarentena** en la seguridad &amp; centro de cumplimiento, use esta dirección URL: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)
  
De forma predeterminada, la seguridad &amp; centro de cumplimiento muestra todos los mensajes de correo electrónico que se ha puesto en cuarentena como correo no deseado. Los mensajes se ordenan de más reciente a más antigua en función de la **fecha** que se recibió el mensaje. **Remitente**, el **asunto**y la fecha de caducidad (bajo **Expires** ) también se muestran para cada mensaje. Puede ordenar por un campo haciendo clic en el encabezado de columna correspondiente; Haga clic en un encabezado de columna una segunda vez para invertir el criterio de ordenación. 
  
Puede ver una lista de todos los mensajes en cuarentena, o puede buscar mensajes específicos mediante el filtrado. Sólo se puede realizar operaciones en un máximo de 100 elementos, de forma masiva para el filtrado también puede ayudar a reducir el conjunto de resultados si dispone de más de que. Rápidamente puede filtrar los mensajes por un motivo de la cuarentena único, elija una opción de la lista desplegable. Las opciones incluyen:
  
- Correo identificado como correo no deseado. Estos mensajes en cuarentena se muestran de forma predeterminada.
    
- Correo identificado como correo masivo.
    
Una vez encontrado un mensaje en cuarentena específico, haga clic en el mensaje para ver detalles acerca de él y tomar medidas. Puede liberar el mensaje a su buzón de correo, obtener una vista previa del mensaje, descargue el mensaje o eliminar el mensaje en cuarentena inmediatamente.
  
> [!NOTE]
> Debe tener permisos de administrador en Office 365 para trabajar con los mensajes en cuarentena que se han enviado a otros usuarios. 
  
## <a name="to-filter-and-find-quarantined-messages"></a>Filtrar y buscar los mensajes en cuarentena

Si tiene una gran cantidad de elementos en cuarentena, puede reducir el número a un conjunto fácil de administrar mediante el filtrado de ellos.
  
1. En la página de **cuarentena** , elija si desea ver el **correo no deseado** o **masiva** de los mensajes en cuarentena. 
    
2. En **Ordenar resultados por**, seleccione cualquier combinación de condiciones estableciendo el filtro apropiado o filtros (no se puede usar caracteres comodín en este momento). Hay varias condiciones, que puede elegir, incluidas las siguientes:
    
  - **Identificador de mensaje** Use esta opción para seleccionar un mensaje específico cuando conoce el identificador de mensaje. 
    
    Por ejemplo, si un mensaje específico es enviado por, o está pensado para un usuario en la organización, pero nunca llegado a su destino, se puede buscar para el mensaje mediante el uso de un seguimiento de mensajes (vea [ejecutar un seguimiento de mensajes y los resultados de la vista](https://go.microsoft.com/fwlink/?LinkId=799737)). Si se detectan que se envió el mensaje en cuarentena, quizás porque coincide con una regla de flujo de correo o identificado como correo no deseado, a continuación, encontrará fácilmente este mensaje en cuarentena mediante la especificación de su identificador de mensaje. Asegúrese de incluir la cadena de identificador de mensaje completa. Esto podría incluir entre corchetes angulares (\<\>), por ejemplo:
    
    \<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com\>
    
  - **Dirección de correo electrónico de remitente** Elija esta opción para filtrar por una dirección de correo electrónico de remitente único. 
    
  - **Dirección de correo electrónico del destinatario** Elija esta opción para filtrar por una dirección de correo electrónico del destinatario único. 
    
  - **Asunto** Escriba al asunto de una dirección de correo electrónico que desea buscar. 
    
  - **Intervalo de fechas** Puede filtrar por la fecha en que se envió el mensaje en cuarentena. Puede especificar la fecha o un intervalo de fechas, incluida la hora. 
    
  - **Fecha de caducidad** Para filtrar por fecha de caducidad, elija **filtro avanzado**. Puede seleccionar los mensajes que se eliminará de la cuarentena en las próximas 24 horas ( **hoy**), en las próximas 48 horas ( **2 siguiente días**), dentro de la semana siguiente ( **siguiente 7 días**), o puede seleccionar un intervalo de tiempo personalizado.
    
    > [!IMPORTANT]
    > De forma predeterminada, los mensajes de correo no deseado y masiva se mantienen en cuarentena durante 30 días. Sin embargo, este período de tiempo es configurable y su administración es posible que ha establecido un período de retención de cuarentena diferentes. Cuando Office 365 elimina un mensaje de cuarentena, no puede recuperarlo. 
  
## <a name="view-details-for-a-specific-message"></a>Ver detalles de un mensaje específico

Después de seleccionar un mensaje, verá un resumen de las propiedades del mensaje en un panel en el lado derecho de la página.
  
- **Identificador de mensaje:** El identificador único para el mensaje. 
    
- **Dirección del remitente:** Quién envió el mensaje. 
    
- **Recibido:** La fecha en que se recibió el mensaje. 
    
- **Asunto:** El texto de la línea de asunto en el mensaje. 
    
- **Cuarentena motivo:** Muestra si se ha identificado un mensaje como **correo no deseado** o de **forma masiva**.
    
- **Caduca:** La fecha cuando el mensaje se eliminará de la cuarentena. 
    
- **Publicadas hasta:** Todas las direcciones de correo electrónico (si hay alguno) a la que se ha publicado el mensaje. 
    
- **Aún no se han publicado en:** Todas las direcciones de correo electrónico (si hay alguno) para que no se ha publicado el mensaje. Puede elegir **la versión** si desea liberar el mensaje a su buzón de correo (más información acerca de la liberación de los mensajes en la siguiente sección). 
    
Puede obtener más detalles acerca del mensaje, elija una de las siguientes opciones:
  
- **Encabezado de mensaje de vista** Elija esta opción para ver el texto de encabezado de mensaje. Para analizar el encabezado en profundidad, copie el texto del encabezado de mensaje en el Portapapeles y, a continuación, elija **Del analizador de encabezado de mensaje de Microsoft** para ir al analizador de conectividad remota (el botón secundario y elija Abrir en una nueva ficha si no desea que deje de Office 365 Complete esta tarea). Pegue el encabezado del mensaje en la página en la sección analizador de encabezado de mensaje y elija analizar encabezados. 
    
- **Vista previa de mensaje** Permite ver sin procesar o versiones HTML del texto de cuerpo del mensaje. En la vista HTML, vínculos están deshabilitados. 
    
## <a name="manage-your-quarantined-messages"></a>Administrar los mensajes en cuarentena

Después de seleccionar un mensaje o un grupo de mensajes, dispone de varias opciones para administrar los mensajes en cuarentena.
  
- No haga nada. Si decide no hacer nada, el mensaje se eliminará automáticamente por Office 365 tras la expiración. Recuerde que, cuando Office 365 elimina un mensaje de cuarentena, no puede recuperarlo.
    
- **Mensaje de versión** Liberar un mensaje en cuarentena (o un conjunto de mensajes) para que el mensaje se envía a su buzón de correo. Al liberar un mensaje, tiene la opción de enviar el mensaje a Microsoft para su análisis. 
    
    Cuando elija informar de un mensaje, también denominado informar de un mensaje como falso positivo, el mensaje se notifica al equipo de análisis de correo electrónico no deseado de Microsoft. El equipo evalúa y analiza los mensajes falsos positivos y, dependiendo de los resultados del análisis, se pueden ajustar para permitir que estos mensajes a través de las reglas de filtro de contenido de spam de todo el servicio.
    
- **Descargar mensajes** Le permite descargar el mensaje como un archivo EML. Una vez que se descarga un mensaje, puede revisar el archivo EML con su cliente de correo electrónico antes de liberar el mensaje. 
    
- **Quitar de la cuarentena** Elimina el mensaje inmediatamente de cuarentena sin liberar el mensaje a su buzón de correo. 
    


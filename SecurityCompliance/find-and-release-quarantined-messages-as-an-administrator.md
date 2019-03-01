---
title: Buscar y liberar mensajes en cuarentena como un administrador
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/16/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ab95bf17-bb09-4dd1-9990-ddd02ddecf05
ms.collection:
- M365-security-compliance
description: En este tema se describe cómo los administradores de Exchange Online y Exchange Online Protection (EOP) pueden buscar, liberar e informar sobre los mensajes en cuarentena en el centro de administración de Exchange (EAC).
ms.openlocfilehash: aec067169b343ed186d506ed33c29385a7dc6450
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341791"
---
# <a name="find-and-release-quarantined-messages-as-an-administrator"></a>Buscar y liberar mensajes en cuarentena como un administrador

En este tema se describe cómo los administradores de Exchange Online y Exchange Online Protection (EOP) pueden buscar, liberar e informar sobre los mensajes en cuarentena en el centro de administración de Exchange (EAC). Office 365 dirige los mensajes a la cuarentena ya sea porque se identificaron como correo no deseado o coincidieron con una regla de flujo de correo (también denominada regla de transporte). 
  
Use el centro &amp; de seguridad y cumplimiento en lugar del EAC para completar cualquiera de estas tareas, así como para ver y trabajar con mensajes que se enviaron a cuarentena porque contienen malware. Para obtener más información, vea [cuarentena de mensajes de correo electrónico en Office 365](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).
  
Los mensajes en cuarentena figuran en la página **cuarentena** de EAC. De forma predeterminada, aparecen ordenados del más reciente al más antiguo en el campo **RECIBIDOS**. También se muestran los valores de **REMITENTE**, **ASUNTO** y **EXPIRA** de cada mensaje. Puede ordenar por cualquiera de estos campos haciendo clic en sus encabezados. Si hace clic en un encabezado de columna por segunda vez, se invertirá el orden. La página **cuarentena** puede mostrar como máximo 500 mensajes. 
  
Puede ver una lista de todos los mensajes en cuarentena o puede buscar mensajes concretos especificando criterios de filtros (el filtrado también puede ayudar a reducir el conjunto de resultados si tiene más de 500 mensajes). Después de buscar y localizar un mensaje en cuarentena concreto, puede consultar detalles sobre dicho mensaje. También puede hacer lo siguiente:
  
- Puede liberar el mensaje para un destinatario (o para varios) y, opcionalmente, puede identificar el mensaje como falso positivo (es decir, que no se trata de correo no deseado) al equipo de análisis de correo no deseado de Microsoft, quienes lo evaluarán y analizarán. Según los resultados del análisis, se podrían ajustar las reglas de filtro de contenido de correo no deseado de todo el sistema a fin de permitir que pase el mensaje.
    
- Puede liberar el mensaje y permitir todos los mensajes que el remitente envíe en el futuro.
    
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?
<a name="sectionSection0"> </a>

- Debe tener permisos asignados para poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "cuarentena" en el tema [permisos de características de Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) . 
    
- Puede liberar o informar sobre varios mensajes a la vez en la página **cuarentena**. De forma alternativa, puede crear un script de Windows PowerShell remoto para realizar esta tarea. Use el cmdlet [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) para buscar los mensajes y el cmdlet [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) para liberarlos. 
    
- Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Métodos abreviados de teclado en el Centro de administración de Exchange**.
    
> [!TIP]
> ¿Tiene algún problema? Solicite ayuda en los foros de Exchange. Visite los foros en [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="use-advanced-search-to-filter-and-locate-quarantined-messages"></a>Usar búsqueda avanzada para filtrar y buscar mensajes en cuarentena
<a name="BKMK_UseAdvancedSearchtoFilterMessages"> </a>

En el centro de administración de Exchange (EAC), puede filtrar elementos en cuarentena con base en distintas condiciones mediante la búsqueda avanzada. Puede utilizar estas condiciones por separado o combinadas. La búsqueda proporcionará una lista de los mensajes que cumplen los criterios del filtro.
  
1. En EAC, vaya a **Protección** \> **cuarentena** y, a continuación, haga clic en **Búsqueda avanzada**.
    
2. En la ventana **Búsqueda avanzada**, seleccione cualquier combinación de las condiciones siguientes. Seleccione la casilla de verificación asociada para habilitar cada condición. No se admiten caracteres comodín. 
    
1. **Id. de mensaje** Puede usar este parámetro para realizar una búsqueda de un mensaje específico. Por ejemplo, si un usuario de la organización envió o recibió un mensaje específico, pero el mensaje nunca llegó al destino, puede buscarlo mediante la característica de seguimiento de mensajes. Para más información, consulte [Ejecutar un seguimiento de mensajes y ver los resultados](http://technet.microsoft.com/library/74a9fc59-7e0e-4832-baf9-2a86418b0079.aspx). Si descubre que el mensaje se envió a cuarentena, quizás porque coincidía con una regla o se identificó como correo no deseado, lo encontrará fácilmente en la cuarentena especificando este identificador de mensaje. Asegúrese de incluir la cadena de Id. de mensaje completa. Esto puede incluir corchetes angulares (\<\>). 
    
2. **Dirección de correo electrónico del remitente** Especifique la dirección de correo electrónico de la persona que envió el mensaje. 
    
3. **Dirección de correo electrónico del destinatario** Especifique la dirección de correo electrónico del destinatario del mensaje. 
    
4. **Asunto** Especifique el texto de la línea de asunto del mensaje. 
    
5. **Recibido** Puede seleccionar que el mensaje se recibió en la cuarentena en las últimas 24 horas ( **Hoy**), en las últimas 48 horas ( **Últimos 2 días**), en la última semana ( **Últimos 7 días**), o puede seleccionar un intervalo de tiempo personalizado durante el cual se recibió el mensaje en la cuarentena. 
    
6. **Expira** Puede seleccionar que el mensaje se elimine de la cuarentena en las próximas 24 horas ( **Hoy**), en las próximas 48 horas ( **Próximos 2 días**), en la próxima semana ( **Próximos 7 días**), o puede seleccionar un intervalo de tiempo personalizado en el cual se eliminará el mensaje de la cuarentena.
    
    > [!IMPORTANT]
    > De forma predeterminada, los mensajes en cuarentena de correo no deseado se mantienen en cuarentena durante 15 días, mientras que los mensajes en cuarentena que coinciden con una regla de flujo de correo se mantienen en cuarentena durante 7 días. Después de este período de tiempo, Office 365 elimina los mensajes y no se pueden recuperar. No se puede configurar el período de retención de los mensajes en cuarentena que coinciden con una regla de flujo de correo. Sin embargo, el período de retención de los mensajes de correo no deseado en cuarentena puede reducirse a través de la configuración **conservar el correo no deseado durante (días)** en las directivas de filtro de contenido. Para obtener más información, consulte [configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md). 
  
7. **Tipo** Puede especificar si desea buscar mensajes en cuarentena que se hayan identificado como **correo no deseado**o si desea buscar los mensajes que coinciden con una regla de flujo de correo (**regla de transporte**).
    
3. Haga clic en **Aceptar** para iniciar la ejecución de la búsqueda avanzada. 
    
    > [!NOTE]
    > Para borrar el criterio de búsqueda y ver todos los mensajes de la cuarentena, desactive todas las casillas de la ventana **Búsqueda avanzada** y, a continuación, haga clic en **Aceptar**. 
  
Después de buscar los mensajes, los resultados que coinciden con los criterios especificados se muestran en la interfaz de usuario. El EAC puede mostrar como máximo 500 mensajes. 
  
## <a name="view-details-about-a-specific-quarantined-message"></a>Ver detalles acerca de un mensaje en cuarentena específico
<a name="BKMK_ViewDetailsAboutaSpecificQuarantinedMessage"> </a>

Una vez encontrado un mensaje en cuarentena específico en la página **cuarentena**, puede ver detalles acerca de él. 
  
1. En la página **cuarentena**, seleccione un mensaje específico y, en el panel de detalles de la derecha de la pantalla, aparecerá un resumen de las propiedades de ese mensaje. 
    
    Los valores de **estado del mensaje** son: 
    
  - **Tipo** Indica si el mensaje se ha identificado como **correo no deseado** o si coincide con una regla de flujo de correo (**regla de transporte**).
    
  - **Expira** La fecha en la que se eliminará el mensaje de la cuarentena. 
    
    Los valores de **detalles del mensaje** son: 
    
  - **Remitente** La dirección de correo electrónico de la persona que envió el mensaje. 
    
  - **Asunto** El texto de la línea de asunto del mensaje. 
    
  - **Recibido** La fecha en la que se envió el mensaje a la cuarentena. 
    
  - **Tamaño** El tamaño del mensaje, en kilobytes (KB), o bien, si el tamaño es mayor que 999 KB, en megabytes (MB). 
    
  - **Ver encabezado de mensaje** Haga clic en este vínculo para abrir el cuadro de diálogo **encabezado de mensaje**, que permite ver el texto del encabezado del mensaje. También puede copiar el texto del encabezado del mensaje en el Portapapeles y pegarlo en el [Analizador de encabezados de mensaje](https://testconnectivity.microsoft.com/?tabid=mha). Cuando esté en la herramienta Analizador de encabezados de mensaje, haga clic en **Analizar encabezados** para recuperar la información sobre el encabezado. 
    
    > [!TIP]
    > Para obtener información acerca de los campos de encabezado de mensaje contra correo no deseado específicos que inserta el servicio, consulte [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md). 
  
  - **Vista previa del mensaje de correo electrónico** Haga clic en este vínculo para revisar el texto del mensaje. 
    
2. Si hace doble clic sobre un mensaje en cuarentena, se abre la ventana **Mensaje en cuarentena** y se muestra la información siguiente: 
    
  - **Publicado en** Lista de todas las direcciones de correo electrónico a las cuales se ha publicado el mensaje, si corresponde. 
    
  - **Aún sin publicar a** Lista de todas las direcciones de correo electrónico a las cuales no se ha publicado el mensaje, si corresponde. Puede hacer clic en el vínculo **Publicar para** a fin de publicar el mensaje; para obtener más información sobre cómo liberar un mensaje, consulte la sección siguiente. 
    
  - **Id. de mensaje** El id. de mensaje de Internet (también conocido como id. de cliente) que se encuentra en el encabezado del mensaje. 
    
    Haga clic en **Cerrar** para volver al panel de cuarentena principal. 
    
## <a name="release-messages-from-quarantine"></a>Liberar mensajes en cuarentena
<a name="sectionSection3"> </a>

Si desea liberar los mensajes dirigidos para sus destinatarios, tiene las opciones siguientes:
  
- [Liberar un mensaje en cuarentena y permitir los mensajes que el remitente envíe en el futuro](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessageallowfuturemessagesfromsender)
    
- [Liberar un mensaje en cuarentena para sus destinatarios sin identificarlo como falso positivo](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive)
    
- [Liberar un mensajes en cuarentena (o más) para todos los destinatarios](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipients)
    
- [Liberar un mensaje en cuarentena (o más) para todos los destinatarios e identificarlo como falso positivo](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives)
    
### <a name="release-a-quarantined-message-and-allow-future-messages-from-the-sender"></a>Liberar un mensaje en cuarentena y permitir los mensajes que el remitente envíe en el futuro
<a name="Releasequarantinedmessageallowfuturemessagesfromsender"> </a>

1. En EAC, vaya a **Protección** \> **cuarentena**.
    
2. Haga clic en un mensaje para seleccionarlo y, a continuación, haga clic en el icono **Liberar mensaje** que se muestra en la siguiente pantalla. 
  
![Muestra la página de cuarentena con el icono de liberar mensaje resaltado y con las opciones de liberación.](media/36ee081f-3e30-40c9-8ce3-240cee1970cc.png)
  
Haga clic en **Liberar el mensaje seleccionado y permitir el remitente** en la lista desplegable. 
    
3. Se abrirá el cuadro de diálogo **liberar mensaje y permitir remitente** . Opcionalmente, puede elegir informar del mensaje a Microsoft y, a continuación, hacer clic en **liberar y permitir**. El mensaje se entregará a todos los destinatarios a los que se dirige y se permitirán todos los mensajes futuros de este remitente. Sin embargo, si este mensaje se ha puesto en cuarentena debido a una regla de flujo de correo o a un remitente bloqueado, el remitente seguirá bloqueado para futuros mensajes. 
    
### <a name="release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive"></a>Liberar un mensaje en cuarentena para sus destinatarios sin identificarlo como falso positivo
<a name="Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive"> </a>

1. En EAC, vaya a **Protección** \> **cuarentena**.
    
2. Seleccione un mensaje, haga clic en el icono **Liberar mensaje** y, luego, haga clic en **Liberar mensaje para unos destinatarios específicos** de la lista desplegable. 
    
3. En el cuadro de diálogo **Liberar mensaje**, seleccione una de las siguientes opciones: 
    
  - **Liberar mensaje para todos los destinatarios** Cuando seleccione esta opción, tenga en cuenta que no se puede liberar un mensaje más de una vez para el mismo destinatario. Si un destinatario ya recibió el mensaje, no se lo puede volver a liberar para ese destinatario. 
    
  - **Liberar mensaje para los destinatarios especificados** Seleccione los destinatarios para los que se liberará el mensaje. Dado que el mensaje solamente se puede publicar una vez para cada destinatario, solamente los destinatarios a quienes puede ser publicado aparecen en la lista. Se admite la selección múltiple. Después de seleccionar los destinatarios, haga clic en **agregar**.
    
4. Haga clic en **publicar**. 
    
Si hace clic en el icono **Actualizar**![Icono Actualizar](media/ITPro-EAC-RefreshIcon.gif) para actualizar los datos y, a continuación, hace doble clic en el mensaje, verá que se ha liberado para los destinatarios previstos. 
  
### <a name="release-one-or-more-quarantined-messages-to-all-recipients"></a>Liberar un mensajes en cuarentena (o más) para todos los destinatarios
<a name="Releaseoneormorequarantinedmessagestoallrecipients"> </a>

1. En EAC, vaya a **Protección** \> **cuarentena**.
    
2. Haga clic en un mensaje para seleccionarlo o utilice la tecla MAYÚS para seleccionar varios mensajes. A continuación, haga clic en el icono **Liberar mensaje**. 
    
3. Haga clic en **Liberar los mensajes seleccionados para TODOS los destinatarios** en la lista desplegable. 
    
4. Aparecerá el cuadro de diálogo de advertencia. Lea la advertencia y seleccione **Sí** si desea continuar. Cuando seleccione esta opción, tenga en cuenta que no se puede liberar un mensaje más de una vez para el mismo destinatario. Si un destinatario ya recibió el mensaje, no se puede volver a liberar para ese destinatario. 
    
### <a name="release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives"></a>Liberar un mensaje en cuarentena (o más) para todos los destinatarios e identificarlo como falso positivo
<a name="Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives"> </a>

1. En EAC, vaya a **Protección** \> **cuarentena**.
    
2. Haga clic en un mensaje para seleccionarlo o utilice la tecla MAYÚS para seleccionar varios mensajes. A continuación, haga clic en el icono **Liberar mensaje**. 
    
3. Haga clic en **Liberar los mensajes seleccionados e informar de ellos como falso positivo** en la lista desplegable. 
    
4. Aparecerá el cuadro de diálogo de advertencia. Lea la advertencia y seleccione **Sí** si desea continuar. Cuando seleccione esta opción, tenga en cuenta que no se puede liberar un mensaje más de una vez para el mismo destinatario. Si un destinatario ya recibió el mensaje, no se puede volver a liberar para ese destinatario. 
    
     Cuando se elige esta opción, el mensaje se libera para todos los destinatarios que todavía no lo hayan recibido. Si es un mensaje en cuarentena por correo no deseado, se notificará también al equipo de análisis de correo no deseado de Microsoft, que lo evaluará y analizará. Según los resultados del análisis, se podrían ajustar las reglas de filtro de contenido de correo no deseado de todo el sistema a fin de permitir que pase el mensaje. 
    
> [!TIP]
> Para ayudar a garantizar que un mensaje no se marque como correo no deseado, siga los pasos en [Cómo ayudar a garantizar que un mensaje no se marque como correo no deseado](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md). 
  
Si hace clic en el icono **Actualizar**![Icono Actualizar](media/ITPro-EAC-RefreshIcon.gif) para actualizar los datos y, a continuación, hace doble clic en el mensaje, verá que se ha liberado para los destinatarios previstos. 
  
## <a name="for-more-information"></a>Más información
<a name="sectionSection4"> </a>

[Preguntas más frecuentes sobre la cuarentena](quarantine-faq.md)
  


---
title: Administrar mensajes en cuarentena y los archivos como un administrador en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/05/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
description: 'Como administrador, puede ver, liberar y notificar mensajes en cuarentena de falsos positivos en Office 365. Puede configurar directivas para que Office 365 filtra los mensajes y los envía a cuarentena por varias razones: debido a que se han identificado como spam, masiva, suplantación de identidad, malware, o porque coincide con una regla de flujo de correo. '
ms.openlocfilehash: 1a0aa0b3f08b18d81b6e1e025e5672ab8fcfafa4
ms.sourcegitcommit: 204fb0269b5c10b63941055824e863d77e3e9b02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2018
ms.locfileid: "27180890"
---
# <a name="manage-quarantined-messages-and-files-as-an-administrator-in-office-365"></a>Administrar mensajes en cuarentena y los archivos como un administrador en Office 365

Como administrador, puede ver, la versión y eliminar los mensajes en cuarentena e informe mensajes falsos positivos en cuarentena en Office 365. También puede ver, descargar y eliminar los archivos en cuarentena capturados por anticipado amenaza protección (ATP) para SharePoint Online, OneDrive para la empresa y Microsoft Teams. Puede configurar directivas para que Office 365 filtra los mensajes y los envía a cuarentena por varias razones: debido a se han identificado como correo no deseado, correo masivo, correo de suplantación de identidad, que contiene el malware, o porque coincide con una regla de flujo de correo.
  
De forma predeterminada, Office 365 envía los mensajes de suplantación de identidad y mensajes que contengan malware directamente en cuarentena. Otros mensajes filtrados se envían a la carpeta de correo no deseado de los usuarios a menos que configure una directiva para enviarlos a cuarentena.
  
Debe tener permisos de administrador en Office 365 para trabajar con los mensajes en cuarentena que se han enviado a otros usuarios y para trabajar con archivos en cuarentena.
  
> [!IMPORTANT]
> De forma predeterminada, correo no deseado, masiva, malware, suplantación de identidad y los mensajes que se han puesto en cuarentena debido a que coincide con una regla de flujo de correo se mantienen en cuarentena durante 30 días. Puede personalizar el tiempo de cuarentena en la configuración contra correo no deseado en la seguridad &amp; centro de cumplimiento. Cuando Office 365 elimina un mensaje de cuarentena, no puede recuperarlo. Si lo desea, puede cambiar el período de retención de mensajes en cuarentena en sus directivas de filtro contra correo no deseado. Para obtener más información, vea [establecer el período de retención de cuarentena](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime) , en este artículo. 
  
## <a name="view-your-organizations-quarantined-messages"></a>Ver los mensajes en cuarentena de su organización

1. Uso de una cuenta de trabajo o escuela que tiene privilegios de administrador global de la organización de Office 365, inicie sesión en Office 365 y [vaya al centro de cumplimiento y seguridad](go-to-the-securitycompliance-center.md).
    
2. En la lista de la izquierda, expanda **Administración de amenaza**, elija la **revisión**y, a continuación, elija la **cuarentena**.
    
    > [!TIP]
    > Para ir directamente a la página de **cuarentena** en la seguridad &amp; centro de cumplimiento, use esta dirección URL: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)
  
    De forma predeterminada, la seguridad &amp; centro de cumplimiento muestra todos los mensajes de correo electrónico que se ha puesto en cuarentena como correo no deseado. Los mensajes se ordenan de más reciente a más antigua en función de la **fecha** que se recibió el mensaje. **Remitente**, el **asunto**y la fecha de caducidad (bajo **Expires** ) también se muestran para cada mensaje. Puede ordenar por un campo haciendo clic en el encabezado de columna correspondiente; Haga clic en un encabezado de columna una segunda vez para invertir el criterio de ordenación. 
    
3. Puede ver una lista de todos los mensajes en cuarentena, o puede reducir el conjunto de resultados mediante el filtrado. Sólo se puede realizar operaciones en un máximo de 100 elementos, de forma masiva para el filtrado también puede ayudar a reducir el conjunto de resultados si dispone de más de que. Puede filtrar rápidamente mensajes por un motivo de la cuarentena único eligiendo una opción desde el filtro en la parte superior de la página. Las opciones incluyen:
    
  - Correo identificado como correo no deseado
    
  - Correo en cuarentena debido a que coincidió con una directiva establecida por una regla de flujo de correo (también denominada una regla de transporte)
    
  - Correo identificado como correo masivo
    
  - Correo identificado como correo de suplantación de identidad
    
  - Correo en cuarentena porque contiene malware
    
Además, como administrador, puede elegir filtrar todos los mensajes para su organización o sólo los mensajes enviados a usted. Finalizar los usuarios sólo puedan ver y trabajar con los mensajes enviados para ellos.
  
También puede filtrar los resultados para buscar mensajes específicos. Para obtener sugerencias, vea [filtrar los resultados y buscar archivos y mensajes en cuarentena](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) en este artículo. 
  
Una vez encontrado un mensaje en cuarentena específico, haga clic en el mensaje para ver detalles acerca de él y realizar acciones, como soltar el mensaje al buzón de otra persona.
  
## <a name="view-your-organizations-quarantined-files"></a>Ver archivos en cuarentena de su organización

1. Con una cuenta de trabajo o escuela que tiene privilegios de administrador global de la organización de Office 365, inicie sesión en Office 365 y [vaya a la seguridad y el centro de cumplimiento](go-to-the-securitycompliance-center.md).
    
2. A la izquierda, expanda **Administración de amenaza**, elija la **revisión**y, a continuación, elija la **cuarentena**. <br/>
    > [!TIP]
    > Para ir directamente a la página de **cuarentena** en la seguridad &amp; centro de cumplimiento, use esta dirección URL: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)
  
3. De forma predeterminada, la página muestra los mensajes de correo electrónico en cuarentena. Para ver los archivos en cuarentena, establecer los filtros en la parte superior de la página para mostrar **los archivos**, puesto en cuarentena debido a **malware**. Debe tener permisos de administrador en Office 365 para trabajar con archivos en cuarentena. 
    
4. Los archivos se ordenan de más reciente a más antigua según la fecha en que el archivo se puso en cuarentena. El **usuario** que por última vez modificado el archivo, el **servicio** al que se ha registrado el archivo, el **Nombre de archivo**, la **ubicación**, el **Tamaño de archivo**, y también se muestran la fecha de caducidad ( **Expires**) para cada archivo. Puede ordenar por un campo haciendo clic en un encabezado; Haga clic en un encabezado de columna una segunda vez para invertir el criterio de ordenación.
    
Puede ver una lista de todos los archivos en cuarentena, o puede buscar archivos específicos mediante el filtrado. Al igual que los mensajes, sólo se puede realizar operaciones en hasta 100 elementos de forma masiva. Actualmente, la seguridad &amp; centro de cumplimiento le permite ver y administrar los archivos que están en cuarentena debido a que se hayan identificado como que contiene el malware. Para obtener sugerencias, vea [filtrar los resultados y buscar archivos y mensajes en cuarentena](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) en este artículo. 
  
## <a name="to-filter-results-and-find-quarantined-messages-and-files"></a>Para filtrar los resultados y buscar archivos y mensajes en cuarentena
<a name="BKMK_AdvSearch"> </a>

Dependiendo de la configuración, puede haber una gran cantidad de mensajes en cuarentena y los archivos. Para buscar un mensaje específico o un archivo o un conjunto de mensajes o archivos, puede filtrar los elementos en cuarentena en una gran variedad de información adicional.
  
1. En la página de **cuarentena** , asegúrese de que la fila superior de filtros está configurada para mostrar mensajes o archivos según corresponda: 
    
      - Para buscar archivos, defina los filtros para mostrar **los archivos** en cuarentena debido a **malware**.<br/>
    Para los archivos en cuarentena, la página muestra en cuarentena todos los archivos, no sólo su propios, independientemente de qué indicar a TI para mostrar.
    
      - Para buscar mensajes en cuarentena, establecer filtros para mostrar **todos los** o **sólo mis** **correo electrónico**. Para el último filtro elegir al tipo de mensaje en cuarentena que busca. Puede buscar los mensajes en cuarentena que se hayan identificado como **spam**, para los mensajes que coincidieron con un flujo de correo o **regla de transporte**, correo **masivo** , correo de **suplantación de identidad** o correo electrónico que contiene el **malware**.
    
2. En **los resultados de la ordenación por**, seleccione el filtro o los filtros que desea utilizar para buscar en las listas de lista desplegable. Las opciones varían en función de si está buscando archivos o mensajes. No se admite caracteres comodín en los campos de búsqueda en este momento.<br/><br/>Para los archivos y mensajes, puede elegir filtrar por la fecha en el mensaje o archivo se envía a cuarentena. Puede especificar la fecha o un intervalo de fechas, incluida la hora. También puede filtrar los resultados de búsqueda por la fecha de caducidad en la que el archivo o el mensaje se eliminará de la cuarentena, o puede usar una combinación de filtros. Para buscar por fecha de caducidad, elija **filtro avanzado**. En **Expires**, puede seleccionar los mensajes que se eliminará de la cuarentena en las próximas 24 horas ( **hoy**), en las próximas 48 horas ( **2 siguiente días**), dentro de la semana siguiente ( **siguiente 7 días**), o puede seleccionar un intervalo de tiempo personalizado.<br/><br/>Para los mensajes, tiene las siguientes opciones adicionales:
    
      - **Identificador de mensaje**. Se usa para identificar un mensaje específico cuando conoce el identificador de mensaje.<br/><br/>Por ejemplo, si un mensaje específico es enviado por, o está pensado para un usuario en la organización, pero nunca llegado a su destino, se puede buscar para el mensaje mediante el uso de un seguimiento de mensajes (vea [ejecutar un seguimiento de mensajes y los resultados de la vista](https://go.microsoft.com/fwlink/?LinkId=799737)). Si se detectan que se envió el mensaje en cuarentena, quizás porque coincide con una regla de flujo de correo o identificado como correo no deseado, a continuación, encontrará fácilmente este mensaje en cuarentena especificando su identificador de mensaje. Asegúrese de incluir la cadena de identificador de mensaje completo. Esto podría incluir entre corchetes angulares (\<\>), por ejemplo:<br/>
    `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`
    
      - **Dirección de correo electrónico del remitente**. Elija esta opción para filtrar por una dirección de correo electrónico de remitente único. 
    
      - **Dirección de correo electrónico del destinatario**. Elija esta opción para filtrar por una dirección de correo electrónico del destinatario único. 
    
      - **Asunto**. Escriba al asunto de una dirección de correo electrónico que desea buscar. Dado que no se admite la búsqueda por comodines, debe usar a todo el tema del mensaje en orden de búsqueda para devolver el mensaje en los resultados. La búsqueda no distingue mayúsculas de minúsculas. 
    
## <a name="view-details-about-quarantined-messages-and-files"></a>Ver detalles acerca de los mensajes en cuarentena y archivos

Cuando se selecciona un elemento mostrado en la lista de cuarentena, verá un resumen de sus propiedades en el panel de **Detalles** en el lado derecho de la seguridad &amp; centro de cumplimiento. 
  
**Detalles que se muestran para los mensajes en cuarentena**
  
- **Identificador de mensaje**. El identificador único para el mensaje. 
    
- **Dirección del remitente**. Quién envió el mensaje. 
    
- **Recibido**. La fecha y hora que se recibió el mensaje. 
    
- **Asunto**. El texto de la línea de asunto del mensaje. 
    
- **Tipo**. Muestra si se ha identificado un mensaje como **Spam**, **masiva**, **phishing**, coincide con una regla de flujo de correo ( **regla de transporte**) o que se identificó como que contiene el **Malware**.
    
- **Expira**. La fecha y la hora cuando el mensaje se eliminarán automáticamente de la cuarentena. 
    
- **Publicada el a**. Todas las direcciones de correo electrónico (si hay alguno) a la que se ha publicado el mensaje. 
    
- **No se ha liberado a**. Todas las direcciones de correo electrónico (si hay alguno) para que el mensaje aún no se han liberado. 
    
 **Detalles que se muestran para los archivos en cuarentena**
  
- **Nombre de archivo** El nombre del archivo en cuarentena. 
    
- **Ruta de acceso del sitio** Dirección URL que define la ubicación del archivo en Office 365. 
    
- **Detectado fecha / hora** La fecha y la hora que se puso en cuarentena el archivo. 
    
- **Expira** La fecha cuando el mensaje se eliminará de la cuarentena. 
    
- **Detectados por** El método utilizado para detectar el malware en el archivo. Esto puede ser ATP (protección contra amenazas avanzada) o motor de protección contra malware de Microsoft. 
    
- **Publicada el** Describe si se ha publicado el archivo. 
    
- **Nombre de malware** Familia y el nombre del malware detectado en el archivo. 
    
- **Identificador de documento** Un identificador único para el documento. 
    
- **Tamaño de archivo** El tamaño del archivo en KB. 
    
- **Organización** Identificador único de la organización en Office 365. 
    
- **Modificado por** La cuenta de trabajo o escuela del usuario que modificó por última vez el archivo. 
    
- **Tamaño de archivo** El tamaño del archivo en KB. 
    
- **Hash SHA256** El valor hash del archivo. Puede utilizar esto para buscar otros almacenes de reputación que es posible que haya o investigar dónde más el archivo podría estar en su entorno. 
    
## <a name="managing-messages-and-files-in-quarantine"></a>Administración de mensajes y archivos en cuarentena
<a name="BKMK_ManageQuarantinedItem"> </a>

Después de seleccionar un mensaje o un grupo de mensajes dispone de varias opciones para administrar los mensajes en cuarentena.
  
- No haga nada. Si decide no hacer nada, el mensaje se eliminará automáticamente por Office 365 tras la expiración. De forma predeterminada, correo no deseado, masiva, malware, suplantación de identidad y los mensajes en cuarentena debido a coincide con una regla de flujo de correo se mantienen en cuarentena durante 30 días. Cuando Office 365 elimina un mensaje de cuarentena, no puede recuperarlo. Si lo desea, puede cambiar el período de retención de mensajes en cuarentena mediante la configuración de la opción de **conservar spam de (días)** en las directivas contra correo no deseadas. Para obtener más información, vea [establecer el período de retención de cuarentena](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime) , en este artículo. 
    
- **Encabezado de mensaje de vista** Seleccione este vínculo para ver el texto del encabezado de mensaje. Para analizar el encabezado en profundidad, copie el texto del encabezado de mensaje en el Portapapeles y, a continuación, elija **Del analizador de encabezado de mensaje de Microsoft** para ir al analizador de conectividad remota (el botón secundario y elija **Abrir en una nueva ficha** si no desea que deje de Office 365 para llevar a cabo esta tarea). Pegue el encabezado del mensaje en la página en la sección analizador de encabezado de mensaje y elija **analizar encabezados**.
    
- **Vista previa de mensaje** Permite ver sin procesar o versiones HTML del texto de cuerpo del mensaje. En la vista HTML, vínculos están deshabilitados. 
    
- **Descargar mensajes** o **descargar el archivo**. Elija esta opción para descargar una copia del mensaje o el archivo al dispositivo local. Debe confirmar que comprende los riesgos asociados con la descarga de los elementos de la cuarentena antes de que se permite para hacerlo. Los mensajes se guardan en formato eml a una carpeta que especifique. Archivos en cuarentena se guardan en su formato original.
    
- **Eliminar** Si lo desea, puede eliminar inmediatamente un elemento puesto en cuarentena (o un conjunto de elementos) en lugar de esperar la fecha de caducidad establecida por Office 365. Para eliminar un mensaje o un archivo, en la lista de cuarentena, seleccione el elemento y, a continuación, elija **Eliminar**. Para eliminar varios elementos a la vez, seleccione la casilla de verificación a la izquierda de los elementos en la lista de cuarentena y, a continuación, en la página **acciones masivas** que aparece, elija **Eliminar mensajes seleccionados** o **eliminar los archivos seleccionados**.
    
- **Versión** Liberar un elemento puesto en cuarentena (o un conjunto de elementos) e informar a Microsoft de los elementos como falso su en cuarentena (falsos positivos). 
    
    Para liberar y notificar un único mensaje o un archivo, en la lista de cuarentena, seleccione el elemento, elija **liberar archivo** o **mensaje**. En la página siguiente, asegúrese de selecciona **los mensajes de informe a Microsoft para su análisis** o **archivos de informes a Microsoft para su análisis** . 
    
    Para liberar varios elementos a la vez, seleccione la casilla de verificación a la izquierda de los elementos en la lista de cuarentena y, a continuación, en la página **acciones masivas** que aparece, elija **liberar archivos** o **mensajes**. En la página siguiente, asegúrese de selecciona **los mensajes de informe a Microsoft para su análisis** o **archivos de informes a Microsoft para su análisis** . 
    
Cuando está liberar los mensajes, debe tener en cuenta lo siguiente:
  
- Cuando se realiza una versión de forma masiva de varios mensajes a la vez, se liberan los mensajes a todos los destinatarios identificados originalmente. Si sólo desea liberar mensajes sólo a determinados destinatarios, debe liberar los mensajes de uno a la vez e identificar a los destinatarios de forma individual.
    
- No se puede liberar un mensaje más de una vez al destinatario de la misma.
    
- Cuando está liberar un mensaje a más de un destinatario, sólo los destinatarios que no han recibido el mensaje anteriormente aparecerán en la lista de posibles destinatarios.
    
- Cuando elija informar de falsos positivos, si el mensaje o mensajes de la versión que se han puesto en cuarentena como spam, masiva, suplantación de identidad, o bien como que contiene el malware, el mensaje también se notificará al equipo de análisis de correo electrónico no deseado de Microsoft. Evaluar el equipo y analizar el mensaje y, dependiendo de los resultados del análisis, se pueden ajustar para permitir que el mensaje a través de las reglas de filtro de contenido de spam de todo el servicio.
    
## <a name="setting-the-quarantine-retention-period"></a>Al establecer el período de retención de cuarentena
<a name="BKMK_ModQuarantineTime"> </a>

Puede configurar cuánto mensajes y archivos permanecerá en cuarentena antes de que expiren. De forma predeterminada, se conservan los elementos en cuarentena durante 30 días. Configure esta opción para cada directiva que cree. También puede modificar el valor de la directiva predeterminada, tal como se describe en este artículo. 
  
### <a name="to-modify-the-quarantine-retention-period-for-the-default-spam-filter-policy-in-the-security-and-compliance-center"></a>Para modificar el período de retención de cuarentena de la directiva de filtro de spam de forma predeterminada en el centro de cumplimiento y seguridad

1. Con una cuenta de trabajo o escuela que tiene privilegios de administrador global de la organización de Office 365, inicie sesión en Office 365 y [vaya a la seguridad y el centro de cumplimiento](go-to-the-securitycompliance-center.md).
    
2. A la izquierda, expanda **Administración de amenaza**, elija la **Directiva**y, a continuación, elija **contra correo no deseado**. <br/>
    > [!TIP]
    > Para ir directamente a la página **contra correo no deseado** en la seguridad &amp; centro de cumplimiento, use esta dirección URL: >[https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)
  
3. Elija **personalizado** para mostrar la ficha **configuración personalizada** . 
    
4. Expanda la fila de la **Directiva de filtro de spam predeterminada (siempre ON)** . 
    
5. Elija **Editar directiva**. La configuración de la directiva de filtro de spam predeterminada aparece en una nueva página.
    
6. Expanda **Spam y acciones de forma masiva**.
    
7. En **cuarentena**, en el cuadro de texto **conservar spam de (días)** , escriba la cantidad de tiempo que desea que Office 365 para conservar los mensajes y archivos en cuarentena. El valor predeterminado es 30 días. Esto también es el máximo. 
    
8. Elija **Guardar**.
    


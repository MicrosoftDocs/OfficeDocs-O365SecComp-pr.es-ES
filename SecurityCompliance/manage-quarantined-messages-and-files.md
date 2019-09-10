---
title: Administrar archivos y mensajes en cuarentena como un administrador en Office 365
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 09/05/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre cómo ver y administrar los mensajes en cuarentena en el centro de seguridad & cumplimiento de Office 365.
ms.openlocfilehash: 0b67abe3dbf21650925b53d2882bc40096d6a646
ms.sourcegitcommit: 81b3bff27bc60235a38004c5b0297ac454331b25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "36822530"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-office-365"></a>Administrar archivos y mensajes en cuarentena como un administrador en Office 365

Como administrador, puede ver, liberar y eliminar mensajes en cuarentena e informar de mensajes falsos positivos en cuarentena en Office 365. También puede ver, descargar y eliminar los archivos en cuarentena capturados por Advance Threat Protection (ATP) para SharePoint Online, OneDrive para la empresa y Microsoft Teams. Puede configurar directivas para que Office 365 filtre mensajes y los envíe a la cuarentena por varias razones: debido a que se identificaron como correo no deseado, correo masivo, correo de suplantación de identidad (phishing), contienen malware o porque coincidieron con una regla de flujo de correo.

De forma predeterminada, Office 365 envía mensajes de suplantación de identidad (phishing) y mensajes que contienen malware directamente a la cuarentena. Otros mensajes filtrados se envían a la carpeta de correo no deseado de los usuarios, a menos que configure una directiva para enviarlos a cuarentena.

Para ver y realizar acciones en mensajes en cuarentena en el centro de seguridad & cumplimiento, su cuenta necesita uno de los siguientes permisos:

**Rol destinatarios con permiso de vista**: ver la lista de mensajes en cuarentena.

**Rol de lector de seguridad**: vea la lista de mensajes en cuarentena y sus encabezados de mensaje.

**Rol de administrador de seguridad**: vea la lista de mensajes en cuarentena y sus encabezados de mensaje; Obtenga una vista previa, libere, elimine y descargue mensajes en cuarentena.

De forma predeterminada, los grupos de funciones administrador de seguridad y administración de la organización en el centro de seguridad & cumplimiento tienen asignado el rol de administrador de seguridad (por lo que la pertenencia a uno de estos grupos de roles le da permisos). Para obtener más información, consulte [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

> [!IMPORTANT]
> De forma predeterminada, los mensajes de correo no deseado, masivos o de suplantación de identidad se mantienen en cuarentena durante 30 días. Los mensajes que se ponen en cuarentena debido a que coinciden con una regla de flujo de correo se mantienen en cuarentena durante 7 días. Los mensajes de malware se mantienen en cuarentena durante 15 días. Puede personalizar el tiempo de cuarentena de correo no deseado en configuración contra correo no deseado en el centro de seguridad & cumplimiento. Cuando Office 365 elimina un mensaje de la cuarentena, no puede recuperarlo. Si lo desea, puede cambiar el período de retención de los mensajes en cuarentena en las directivas de filtro contra correo no deseado. Para obtener más información, consulte la sección [establecer el período de retención de cuarentena](#set-the-quarantine-retention-period) en este tema.

## <a name="view-your-organizations-quarantined-messages"></a>Ver los mensajes en cuarentena de la organización

1. [Abra el centro de seguridad & cumplimiento](go-to-the-securitycompliance-center.md) y vaya a **Threat Management** \> **Review** \> **Quarantine**.

   > [!TIP]
   > Para ir directamente a la página **cuarentena** , use esta dirección URL [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine):.

   De forma predeterminada, el centro de seguridad & cumplimiento muestra todos los mensajes de correo electrónico que se han puesto en cuarentena como correo no deseado. Los mensajes se ordenan de más reciente a más antiguo en función de la **fecha** en que se recibió el mensaje. El **remitente**, el **asunto**y la fecha de caducidad (en **Expires**) también se muestran para cada mensaje. Puede ordenar por un campo haciendo clic en el encabezado de columna correspondiente; Haga clic en un encabezado de columna por segunda vez para invertir el criterio de ordenación.

2. Puede ver una lista de todos los mensajes en cuarentena o puede reducir el conjunto de resultados mediante filtrado. Solo puede realizar operaciones masivas en un máximo de 100 elementos, por lo que el filtrado también puede ayudar a reducir el conjunto de resultados si tiene más de eso. Puede filtrar rápidamente los mensajes por una única razón de cuarentena eligiendo una opción del filtro en la parte superior de la página. Las opciones son:

   - Correo identificado como correo no deseado

   - Correo en cuarentena porque coincidía con una directiva establecida por una regla de flujo de correo (también denominada regla de transporte)

   - Correo identificado como correo masivo

   - Correo identificado como correo de suplantación de identidad

   - Correo en cuarentena porque contiene malware

Como administrador, también puede elegir filtrar todos los mensajes de su organización o solo los mensajes que se le envíen. Los usuarios finales solo pueden ver y trabajar con los mensajes que se les han enviado.

También puede filtrar los resultados para buscar mensajes específicos. Para obtener sugerencias, consulte la sección [filtrar los resultados para buscar mensajes y archivos en cuarentena](#filter-the-results-to-find-quarantined-messages-and-files) en este tema.

Una vez que haya encontrado un mensaje en cuarentena específico, haga clic en el mensaje para ver los detalles del mismo y realice acciones como, por ejemplo, publicar el mensaje en el buzón de una persona.

## <a name="view-your-organizations-quarantined-files"></a>Ver los archivos en cuarentena de la organización

1. [Abra el centro de seguridad & cumplimiento](go-to-the-securitycompliance-center.md) y vaya a **Threat Management** \> **Review** \> **Quarantine**.

   > [!TIP]
   > Para ir directamente a la página **cuarentena** en el centro de seguridad & cumplimiento, use esta dirección URL: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)

   De forma predeterminada, la página muestra los mensajes de correo electrónico en cuarentena. Para ver los archivos en cuarentena, establezca los filtros en la parte superior de la página para mostrar **los archivos**, en cuarentena debido a **malware**.

   Los archivos se ordenan del más reciente al más antiguo en función de la fecha en que el archivo se puso en cuarentena. El **usuario** que modificó el archivo por última vez, el **servicio** al que se publicó el archivo, el **nombre del archivo**, la **Ubicación**, el **tamaño del archivo**y la fecha de caducidad ( **expira**) también se enumeran para cada archivo. Puede ordenar por un campo haciendo clic en un encabezado; Haga clic en un encabezado de columna por segunda vez para invertir el criterio de ordenación.

2. Puede ver una lista de todos los archivos en cuarentena o puede buscar archivos específicos mediante filtros. Al igual que ocurre con los mensajes, solo puede realizar operaciones masivas en un máximo de 100 elementos. Actualmente, el centro de seguridad & cumplimiento le permite ver y administrar los archivos que están en cuarentena porque se han identificado como que contienen malware. Para obtener sugerencias, consulte la siguiente sección.

## <a name="filter-the-results-to-find-quarantined-messages-and-files"></a>Filtrar los resultados para buscar mensajes y archivos en cuarentena

En función de la configuración, es posible que haya muchos archivos y mensajes en cuarentena. Para buscar un mensaje, un archivo o un conjunto de mensajes o archivos específicos, puede filtrar los elementos en cuarentena en función de una amplia variedad de información adicional.

1. En la página **cuarentena** , asegúrese de que la fila superior de filtros esté configurada para mostrar mensajes o archivos según corresponda:

   - Para buscar archivos, establezca los filtros para mostrar **los archivos** en cuarentena debido a **malware**.

     Para los archivos en cuarentena, la página muestra todos los archivos en cuarentena, no solo los suyos, independientemente de lo que indique que se muestre.

   - Para buscar mensajes en cuarentena, establezca filtros para mostrar **todos los** o **solo mi** **correo electrónico**. Para el último filtro, elija el tipo de mensaje en cuarentena que está buscando. Puede buscar mensajes en cuarentena que se hayan identificado como **correo no deseado**en los mensajes que coinciden con una regla de flujo de correo (**regla de transporte**), correo **masivo** , correo de **suplantación de identidad (phishing** ) o correo que contenga **malware**.

2. En **ordenar resultados por**, seleccione el filtro o los filtros que desea usar para la búsqueda en las listas desplegables. Las opciones varían en función de si se está buscando archivos o mensajes. Los caracteres comodín no se admiten en los campos de búsqueda en este momento.

   Para los archivos y los mensajes, puede elegir filtrar por la fecha en la que se envió el mensaje o el archivo a cuarentena. Puede especificar la fecha o un intervalo de fechas, incluida la hora. También puede filtrar los resultados de la búsqueda por la fecha de caducidad en la que se eliminará el archivo o mensaje de la cuarentena, o puede usar una combinación de filtros. Para buscar por fecha de expiración, elija **filtro avanzado**. En **fecha de expiración**, puede seleccionar mensajes que se eliminarán de la cuarentena en las próximas 24 horas ( **hoy**), en el siguiente 48 horas ( **próximos 2 días**), en la próxima semana ( **próximos 7 días**), o puede seleccionar un intervalo de tiempo personalizado.

   Para los mensajes, tiene las siguientes opciones adicionales:

   - **Identificador del mensaje**: Use esta información para identificar un mensaje específico cuando conoce el identificador del mensaje.

     Por ejemplo, si un usuario envía un mensaje específico o está destinado a un usuario de su organización, pero nunca llegó a su destino, puede buscar el mensaje mediante un [seguimiento de mensajes](message-trace-scc.md). Si descubre que el mensaje se envió a la cuarentena, quizá porque coincidía con una regla de flujo de correo o se identificó como correo no deseado, puede encontrar fácilmente este mensaje en cuarentena especificando su identificador de mensaje. Asegúrese de incluir la cadena de identificador de mensaje completa. Esto puede incluir corchetes angulares\<\>(), por ejemplo `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`:.

   - **Dirección de correo electrónico del remitente**: elija esta opción para filtrar por una sola dirección de correo electrónico del remitente.

   - **Dirección de correo electrónico del destinatario**: elija esta opción para filtrar por una sola dirección de correo electrónico de destinatarios.

   - **Asunto**. Escriba el asunto de la dirección de correo electrónico que desea buscar. Dado que no se admite la búsqueda de comodines, debe usar el asunto completo del mensaje para que la búsqueda devuelva el mensaje en los resultados. La búsqueda no distingue mayúsculas de minúsculas.

## <a name="view-details-about-quarantined-messages-and-files"></a>Ver los detalles de los mensajes y archivos en cuarentena

Al seleccionar un elemento que se muestra en la lista de cuarentena, verá un resumen de sus propiedades en el panel de **detalles** de la parte derecha del centro de seguridad & cumplimiento.

### <a name="details-displayed-for-quarantined-messages"></a>Detalles mostrados para los mensajes en cuarentena

- **Identificador del mensaje**: el identificador único del mensaje.

- **Dirección del remitente**: quién envió el mensaje.

- **Received**: la fecha y la hora en que se recibió el mensaje.

- **Subject**: el texto de la línea de asunto del mensaje.

- **Tipo**: muestra si un mensaje se ha identificado como **correo no deseado**, en **masa**, **phish**, coincide con una regla de flujo de correo (**regla de transporte**) o se identificó como **malware**que lo contiene.

- **Expires**: fecha y hora en que el mensaje se eliminará automáticamente de la cuarentena.

- **Lanzado a**: todas las direcciones de correo electrónico (si las hay) en las que se ha lanzado el mensaje.

- **Todavía no se ha lanzado a**: todas las direcciones de correo electrónico (si las hay) en las que el mensaje no se ha lanzado todavía.

### <a name="details-displayed-for-quarantined-files"></a>Detalles mostrados para los archivos en cuarentena

- **Nombre de archivo**: nombre del archivo en cuarentena.

- **Ruta de acceso al sitio**: dirección URL que define la ubicación del archivo en Office 365.

- **Fecha y hora de detección**: la fecha y la hora en que se puso en cuarentena el archivo.

- **Expires**: la fecha en la que se eliminará el mensaje de la cuarentena.

- **Detectado por**: el método que se usa para detectar el malware en el archivo. Puede ser ATP (protección contra amenazas avanzada) o el motor antimalware de Microsoft.

- **Lanzado**: describe si el archivo se ha soltado o no.

- **Nombre del malware**: familia y nombre del malware detectado en el archivo.

- **Identificador de documento**: un identificador único para el documento.

- **Tamaño de archivo**: el tamaño del archivo en KB.

- **Organization**: el identificador único de la organización en Office 365.

- **Modificado por**: la cuenta profesional o educativa del usuario que modificó el archivo por última vez.

- **Tamaño de archivo**: el tamaño del archivo en KB.

- **Hash SHA256**: hash del archivo. Puede usar esto para buscar otros almacenes de reputación que pueda tener o investigar donde, de lo contrario, el archivo puede estar en su entorno.

## <a name="manage-messages-and-files-in-quarantine"></a>Administrar mensajes y archivos en cuarentena

Después de seleccionar un mensaje o un grupo de mensajes en cuarentena, tiene varias opciones para lo que debe hacer con los mensajes:

- No hacer nada: Si decide no realizar ninguna acción, Office 365 se eliminará automáticamente al expirar el mensaje. De forma predeterminada, los mensajes de correo no deseado, masivos, de malware, de suplantación de identidad (phishing) y mensajes en cuarentena porque coinciden con una regla de flujo de correo se mantienen en cuarentena durante 30 días. Cuando Office 365 elimina un mensaje de la cuarentena, no puede recuperarlo. Si lo desea, puede cambiar el período de retención de los mensajes en cuarentena configurando la opción **conservar el correo no deseado durante (días)** en las directivas contra correo no deseado. Para obtener más información, consulte la sección [establecer el período de retención de cuarentena](#set-the-quarantine-retention-period) en este tema.

- **Ver encabezado de mensaje**: haga clic en este vínculo para ver el texto del encabezado del mensaje. Para analizar el encabezado en profundidad, copie el texto del encabezado del mensaje en el portapapeles y, a continuación, elija **analizador de encabezados de mensajes de Microsoft** para ir al analizador de conectividad remota (haga clic con el botón secundario del mouse (ratón) y elija **abrir en una nueva pestaña** si no desea salir de Office 365 para completar esta tarea). Pegue el encabezado del mensaje en la página en la sección analizador de encabezados de mensaje y elija **analizar encabezados**.

- **Vista previa del mensaje**: le permite ver versiones RAW o HTML del texto del cuerpo del mensaje. En la vista HTML, los vínculos están deshabilitados.

- **Descargar mensaje** o **Descargar archivo**: elija esta opción para descargar una copia del mensaje o archivo en el dispositivo local. Tendrás que confirmar que comprendes los riesgos asociados con la descarga de elementos de cuarentena antes de que tengas permiso para hacerlo. Los mensajes se guardan en formato. eml en la carpeta que especifique. Los archivos en cuarentena se guardan en su formato original.

- **Eliminar**: si lo desea, puede eliminar inmediatamente un elemento en cuarentena (o un conjunto de elementos) en lugar de esperar la fecha de expiración establecida por Office 365. Para eliminar un mensaje o un archivo, en la lista cuarentena, seleccione el elemento y, a continuación, elija **eliminar**. Para eliminar varios elementos al mismo tiempo, seleccione la casilla situada a la izquierda de los elementos en la lista cuarentena y, a continuación, en la página **acciones en masa** que aparece, elija **eliminar mensajes seleccionados** o **eliminar archivos seleccionados**.

- **Release**: liberar un elemento en cuarentena (o un conjunto de elementos) e informar de los elementos como falsos en cuarentena (falsos positivos) a Microsoft.

  Para liberar e informar de un solo mensaje o archivo, en la lista de cuarentena, seleccione el elemento, elija **liberar archivo** o **liberar mensaje**. En la página siguiente, asegúrese de que se haya seleccionado **Informe de mensajes a Microsoft para su análisis** o **los archivos de informes de Microsoft para su análisis** .

  Para liberar varios elementos a la vez, seleccione la casilla de verificación situada a la izquierda de los elementos en la lista cuarentena y, a continuación, en la página **acciones en masa** que aparece, elija **liberar archivos** o **liberar mensajes**. En la página siguiente, asegúrese de que se haya seleccionado **Informe de mensajes a Microsoft para su análisis** o **los archivos de informes de Microsoft para su análisis** .

Cuando esté publicando mensajes, tenga en cuenta lo siguiente:

- Cuando se realiza una liberación masiva de varios mensajes a la vez, los mensajes se liberan a todos los destinatarios identificados originalmente. Si solo desea liberar mensajes para destinatarios específicos, debe liberar los mensajes de uno en uno e identificar los destinatarios de forma individual.

- No se puede publicar un mensaje más de una vez para el mismo destinatario.

- Cuando publica un mensaje en más de un destinatario, solo los destinatarios que no recibieron el mensaje aparecerán en la lista de posibles destinatarios.

- Cuando elige informar de falsos positivos, si el mensaje o los mensajes que publica se pusieron en cuarentena como correo no deseado, en masa o en modo de suplantación de identidad (phishing) o como que contiene malware, el mensaje también se notificará al equipo de análisis de correo no deseado de Microsoft. El equipo evaluará y analizará el mensaje y, según los resultados del análisis, las reglas de filtro de contenido de correo no deseado de todo el servicio pueden ajustarse para permitir el paso del mensaje.

## <a name="set-the-quarantine-retention-period"></a>Establecer el período de retención de cuarentena

Puede configurar cuánto tiempo los mensajes y archivos permanecerán en cuarentena antes de que expiren. De forma predeterminada, los elementos en cuarentena se conservan durante 30 días. Configure esta opción para cada directiva que cree. También puede modificar el valor de la directiva predeterminada como se describe en este artículo.

### <a name="modify-the-quarantine-retention-period-for-the-default-spam-filter-policy-in-the-security--compliance-center"></a>Modificar el período de retención de cuarentena para la Directiva de filtro de correo no deseado predeterminada en el centro de seguridad & cumplimiento

1. [Abra el centro de seguridad & cumplimiento](go-to-the-securitycompliance-center.md) y vaya a la **Directiva** \> de **Administración** \> de amenazas **contra correo no deseado**.

   > [!TIP]
   > Para ir directamente a la página **contra el correo no deseado** , use esta dirección URL:[https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)

2. Elija **personalizado** para mostrar la ficha **Configuración personalizada** .

3. Expanda la fila **Directiva de filtro de correo no deseado predeterminada (siempre activa)** .

4. Elija **Editar Directiva**. La configuración de la Directiva de filtro de correo no deseado predeterminada aparece en una página nueva.

5. Expanda **correo no deseado y acciones en masa**.

6. En **cuarentena**, en el cuadro de texto **conservar el correo no deseado durante (días)** , escriba la cantidad de tiempo que desea que Office 365 conserve los mensajes y archivos en cuarentena. El valor predeterminado es 30 días. Este es también el máximo.

7. Elija **Guardar**.

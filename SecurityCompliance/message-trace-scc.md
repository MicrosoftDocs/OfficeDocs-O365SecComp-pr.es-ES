---
title: Seguimiento de mensajes en el centro de cumplimiento de seguridad &
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
description: Los administradores pueden utilizar el seguimiento de mensajes en el centro de cumplimiento de seguridad & para averiguar qué ha sucedido con los mensajes.
ms.openlocfilehash: 9dfdab4adc5caba55664e93b49c8428791670ab3
ms.sourcegitcommit: 25fb33a1f8b2844fde15f6c03db2936c610824e0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2019
ms.locfileid: "28685659"
---
# <a name="message-trace-in-the-security--compliance-center"></a>Seguimiento de mensajes en el centro de cumplimiento de seguridad &

Seguimiento de mensajes en el centro de cumplimiento de seguridad & sigue mensajes de correo electrónico cuando viajan a través de la organización de Exchange Online. Puede determinar si un mensaje se ha recibido, rechazado, aplazado o emitido por el servicio. También se muestran las acciones realizadas en el mensaje antes de alcanzar su estado final.

Seguimiento de mensajes en el centro de cumplimiento de seguridad & mejora con seguimiento de mensajes que estaba disponible en el centro de administración de Exchange (EAC). Puede usar la información de seguimiento de mensajes para responder a preguntas de los usuarios acerca de ¿qué sucedió con sus mensajes de eficazmente, solucionar problemas del flujo de correo y validar los cambios de directiva.

## <a name="open-message-trace"></a>Seguimiento de mensaje abierto

1. [Inicie sesión en Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) con su cuenta profesional o educativa.

2. Seleccione el icono del iniciador de aplicaciones ![Icono del iniciador de aplicaciones de Office 365](media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png) de la esquina superior izquierda y elija **Administrador**.

3. En el panel de navegación inferior izquierda, expanda **centros de administración** y seleccione **& cumplimiento de seguridad**.

4. En la página **& cumplimiento de seguridad** que se abre, expanda el **flujo de correo**y seleccione el **seguimiento de mensajes**.

## <a name="message-trace-page"></a>Página de seguimiento de mensaje

Desde aquí puede iniciar una nueva traza predeterminada haciendo clic en el botón **iniciar un seguimiento** . Realiza una búsqueda de todos los mensajes de todos los remitentes y destinatarios para los dos últimos días. O puede usar una de las consultas almacenadas de las categorías de consulta disponibles y cualquiera ejecutarlas como-es o usarlos como puntos de partida para sus propias consultas:

- **Valor predeterminado de consultas**: consultas integradas proporcionadas por Office 365.

- **Consultas personalizadas**: consultas guardadas por los administradores de la organización para un uso futuro.

- **Las consultas de autoguardado**: los últimos diez recientemente ejecutan consultas. Esta lista hace que sea sencillo recoger donde lo dejó.

También en esta página es una sección **Downloadable informes** para las solicitudes que se ha enviado, así como los informes de ellos mismos cuando hay disponibles para su descarga.

## <a name="options-for-a-new-message-trace"></a>Opciones para un nuevo seguimiento de mensajes

### <a name="filter-by-senders-and-recipients"></a>Filtrar por remitentes y destinatarios

Los valores predeterminados son **todos los remitentes** y **destinatarios**, pero puede usar los siguientes campos para filtrar los resultados:

- **Las siguientes personas**: haga clic en este campo para seleccionar uno o más remitentes de su organización. También puede comenzar a escriba un nombre y los elementos de la lista se filtrarán por lo que ha escrito, mucho al igual que el comportamiento de una página de búsqueda.

- **A estas personas**: haga clic en este campo para seleccionar uno o más destinatarios de la organización.

También puede escribir las direcciones de correo electrónico de los remitentes externos y los destinatarios. Se admite caracteres comodín (`*@contoso.com` o `scot?@contoso.com`), pero no se puede usar varias entradas de comodín en el mismo campo al mismo tiempo.

### <a name="time-range"></a>Intervalo de tiempo

El valor predeterminado es **2 días**, pero puede especificar intervalos de fecha y hora de hasta 90 días. Al usar intervalos de fecha y hora, tenga en cuenta estos problemas:

- De forma predeterminada, selecciona el intervalo de tiempo en la vista de **control deslizante** mediante una línea de tiempo. Sólo puede seleccionar el día o configuración que se muestra de tiempo. Intenta seleccionar un valor intermedios se ajustará la burbuja de inicio y finalización a más próximo que se muestra la configuración.

   ![Un intervalo de tiempo del control deslizante en un nuevo seguimiento de mensajes en el centro de cumplimiento de seguridad &](media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

   Sin embargo, también puede cambiar a la vista **personalizada** donde puede especificar los valores de **fecha de inicio** y **fecha de finalización** (incluidos veces), y también puede seleccionar la **zona horaria** para el intervalo de fecha y hora. Tenga en cuenta que la configuración de **zona horaria** se aplica a las entradas de consulta y los resultados de la consulta.

   ![Un intervalo de tiempo personalizado en un nuevo seguimiento de mensajes en el centro de cumplimiento de seguridad &](media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

   Para 10 días o menos, los resultados están disponibles al instante como un informe de **Resumen** . Si especifica un intervalo de tiempo que es incluso ligeramente mayor que 10 días, los resultados se retrasarán como sólo están disponibles como un archivo CSV descargable (informes **mejorada resumen** o **extendida** ).

   Para obtener más información acerca de los distintos tipos de informe, vea la sección [Elegir tipo de informe](#choose-report-type) en este tema.

   **Nota**: los informes de resumen y extendidos mejorados están preparados con datos de seguimiento de mensajes archivados, y puede tardar hasta varias horas antes de que el informe está disponible para su descarga. Dependiendo de cómo muchos otros administradores también han enviado solicitudes de informe de aproximadamente al mismo tiempo, es posible que Observe también un retraso antes de que comience el procesamiento para la solicitud en cola.

- Guardar una consulta en la vista de **control deslizante** guarda el intervalo de tiempo relativo (por ejemplo, 3 días desde la fecha actual). Guardar una consulta en la vista **personalizada** guarda el rango de fecha y hora absoluta (por ejemplo, 2018-05-06 13:00 a 2018-05-08 18:00).

### <a name="more-search-options"></a>Más opciones de búsqueda

#### <a name="delivery-status"></a>Estado de entrega

Puede dejar el valor predeterminado de **todos los** seleccionada, o puede seleccionar uno de los siguientes valores para filtrar los resultados:

- **Entregado**: el mensaje se entregó correctamente al destino previsto.

- **Pendiente**: entrega del mensaje se está intentado o reintentando.

- **Expanded**: un destinatario del grupo de distribución se expandió antes de la entrega a los miembros individuales del grupo.

- **Error**: el mensaje no se entregó.

- **En cuarentena**: el mensaje se puso en cuarentena (como spam, correo masivo o phishing). Para obtener más información, vea [los mensajes de correo electrónico de cuarentena en Office 365](https://support.office.com/article/4c234874-015e-4768-8495-98fcccfc639b.aspx).

- **Filtrado como correo no deseado**: el mensaje fue identificado correo no deseado y se rechazó o bloqueados (no en cuarentena).

- **Al obtener el estado:** El mensaje se recibió recientemente por Office 365, pero no hay otros datos de estado aún están disponibles. Compruebe de nuevo en unos minutos.

**Nota**: los valores **pendiente,** **puesto en cuarentena**y **filtro como correo no deseado** sólo están disponibles para las búsquedas de menos de 10 días. Además, puede haber un retraso de 5 a 10 minutos entre el estado de entrega real y conocida.

#### <a name="message-id"></a>Id. del mensaje

Este es el identificador de mensaje de internet (también conocido como el identificador de cliente) que se encuentra en la **Message-ID:** campo de encabezado en el encabezado del mensaje. Los usuarios pueden conceder este valor para investigar mensajes específicos.

Este valor es constante durante la duración del mensaje. Para los mensajes creados en Office 365 o Exchange, el valor está en el formato `<GUID@ServerFQDN>`, incluidos los corchetes angulares (\< \>). Por ejemplo, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Otros sistemas de mensajería es posible que utilice una sintaxis diferente o valores. Este valor se supone que es único, pero no todos los sistemas de correo electrónico seguir estrictamente este requisito. Si el **Message-ID:** campo de encabezado no existe o no está en blanco para los mensajes entrantes de orígenes externos, y se asigna un valor arbitrario.

Cuando se usa el **Identificador de mensaje** para filtrar los resultados, asegúrese de incluir la cadena completa, incluidos los corchetes angulares.

#### <a name="direction"></a>Dirección

Puede dejar el valor predeterminado de **todos los** seleccionada, o puede seleccionar **entrada** (los mensajes enviados a destinatarios de la organización) o **salida** (los mensajes enviados desde los usuarios de su organización) para filtrar los resultados.

#### <a name="original-client-ip-address"></a>Dirección IP del cliente original

Puede sistemas de almacenamiento de los resultados por dirección IP del cliente para investigar alterado malintencionadamente equipos que va a enviar grandes cantidades de correo no deseado o malware. Aunque podrían parecer que los mensajes procedentes de remitentes varios, es probable que el mismo equipo está generando todos los mensajes.

**Nota**: la información de dirección IP de cliente sólo está disponible para 10 días y sólo está disponible en los informes de **Resumen mejorada** o **extendida** (archivos descargables de CSV).

### <a name="choose-report-type"></a>Elija el tipo de informe

Los tipos de informe disponibles son:

- **Resumen**: disponible si el intervalo de tiempo es inferior a 10 días y no requiere opciones de filtrado adicionales. Los resultados están disponibles casi inmediatamente después haga clic en **Buscar**.

- **Resumen de mejorada** o **extendida**: estos informes sólo están disponibles como archivos CSV descargables y requieren una o varias de las siguientes opciones de filtrado, independientemente del intervalo de tiempo: **estas personas**, **a estas personas**o ** Identificador de mensaje**. Puede usar caracteres comodín para los remitentes o los destinatarios (por ejemplo, \*@contoso.com).

**Notas**:

- Informes de resumen y extendidos mejorados están preparados con datos de seguimiento de mensajes archivados, y puede tardar hasta varias horas antes de que el informe está disponible para descargar. Dependiendo de cómo muchos otros administradores también han enviado solicitudes de informe de aproximadamente al mismo tiempo, es posible que Observe también un retraso antes de que comience la solicitud en cola que va a procesar.

- Mientras que puede seleccionar un informe de resumen o extendida mejorada para cualquier intervalo de fecha y hora, con frecuencia las últimas cuatro horas de los datos archivados no aún esté disponible para estos dos tipos de informes.

Al hacer clic en **siguiente**, aparecerá con una página de resumen que se enumera las opciones de filtrado que ha seleccionado, un título (editable) único para el informe y la dirección de correo electrónico que recibe la notificación cuando se complete (también puede modificar el seguimiento de mensajes y debe estar en uno de los dominios aceptados de su organización). Haga clic en **informe de preparación** para enviar el seguimiento de mensajes. En el método main página de **seguimiento de mensajes** , puede ver el estado del informe en la sección **informes de descargables** .

Para obtener más información acerca de la información que se devuelve en los distintos tipos de informe, vea la siguiente sección.

## <a name="message-trace-results"></a>Resultados de seguimiento de mensajes

Los distintos tipos de informe devuelven distintos niveles de información. La información que está disponible en los diferentes informes se describe en las secciones siguientes.

### <a name="summary-report-output"></a>Salida de informe de resumen

Después de ejecutar el seguimiento de mensajes, se mostrarán los resultados, ordenados por descendente (más reciente primero) de fecha y hora.

![Resultados de informe de resumen de seguimiento de mensajes en el centro de cumplimiento de seguridad &](media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

El informe de resumen contiene la siguiente información:

- **Fecha**: la fecha y hora en que se recibió el mensaje por el servicio, mediante la zona horaria UTC configurada.

- **Remitente**: la dirección de correo electrónico del remitente (*alias*@*dominio*).

- **Destinatario**: la dirección de correo electrónico del destinatario o los destinatarios. Para enviar un mensaje a varios destinatarios, hay una línea por cada destinatario. Si el destinatario es un grupo de distribución, el grupo de distribución dinámico o el grupo de seguridad habilitados para correo, el grupo será el primer destinatario y, a continuación, cada miembro del grupo se encuentra en una línea independiente.

- **Asunto**: los primeros 256 caracteres del mensaje **Asunto:** campo.

- **Estado**: estos valores se describen en la sección [estado de entrega](#delivery-status) .

De forma predeterminada, los resultados de 250 en primer lugar se cargan y fácilmente disponibles. Cuando se desplaza hacia abajo, hay una ligera pausa como el siguiente lote de resultados se cargan. En lugar de desplazarse, haga clic en **cargar todos** para cargar todos los resultados hasta un máximo de 10.000.

Puede hacer clic en los encabezados de columna para ordenar los resultados por los valores de dicha columna en orden ascendente o descendente.

Puede hacer clic en **los resultados de filtro** para filtrar los resultados por una o más columnas.

Puede exportar los resultados una vez que ha seleccionado una o varias filas al hacer clic en **exportar los resultados** y, a continuación, seleccionando **exportar los resultados de todos los**, **exportación carga resultados**o **exportación seleccionada**.

#### <a name="find-related-records-for-this-message"></a>Buscar registros relacionados para este mensaje

Registros de mensajes relacionados son registros que comparten el mismo identificador de mensaje. Recuerde que, incluso un único mensaje enviado entre dos personas puede generar varios registros. Cuando el mensaje se ve afectado por la expansión de grupos de distribución, transferencia, reglas de flujo de correo (también conocida como reglas de transporte), etcetera, que aumenta el número de registros.

Después de seleccionar la casilla de verificación de una fila, puede encontrar registros relacionados para el mensaje, haga clic en el botón **Buscar relacionados con** que aparece, o mediante la selección de **opciones más** ![más](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Buscar registros relacionados para este mensaje**).

Para obtener más información sobre el identificador de mensaje, vea la sección de identificador de mensaje anteriormente en este tema.

#### <a name="message-trace-details"></a>Detalles de seguimiento de mensajes

En el resultado del informe de resumen, puede ver detalles acerca de un mensaje mediante cualquiera de los métodos siguientes:

- Seleccione la fila (haga clic en cualquier lugar en la fila, excepto la casilla de verificación).

- Seleccione la casilla de verificación de la fila y haga clic en **más opciones** ![más](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Ver detalles del mensaje**.

   ![Detalles después de hacer doble clic en una fila en los resultados de seguimiento de mensajes de informe de resumen en el centro de cumplimiento de seguridad &](media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

Los detalles de seguimiento de mensaje contienen la siguiente información adicional que no está presente en el informe de resumen:

- **Eventos de mensaje**: esta sección contiene las clasificaciones que ayudan a clasificar las acciones que realiza el servicio en los mensajes. Algunos de los eventos más interesantes que pueden surgir son:

   - **Recepción**: el servicio recibió el mensaje.

   - **Enviar**: el mensaje fue enviado por el servicio.

   - **Error**: no se pudo entregar el mensaje.

   - **Entregar**: el mensaje se entregó a un buzón de correo.

   - **Expandir**: el mensaje se envió a un grupo de distribución que se ha expandido.

   - **Transferir**: se movieron destinatarios a un mensaje bifurcado debido a la conversión de contenido, los límites de destinatarios del mensaje o los agentes.

   - **Defer**: la entrega del mensaje se pospuso y es posible que se vuelva a intentar más adelante.

   - **Resuelto**: el mensaje se ha redirigido a una dirección de destinatario nuevo basada en una búsqueda de Active Directory. Cuando esto ocurre, la dirección del destinatario original aparece en una fila independiente en el seguimiento de mensajes junto con el estado de entrega final para el mensaje.

   Tenga en cuenta que incluso un mensaje sin incidentes que se entrega correctamente generará varias entradas de **evento** en el seguimiento de mensajes.

- **Obtener más información**: esta sección contiene los siguientes detalles:

   - **Identificador de mensaje**: este valor se describe en la sección de [Identificador de mensaje](#message-id) anteriormente en este tema. Por ejemplo, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

   - **Tamaño del mensaje**

   - **Dirección IP**: la dirección IP del equipo que envió el mensaje. Para los mensajes salientes enviados desde Exchange Online, este valor está en blanco.

   - **Para IP**: la dirección IP o direcciones donde el servicio ha tratado de entregar el mensaje. Si el mensaje tiene varios destinatarios, éstos se muestran. Para los mensajes entrantes enviados a Exchange Online, este valor está en blanco.

### <a name="enhanced-summary-reports"></a>Informes de resumen mejorados

Disponibles informes de resumen mejorada (completados) están disponibles en la sección **informes de descargables** en el seguimiento de mensajes de principio. La siguiente información está disponible en el informe:

- **origin_timestamp**<sup>*</sup>: la fecha y la hora cuando el mensaje se recibió inicialmente por el servicio, mediante la zona horaria UTC configurada.

- **sender_address**: dirección de correo electrónico del remitente (*alias*@*dominio*).

- **Recipient_status**: el estado de la entrega del mensaje al destinatario. Si el mensaje se envió a varios destinatarios, se muestran todos los destinatarios y el estado correspondiente para cada una, con el formato: \< *dirección de correo electrónico*\>##\<*estado*\>. Por ejemplo:

   - **Enviar ##Receive,** significa que el mensaje se ha recibido por el servicio y se envió al destino previsto.

   - **Se producirá un error en ##Receive,** significa que el mensaje se recibió por el servicio pero entrega al destino previsto no se pudo.

   - **Entregar ##Receive,** significa que el mensaje se ha recibido por el servicio y se entregó al buzón de correo del destinatario.

- **message_subject**: los primeros 256 caracteres del campo de **asunto** del mensaje.

- **total_bytes**: el tamaño del mensaje en bytes, incluidos los datos adjuntos.

- **message_id**: este valor se describe en la sección de [Identificador de mensaje](#message-id) anteriormente en este tema. Por ejemplo, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

- **network_message_id**: un valor de identificador de mensaje únicos que son válidas para todas las copias del mensaje que podría crearse debido a la expansión de grupos de distribución o de bifurcación. Un valor de ejemplo es `1341ac7b13fb42ab4d4408cf7f55890f`.

- **original_client_ip**: la dirección IP del cliente del remitente.

- **direccionalidad**: indica si el mensaje se envió como entrante (1) a su organización, o si se envió saliente (2) en la organización.

- **connector_id**: el nombre del conector de origen o de destino. Para obtener más información acerca de los conectores en Exchange Online, vea [Configurar el flujo de correo mediante conectores en Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

- **delivery_priority**<sup>*</sup>: si el mensaje se envió con prioridad **alta**, **baja**o **Normal** .

<sup>*</sup>Estas propiedades sólo están disponibles en los informes de resumen mejorada.

### <a name="extended-reports"></a>Informes ampliados

Informes de Extended (completados) disponibles están disponibles en la sección **informes de Downloadable** al principio de seguimiento de mensajes. Prácticamente toda la información de un informe de resumen de mejorada está disponible en un informe de Extended (a excepción de **origin_timestamp** y **delivery_priority**). La siguiente información adicional sólo está disponible en un informe de Extended:

- **client_ip**: la dirección IP del servidor de correo electrónico o el cliente de mensajería que envió el mensaje.

- **client_hostname**: el nombre de host o el FQDN del servidor de correo electrónico o el cliente de mensajería que envió el mensaje.

- **server_ip**: la dirección IP del servidor de origen o de destino.

- **server_hostname**: el nombre de host o el FQDN del servidor de destino.

- **source_context**: información adicional asociada con el campo de **origen** . Por ejemplo:

   - `Protocol Filter Agent`

   - `3489061114359050000`

- **origen**: Exchange Online el componente que es responsable del evento. Por ejemplo:

   - `AGENT`

   - `MAILBOXRULE`

   - `SMTP`

- **IdDeSuceso**: estos se corresponden con los valores de **evento de mensaje** que se explican en la sección [Buscar los registros relacionados para este mensaje](#find-related-records-for-this-message) .

- **internal_message_id**: un identificador de mensaje que es asignado por el servidor de Exchange Online que actualmente se está procesando el mensaje.

- **recipient_address**: las direcciones de correo electrónico de los destinatarios del mensaje. Varias direcciones de correo electrónico están separadas por el carácter de punto y coma (;).

- **recipient_count**: el número total de destinatarios en el mensaje.

- **related_recipient_address**: se utiliza con `EXPAND`, `REDIRECT`, y `RESOLVE` direcciones que están asociadas con el mensaje de correo electrónico de eventos para mostrar los demás destinatarios.

- **referencia**: este campo contiene información adicional para tipos específicos de eventos. Por ejemplo:

   - **DSN**: contiene el vínculo de informe, que es el valor de **message_id** de la notificación de estado de entrega asociada (también conocido como un DSN, informe de no entrega, NDR o mensaje de rebote) si se genera un DSN con posterioridad a este evento. Si se trata de un mensaje de DSN, este campo contiene el valor **message_id** del mensaje original que se generó el DSN para.

   - **Expandir**: contiene el valor de **related_recipient_address** de los mensajes relacionados.

   - **Recepción**: es posible que contienen el valor **message_id** del mensaje relacionado si el mensaje fue generado por otros procesos (por ejemplo, las reglas de bandeja de entrada).

   - **Enviar**: contiene el valor de **internal_message_id** de todos los mensajes de DSN.

   - **Transferir**: contiene el valor de **internal_message_id** del mensaje que se va a bifurca (por ejemplo, mediante la conversión del contenido, los límites de destinatarios de mensaje o agentes).

   - **MAILBOXRULE**: contiene el valor de **internal_message_id** del mensaje entrante que ha provocado la regla de bandeja de entrada generar el mensaje saliente.

   Para el resto de los tipos de eventos, este campo suele estar en blanco.

- **return_path**: la dirección de correo electrónico devuelto especificada por el comando **MAIL FROM** que envió el mensaje. Aunque este campo nunca está vacío, puede tener el valor de la dirección de remitente null representado como `<>`.

- **message_info**: información adicional sobre el mensaje. Por ejemplo:

   - El origen mensaje fecha y hora en UTC para `DELIVER` y `SEND` eventos. La fecha y hora de origen es la hora cuando el mensaje escrito en primer lugar la organización de Exchange Online. La fecha y hora UTC se representa en el formato de fecha y hora ISO 8601: `yyyy-mm-ddThh:mm:ss.fffZ`, donde `yyyy` = año, `mm` = mes, `dd` = día, `T` indica el principio del componente de hora, `hh` = hora, `mm` = minuto, `ss` = segundo, `fff` = las fracciones de segundo, y `Z` significa `Zulu`, que es otra forma para indicar la hora UTC.

   - Errores de autenticación. Por ejemplo, es posible que vea el valor `11a` y el tipo de autenticación que se usó cuando se produjo el error de autenticación.

- **tenant_id**: un valor GUID que representa la organización de Exchange Online (por ejemplo, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).

- **original_server_ip**: la dirección IP del servidor original.

- **custom_data**: contiene los datos relacionados con los tipos de eventos específicos. Para obtener más información, consulte las siguientes secciones.

#### <a name="customdata-values"></a>valores de custom_data

El campo **custom_data** para un `AGENTINFO` (evento) se usa por una variedad de agentes Exchange Online para registrar los detalles de procesamiento de mensajes. En las secciones siguientes se describen algunas de los agentes más interesantes.

#### <a name="spam-filter-agent"></a>Agente de filtro de correo no deseado

Un valor de **custom_data** que comienza con `S:SFA` va desde el agente de filtro de spam. En la siguiente tabla se describen los detalles de la clave:

|**Valor**|**Descripción**|
|:-----|:-----|
|`SFV=NSPM`|El mensaje se marcó como correo seguro y se envió a los destinatarios correspondientes.|
|`SFV=SPM`|El filtro de contenido marcó el mensaje como correo no deseado.|
|`SFV=BLK`|Se omitió el filtrado y se bloqueó el mensaje porque proviene de un remitente bloqueado.|
|`SFV=SKS`|El mensaje se marcó como correo no deseado antes de que el filtro de contenido lo procesara. Esto incluye los mensajes que coinciden con una regla de transporte que marca el mensaje automáticamente como correo no deseado y omite otros tipos de filtrado.|
|`SCL=<number>`|Para más información sobre los distintos valores SCL y su significado, vea [Niveles de confianza de correo no deseado](https://technet.microsoft.com/library/jj200686.aspx).|
|`PCL=<number>`|Valor de nivel de confianza de protección antiphishing (PCL) del mensaje. Se puede interpretar del mismo modo que los valores de SCL descritos en [Niveles de confianza de correo no deseado](https://technet.microsoft.com/library/jj200686.aspx).  |
|`DI=SB`|Se bloqueó el remitente del mensaje.|
|`DI=SQ`|El mensaje se puso en cuarentena.|
|`DI=SD`|El mensaje se eliminó.|
|`DI=SJ`|El mensaje se envió a la carpeta de correo no deseado del destinatario.|
|`DI=SN`|El mensaje se enrutó a través del grupo de entrega de mayor riesgo. Para obtener más información, vea el [grupo de alto riesgo de entrega para los mensajes salientes](https://technet.microsoft.com/library/jj200746.aspx).|
|`DI=SO`|El mensaje se enrutó a través del grupo de entrega saliente normal.|
|' SFS = [a]|SFS = [b]'|Indica que se coincidió con reglas de correo no deseado.|
|`IPV=CAL`|El mensaje se permitió a través de los filtros de correo no deseado porque la dirección IP estaba incluida en una lista de direcciones IP permitidas en el filtro de conexión.|
|`H=<EHLOstring>`|La cadena HELO o EHLO del servidor de correo electrónico de conexión.|
|`PTR=<ReverseDNS>`|Registro PTR de la dirección IP de envío, también denominado dirección DNS inversa.|

Un valor de **custom_data** de ejemplo para un mensaje que se filtra como correo no deseado como esta:

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a>Agente de filtro de malware

Un valor de **custom_data** que comienza con `S:AMA` va desde el agente de filtro de malware. En la siguiente tabla se describen los detalles de la clave:

|**Valor**|**Descripción**|
|:-----|:-----|
|' AMA = SUMA|v=1|` or `AMA=EV|v = 1'|El mensaje se determinó que contengan malware. `SUM` indica cualquier número de motores de podría ha detectado el malware. `EV` indica que se detectó el malware por un motor específico. Cuando se detecta malware por un motor de que esto desencadena las acciones posteriores.|
|`Action=r`|El mensaje se reemplazó.|
|`Action=p`|El mensaje se omitió.|
|`Action=d`|El mensaje se difirió.|
|`Action=s`|El mensaje se eliminó.|
|`Action=st`|El mensaje se omitió.|
|`Action=sy`|El mensaje se omitió.|
|`Action=ni`|El mensaje se rechazó.|
|`Action=ne`|El mensaje se rechazó.|
|`Action=b`|El mensaje se bloqueó.|
|`Name=<malware>`|Se detectó el nombre del malware.|
|`File=<filename>`|El nombre del archivo que contiene el malware.|

Un valor de **custom_data** de ejemplo para un mensaje que contiene el malware tiene este aspecto:

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a>Agente de reglas de transporte

Un valor de **custom_data** que comienza con`S:TRA` va desde el agente de reglas de transporte para las reglas de flujo de correo (también conocida como reglas de transporte). En la siguiente tabla se describen los detalles de la clave:

|**Valor**|**Descripción**|
|:-----|:-----|
|' ETR|ruleId =<guid>`|El identificador de regla coincidente.|
|`St=<datetime>`|La fecha y la hora en UTC cuando se produjo la coincidencia de regla.|
|`Action=<ActionDefinition>`|La acción que se ha aplicado. Para obtener una lista de acciones disponibles, vea [Mail flow acciones de regla en Exchange Online](https://technet.microsoft.com/library/jj919237.aspx).|
|`Mode=<Mode>`|El modo de la regla. Los valores válidos son:<br/>• **Exigir**: se exigirán todas las acciones de la regla. <br/>• **Probar con sugerencias de directiva:**: acciones de cualquier sugerencia de directiva que se van a enviar, pero no se actuará sobre otras acciones de la aplicación. <br/>• **Probar sin sugerencias de directiva**: las acciones aparecerán en un archivo de registro, pero no se notificará remitentes de ninguna manera y no se actuará sobre las acciones.|

Un valor de **custom_data** de ejemplo para un mensajes que coincide con las condiciones de una regla de flujo de correo tiene este aspecto:

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`

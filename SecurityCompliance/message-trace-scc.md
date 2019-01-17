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
# <a name="message-trace-in-the-security--compliance-center"></a><span data-ttu-id="d177e-103">Seguimiento de mensajes en el centro de cumplimiento de seguridad &</span><span class="sxs-lookup"><span data-stu-id="d177e-103">Message trace in the Security & Compliance Center</span></span>

<span data-ttu-id="d177e-p101">Seguimiento de mensajes en el centro de cumplimiento de seguridad & sigue mensajes de correo electrónico cuando viajan a través de la organización de Exchange Online. Puede determinar si un mensaje se ha recibido, rechazado, aplazado o emitido por el servicio. También se muestran las acciones realizadas en el mensaje antes de alcanzar su estado final.</span><span class="sxs-lookup"><span data-stu-id="d177e-p101">Message trace in the Security & Compliance Center follows email messages as they travel through your Exchange Online organization. You can determine if a message was received, rejected, deferred, or delivered by the service. It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="d177e-p102">Seguimiento de mensajes en el centro de cumplimiento de seguridad & mejora con seguimiento de mensajes que estaba disponible en el centro de administración de Exchange (EAC). Puede usar la información de seguimiento de mensajes para responder a preguntas de los usuarios acerca de ¿qué sucedió con sus mensajes de eficazmente, solucionar problemas del flujo de correo y validar los cambios de directiva.</span><span class="sxs-lookup"><span data-stu-id="d177e-p102">Message trace in the Security & Compliance Center improves upon message trace that was available in the Exchange admin center (EAC). You can use the information from message trace to efficiently answer user questions about what happened to their messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="d177e-109">Seguimiento de mensaje abierto</span><span class="sxs-lookup"><span data-stu-id="d177e-109">Open message trace</span></span>

1. <span data-ttu-id="d177e-110">[Inicie sesión en Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="d177e-110">[Sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="d177e-111">Seleccione el icono del iniciador de aplicaciones ![Icono del iniciador de aplicaciones de Office 365](media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png) de la esquina superior izquierda y elija **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="d177e-111">Select the app launcher icon ![Office 365 app launcher icon](media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png) in the upper-left and choose **Admin**.</span></span>

3. <span data-ttu-id="d177e-112">En el panel de navegación inferior izquierda, expanda **centros de administración** y seleccione **& cumplimiento de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="d177e-112">In the lower-left navigation, expand **Admin centers** and select **Security & Compliance**.</span></span>

4. <span data-ttu-id="d177e-113">En la página **& cumplimiento de seguridad** que se abre, expanda el **flujo de correo**y seleccione el **seguimiento de mensajes**.</span><span class="sxs-lookup"><span data-stu-id="d177e-113">In the **Security & Compliance** page that opens, expand **Mail flow**, and select **Message trace**.</span></span>

## <a name="message-trace-page"></a><span data-ttu-id="d177e-114">Página de seguimiento de mensaje</span><span class="sxs-lookup"><span data-stu-id="d177e-114">Message trace page</span></span>

<span data-ttu-id="d177e-p103">Desde aquí puede iniciar una nueva traza predeterminada haciendo clic en el botón **iniciar un seguimiento** . Realiza una búsqueda de todos los mensajes de todos los remitentes y destinatarios para los dos últimos días. O puede usar una de las consultas almacenadas de las categorías de consulta disponibles y cualquiera ejecutarlas como-es o usarlos como puntos de partida para sus propias consultas:</span><span class="sxs-lookup"><span data-stu-id="d177e-p103">From here you can start a new default trace by clicking on the **Start a trace** button. This will search for all messages for all senders and recipients for the last two days. Or you can use one of the stored queries from the available query categories and either run them as-is or use them as starting points for your own queries:</span></span>

- <span data-ttu-id="d177e-118">**Valor predeterminado de consultas**: consultas integradas proporcionadas por Office 365.</span><span class="sxs-lookup"><span data-stu-id="d177e-118">**Default queries**: Built-in queries provided by Office 365.</span></span>

- <span data-ttu-id="d177e-119">**Consultas personalizadas**: consultas guardadas por los administradores de la organización para un uso futuro.</span><span class="sxs-lookup"><span data-stu-id="d177e-119">**Custom queries**: Queries saved by admins in your organization for future use.</span></span>

- <span data-ttu-id="d177e-p104">**Las consultas de autoguardado**: los últimos diez recientemente ejecutan consultas. Esta lista hace que sea sencillo recoger donde lo dejó.</span><span class="sxs-lookup"><span data-stu-id="d177e-p104">**Autosaved queries**: The last ten most recently run queries. This list makes it simple to pick up where you left off.</span></span>

<span data-ttu-id="d177e-122">También en esta página es una sección **Downloadable informes** para las solicitudes que se ha enviado, así como los informes de ellos mismos cuando hay disponibles para su descarga.</span><span class="sxs-lookup"><span data-stu-id="d177e-122">Also on this page is a **Downloadable reports** section for the requests you've submitted, as well as the reports themselves when they're are available for download.</span></span>

## <a name="options-for-a-new-message-trace"></a><span data-ttu-id="d177e-123">Opciones para un nuevo seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="d177e-123">Options for a new message trace</span></span>

### <a name="filter-by-senders-and-recipients"></a><span data-ttu-id="d177e-124">Filtrar por remitentes y destinatarios</span><span class="sxs-lookup"><span data-stu-id="d177e-124">Filter by senders and recipients</span></span>

<span data-ttu-id="d177e-125">Los valores predeterminados son **todos los remitentes** y **destinatarios**, pero puede usar los siguientes campos para filtrar los resultados:</span><span class="sxs-lookup"><span data-stu-id="d177e-125">The default values are **All senders** and **All recipients**, but you can use the following fields to filter the results:</span></span>

- <span data-ttu-id="d177e-p105">**Las siguientes personas**: haga clic en este campo para seleccionar uno o más remitentes de su organización. También puede comenzar a escriba un nombre y los elementos de la lista se filtrarán por lo que ha escrito, mucho al igual que el comportamiento de una página de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d177e-p105">**By these people**: Click in this field to select one or more senders from your organization. You can also start to type a name and the items in the list will be filtered by what you've typed, much like how a search page behaves.</span></span>

- <span data-ttu-id="d177e-128">**A estas personas**: haga clic en este campo para seleccionar uno o más destinatarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="d177e-128">**To these people**: Click in this field to select one or more recipients in your organization.</span></span>

<span data-ttu-id="d177e-p106">También puede escribir las direcciones de correo electrónico de los remitentes externos y los destinatarios. Se admite caracteres comodín (`*@contoso.com` o `scot?@contoso.com`), pero no se puede usar varias entradas de comodín en el mismo campo al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="d177e-p106">You can also type the email addresses of external senders and recipients. Wildcards are supported (`*@contoso.com` or `scot?@contoso.com`), but you can't use multiple wildcard entries in the same field at the same time.</span></span>

### <a name="time-range"></a><span data-ttu-id="d177e-131">Intervalo de tiempo</span><span class="sxs-lookup"><span data-stu-id="d177e-131">Time range</span></span>

<span data-ttu-id="d177e-p107">El valor predeterminado es **2 días**, pero puede especificar intervalos de fecha y hora de hasta 90 días. Al usar intervalos de fecha y hora, tenga en cuenta estos problemas:</span><span class="sxs-lookup"><span data-stu-id="d177e-p107">The default value is **2 days**, but you can specify date/time ranges of up to 90 days. When you use date/time ranges, consider these issues:</span></span>

- <span data-ttu-id="d177e-p108">De forma predeterminada, selecciona el intervalo de tiempo en la vista de **control deslizante** mediante una línea de tiempo. Sólo puede seleccionar el día o configuración que se muestra de tiempo. Intenta seleccionar un valor intermedios se ajustará la burbuja de inicio y finalización a más próximo que se muestra la configuración.</span><span class="sxs-lookup"><span data-stu-id="d177e-p108">By default, you select the time range in **Slider** view using a time line. You can only select the day or time settings that are displayed. Trying to select an in-between value will snap the start/end bubble to the nearest displayed setting.</span></span>

   ![Un intervalo de tiempo del control deslizante en un nuevo seguimiento de mensajes en el centro de cumplimiento de seguridad &](media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

   <span data-ttu-id="d177e-p109">Sin embargo, también puede cambiar a la vista **personalizada** donde puede especificar los valores de **fecha de inicio** y **fecha de finalización** (incluidos veces), y también puede seleccionar la **zona horaria** para el intervalo de fecha y hora. Tenga en cuenta que la configuración de **zona horaria** se aplica a las entradas de consulta y los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="d177e-p109">But, you can also switch to **Custom** view where you can specify the **Start date** and **End date** values (including times), and you can also select the **Time zone** for the date/time range. Note that the **Time zone** setting applies to both your query inputs and your query results.</span></span>

   ![Un intervalo de tiempo personalizado en un nuevo seguimiento de mensajes en el centro de cumplimiento de seguridad &](media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

   <span data-ttu-id="d177e-p110">Para 10 días o menos, los resultados están disponibles al instante como un informe de **Resumen** . Si especifica un intervalo de tiempo que es incluso ligeramente mayor que 10 días, los resultados se retrasarán como sólo están disponibles como un archivo CSV descargable (informes **mejorada resumen** o **extendida** ).</span><span class="sxs-lookup"><span data-stu-id="d177e-p110">For 10 days or less, the results are available instantly as a **Summary** report. If you specify a time range that's even slightly greater than 10 days, the results will be delayed as they are only available as a downloadable CSV file ( **Enhanced summary** or **Extended** reports).</span></span>

   <span data-ttu-id="d177e-143">Para obtener más información acerca de los distintos tipos de informe, vea la sección [Elegir tipo de informe](#choose-report-type) en este tema.</span><span class="sxs-lookup"><span data-stu-id="d177e-143">For more information about the different report types, see the [Choose report type](#choose-report-type) section in this topic.</span></span>

   <span data-ttu-id="d177e-p111">**Nota**: los informes de resumen y extendidos mejorados están preparados con datos de seguimiento de mensajes archivados, y puede tardar hasta varias horas antes de que el informe está disponible para su descarga. Dependiendo de cómo muchos otros administradores también han enviado solicitudes de informe de aproximadamente al mismo tiempo, es posible que Observe también un retraso antes de que comience el procesamiento para la solicitud en cola.</span><span class="sxs-lookup"><span data-stu-id="d177e-p111">**Note**: Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available for download. Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before processing starts for your queued request.</span></span>

- <span data-ttu-id="d177e-p112">Guardar una consulta en la vista de **control deslizante** guarda el intervalo de tiempo relativo (por ejemplo, 3 días desde la fecha actual). Guardar una consulta en la vista **personalizada** guarda el rango de fecha y hora absoluta (por ejemplo, 2018-05-06 13:00 a 2018-05-08 18:00).</span><span class="sxs-lookup"><span data-stu-id="d177e-p112">Saving a query in **Slider** view saves the relative time range (for example, 3 days from today). Saving a query in **Custom** view saves the absolute date/time range (for example, 2018-05-06 13:00 to 2018-05-08 18:00).</span></span>

### <a name="more-search-options"></a><span data-ttu-id="d177e-148">Más opciones de búsqueda</span><span class="sxs-lookup"><span data-stu-id="d177e-148">More search options</span></span>

#### <a name="delivery-status"></a><span data-ttu-id="d177e-149">Estado de entrega</span><span class="sxs-lookup"><span data-stu-id="d177e-149">Delivery status</span></span>

<span data-ttu-id="d177e-150">Puede dejar el valor predeterminado de **todos los** seleccionada, o puede seleccionar uno de los siguientes valores para filtrar los resultados:</span><span class="sxs-lookup"><span data-stu-id="d177e-150">You can leave the default value **All** selected, or you can select one of the following values to filter the results:</span></span>

- <span data-ttu-id="d177e-151">**Entregado**: el mensaje se entregó correctamente al destino previsto.</span><span class="sxs-lookup"><span data-stu-id="d177e-151">**Delivered**: The message was successfully delivered to the intended destination.</span></span>

- <span data-ttu-id="d177e-152">**Pendiente**: entrega del mensaje se está intentado o reintentando.</span><span class="sxs-lookup"><span data-stu-id="d177e-152">**Pending**: Delivery of the message is being attempted or re-attempted.</span></span>

- <span data-ttu-id="d177e-153">**Expanded**: un destinatario del grupo de distribución se expandió antes de la entrega a los miembros individuales del grupo.</span><span class="sxs-lookup"><span data-stu-id="d177e-153">**Expanded**: A distribution group recipient was expanded before delivery to the individual members of the group.</span></span>

- <span data-ttu-id="d177e-154">**Error**: el mensaje no se entregó.</span><span class="sxs-lookup"><span data-stu-id="d177e-154">**Failed**: The message was not delivered.</span></span>

- <span data-ttu-id="d177e-p113">**En cuarentena**: el mensaje se puso en cuarentena (como spam, correo masivo o phishing). Para obtener más información, vea [los mensajes de correo electrónico de cuarentena en Office 365](https://support.office.com/article/4c234874-015e-4768-8495-98fcccfc639b.aspx).</span><span class="sxs-lookup"><span data-stu-id="d177e-p113">**Quarantined**: The message was quarantined (as spam, bulk mail, or phishing). For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/4c234874-015e-4768-8495-98fcccfc639b.aspx).</span></span>

- <span data-ttu-id="d177e-157">**Filtrado como correo no deseado**: el mensaje fue identificado correo no deseado y se rechazó o bloqueados (no en cuarentena).</span><span class="sxs-lookup"><span data-stu-id="d177e-157">**Filtered as spam**: The message was identified spam, and was rejected or blocked (not quarantined).</span></span>

- <span data-ttu-id="d177e-p114">**Al obtener el estado:** El mensaje se recibió recientemente por Office 365, pero no hay otros datos de estado aún están disponibles. Compruebe de nuevo en unos minutos.</span><span class="sxs-lookup"><span data-stu-id="d177e-p114">**Getting status:** The message was recently received by Office 365, but no other status data is yet available. Check back in a few minutes.</span></span>

<span data-ttu-id="d177e-p115">**Nota**: los valores **pendiente,** **puesto en cuarentena**y **filtro como correo no deseado** sólo están disponibles para las búsquedas de menos de 10 días. Además, puede haber un retraso de 5 a 10 minutos entre el estado de entrega real y conocida.</span><span class="sxs-lookup"><span data-stu-id="d177e-p115">**Note**: The values **Pending,** **Quarantined**, and **Filter as spam** are only available for searches less than 10 days. Also, there might be a 5 to 10 minute delay between the actual and reported delivery status.</span></span>

#### <a name="message-id"></a><span data-ttu-id="d177e-162">Id. del mensaje</span><span class="sxs-lookup"><span data-stu-id="d177e-162">Message ID</span></span>

<span data-ttu-id="d177e-p116">Este es el identificador de mensaje de internet (también conocido como el identificador de cliente) que se encuentra en la **Message-ID:** campo de encabezado en el encabezado del mensaje. Los usuarios pueden conceder este valor para investigar mensajes específicos.</span><span class="sxs-lookup"><span data-stu-id="d177e-p116">This is the internet message ID (also known as the Client ID) that's found in the **Message-ID:** header field in the message header. Users can give you this value to investigate specific messages.</span></span>

<span data-ttu-id="d177e-p117">Este valor es constante durante la duración del mensaje. Para los mensajes creados en Office 365 o Exchange, el valor está en el formato `<GUID@ServerFQDN>`, incluidos los corchetes angulares (\< \>). Por ejemplo, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Otros sistemas de mensajería es posible que utilice una sintaxis diferente o valores. Este valor se supone que es único, pero no todos los sistemas de correo electrónico seguir estrictamente este requisito. Si el **Message-ID:** campo de encabezado no existe o no está en blanco para los mensajes entrantes de orígenes externos, y se asigna un valor arbitrario.</span><span class="sxs-lookup"><span data-stu-id="d177e-p117">This value is constant for the lifetime of the message. For messages created in Office 365 or Exchange, the value is in the format `<GUID@ServerFQDN>`, including the angle brackets (\< \>). For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Other messaging systems might use different syntax or values. This value is supposed to be unique, but not all email systems strictly follow this requirement. If the **Message-ID:** header field doesn't exist or is blank for incoming messages from external sources, an arbitrary value is assigned.</span></span>

<span data-ttu-id="d177e-171">Cuando se usa el **Identificador de mensaje** para filtrar los resultados, asegúrese de incluir la cadena completa, incluidos los corchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="d177e-171">When you use **Message ID** to filter the results, be sure to include the full string, including any angle brackets.</span></span>

#### <a name="direction"></a><span data-ttu-id="d177e-172">Dirección</span><span class="sxs-lookup"><span data-stu-id="d177e-172">Direction</span></span>

<span data-ttu-id="d177e-173">Puede dejar el valor predeterminado de **todos los** seleccionada, o puede seleccionar **entrada** (los mensajes enviados a destinatarios de la organización) o **salida** (los mensajes enviados desde los usuarios de su organización) para filtrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="d177e-173">You can leave the default value **All** selected, or you can select **Inbound** (messages sent to recipients in your organization) or **Outbound** (messages sent from users in your organization) to filter the results.</span></span>

#### <a name="original-client-ip-address"></a><span data-ttu-id="d177e-174">Dirección IP del cliente original</span><span class="sxs-lookup"><span data-stu-id="d177e-174">Original client IP address</span></span>

<span data-ttu-id="d177e-p118">Puede sistemas de almacenamiento de los resultados por dirección IP del cliente para investigar alterado malintencionadamente equipos que va a enviar grandes cantidades de correo no deseado o malware. Aunque podrían parecer que los mensajes procedentes de remitentes varios, es probable que el mismo equipo está generando todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="d177e-p118">You can filer the results by client IP address to investigate hacked computers that are sending large amounts of spam or malware. Although the messages might appear to come from multiple senders, it's likely that the same computer is generating all of the messages.</span></span>

<span data-ttu-id="d177e-177">**Nota**: la información de dirección IP de cliente sólo está disponible para 10 días y sólo está disponible en los informes de **Resumen mejorada** o **extendida** (archivos descargables de CSV).</span><span class="sxs-lookup"><span data-stu-id="d177e-177">**Note**: The client IP address information is only available for 10 days, and is only available in the **Enhanced summary** or **Extended** reports (downloadable CSV files).</span></span>

### <a name="choose-report-type"></a><span data-ttu-id="d177e-178">Elija el tipo de informe</span><span class="sxs-lookup"><span data-stu-id="d177e-178">Choose report type</span></span>

<span data-ttu-id="d177e-179">Los tipos de informe disponibles son:</span><span class="sxs-lookup"><span data-stu-id="d177e-179">The available report types are:</span></span>

- <span data-ttu-id="d177e-p119">**Resumen**: disponible si el intervalo de tiempo es inferior a 10 días y no requiere opciones de filtrado adicionales. Los resultados están disponibles casi inmediatamente después haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="d177e-p119">**Summary**: Available if the time range is less than 10 days, and requires no additional filtering options. The results are available almost immediately after you click **Search**.</span></span>

- <span data-ttu-id="d177e-p120">**Resumen de mejorada** o **extendida**: estos informes sólo están disponibles como archivos CSV descargables y requieren una o varias de las siguientes opciones de filtrado, independientemente del intervalo de tiempo: **estas personas**, **a estas personas**o \*\* Identificador de mensaje\*\*. Puede usar caracteres comodín para los remitentes o los destinatarios (por ejemplo, \*@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d177e-p120">**Enhanced summary** or **Extended**: These reports are only available as downloadable CSV files, and require one or more of the following filtering options regardless of the time range: **By these people**, **To these people**, or **Message ID**. You can use wildcards for the senders or the recipients (for example, \*@contoso.com).</span></span>

<span data-ttu-id="d177e-184">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="d177e-184">**Notes**:</span></span>

- <span data-ttu-id="d177e-p121">Informes de resumen y extendidos mejorados están preparados con datos de seguimiento de mensajes archivados, y puede tardar hasta varias horas antes de que el informe está disponible para descargar. Dependiendo de cómo muchos otros administradores también han enviado solicitudes de informe de aproximadamente al mismo tiempo, es posible que Observe también un retraso antes de que comience la solicitud en cola que va a procesar.</span><span class="sxs-lookup"><span data-stu-id="d177e-p121">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available to download. Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before your queued request starts to be processed.</span></span>

- <span data-ttu-id="d177e-187">Mientras que puede seleccionar un informe de resumen o extendida mejorada para cualquier intervalo de fecha y hora, con frecuencia las últimas cuatro horas de los datos archivados no aún esté disponible para estos dos tipos de informes.</span><span class="sxs-lookup"><span data-stu-id="d177e-187">While you can select an Enhanced summary or Extended report for any date/time range, commonly the last four hours of archived data will not yet be available for these two types of reports.</span></span>

<span data-ttu-id="d177e-p122">Al hacer clic en **siguiente**, aparecerá con una página de resumen que se enumera las opciones de filtrado que ha seleccionado, un título (editable) único para el informe y la dirección de correo electrónico que recibe la notificación cuando se complete (también puede modificar el seguimiento de mensajes y debe estar en uno de los dominios aceptados de su organización). Haga clic en **informe de preparación** para enviar el seguimiento de mensajes. En el método main página de **seguimiento de mensajes** , puede ver el estado del informe en la sección **informes de descargables** .</span><span class="sxs-lookup"><span data-stu-id="d177e-p122">When you click **Next**, you're presented with a summary page that lists the filtering options that you selected, a unique (editable) title for the report, and the email address that receives the notification when the message trace completes (also editable, and must be in one of your organization's accepted domains). Click **Prepare report** to submit the message trace. On the main **Message trace** page, you can see the status of the report in the **Downloadable reports** section.</span></span>

<span data-ttu-id="d177e-191">Para obtener más información acerca de la información que se devuelve en los distintos tipos de informe, vea la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="d177e-191">For more information about the information that's returned in the different report types, see the next section.</span></span>

## <a name="message-trace-results"></a><span data-ttu-id="d177e-192">Resultados de seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="d177e-192">Message trace results</span></span>

<span data-ttu-id="d177e-p123">Los distintos tipos de informe devuelven distintos niveles de información. La información que está disponible en los diferentes informes se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="d177e-p123">The different report types return different levels of information. The information that's available in the different reports is described in the following sections.</span></span>

### <a name="summary-report-output"></a><span data-ttu-id="d177e-195">Salida de informe de resumen</span><span class="sxs-lookup"><span data-stu-id="d177e-195">Summary report output</span></span>

<span data-ttu-id="d177e-196">Después de ejecutar el seguimiento de mensajes, se mostrarán los resultados, ordenados por descendente (más reciente primero) de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="d177e-196">After running the message trace, the results will be listed, sorted by descending date/time (most recent first).</span></span>

![Resultados de informe de resumen de seguimiento de mensajes en el centro de cumplimiento de seguridad &](media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

<span data-ttu-id="d177e-198">El informe de resumen contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="d177e-198">The summary report contains the following information:</span></span>

- <span data-ttu-id="d177e-199">**Fecha**: la fecha y hora en que se recibió el mensaje por el servicio, mediante la zona horaria UTC configurada.</span><span class="sxs-lookup"><span data-stu-id="d177e-199">**Date**: The date and time at which the message was received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="d177e-200">**Remitente**: la dirección de correo electrónico del remitente (*alias*@*dominio*).</span><span class="sxs-lookup"><span data-stu-id="d177e-200">**Sender**: The email address of the sender (*alias*@*domain*).</span></span>

- <span data-ttu-id="d177e-p124">**Destinatario**: la dirección de correo electrónico del destinatario o los destinatarios. Para enviar un mensaje a varios destinatarios, hay una línea por cada destinatario. Si el destinatario es un grupo de distribución, el grupo de distribución dinámico o el grupo de seguridad habilitados para correo, el grupo será el primer destinatario y, a continuación, cada miembro del grupo se encuentra en una línea independiente.</span><span class="sxs-lookup"><span data-stu-id="d177e-p124">**Recipient**: The email address of the recipient or recipients. For a message sent to multiple recipients, there's one line per recipient. If the recipient is a distribution group, dynamic distribution group, or mail-enabled security group, the group will be the first recipient, and then each member of the group is on a separate line.</span></span>

- <span data-ttu-id="d177e-204">**Asunto**: los primeros 256 caracteres del mensaje **Asunto:** campo.</span><span class="sxs-lookup"><span data-stu-id="d177e-204">**Subject**: The first 256 characters of the message's **Subject:** field.</span></span>

- <span data-ttu-id="d177e-205">**Estado**: estos valores se describen en la sección [estado de entrega](#delivery-status) .</span><span class="sxs-lookup"><span data-stu-id="d177e-205">**Status**: These values are described in the [Delivery status](#delivery-status) section.</span></span>

<span data-ttu-id="d177e-p125">De forma predeterminada, los resultados de 250 en primer lugar se cargan y fácilmente disponibles. Cuando se desplaza hacia abajo, hay una ligera pausa como el siguiente lote de resultados se cargan. En lugar de desplazarse, haga clic en **cargar todos** para cargar todos los resultados hasta un máximo de 10.000.</span><span class="sxs-lookup"><span data-stu-id="d177e-p125">By default, the first 250 results are loaded and readily available. When you scroll down, there's a slight pause as the next batch of results are loaded. Instead of scrolling, you can click **Load all** to load all of the results up to a maximum of 10,000.</span></span>

<span data-ttu-id="d177e-209">Puede hacer clic en los encabezados de columna para ordenar los resultados por los valores de dicha columna en orden ascendente o descendente.</span><span class="sxs-lookup"><span data-stu-id="d177e-209">You can click on the column headers to sort the results by the values in that column in ascending or descending order.</span></span>

<span data-ttu-id="d177e-210">Puede hacer clic en **los resultados de filtro** para filtrar los resultados por una o más columnas.</span><span class="sxs-lookup"><span data-stu-id="d177e-210">You can click **Filter results** to filter the results by one or more columns.</span></span>

<span data-ttu-id="d177e-211">Puede exportar los resultados una vez que ha seleccionado una o varias filas al hacer clic en **exportar los resultados** y, a continuación, seleccionando **exportar los resultados de todos los**, **exportación carga resultados**o **exportación seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="d177e-211">You can export the results after you've selected one or more rows by clicking **Export results** and then selecting **Export all results**, **Export loaded results**, or **Export selected**.</span></span>

#### <a name="find-related-records-for-this-message"></a><span data-ttu-id="d177e-212">Buscar registros relacionados para este mensaje</span><span class="sxs-lookup"><span data-stu-id="d177e-212">Find related records for this message</span></span>

<span data-ttu-id="d177e-p126">Registros de mensajes relacionados son registros que comparten el mismo identificador de mensaje. Recuerde que, incluso un único mensaje enviado entre dos personas puede generar varios registros. Cuando el mensaje se ve afectado por la expansión de grupos de distribución, transferencia, reglas de flujo de correo (también conocida como reglas de transporte), etcetera, que aumenta el número de registros.</span><span class="sxs-lookup"><span data-stu-id="d177e-p126">Related message records are records that shared the same Message ID. Remember, even a single message sent between two people can generate multiple records. The number of records increases when the message is affected by distribution group expansion, forwarding, mail flow rules (also known as transport rules), etc.</span></span>

<span data-ttu-id="d177e-216">Después de seleccionar la casilla de verificación de una fila, puede encontrar registros relacionados para el mensaje, haga clic en el botón **Buscar relacionados con** que aparece, o mediante la selección de **opciones más** ![más](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Buscar registros relacionados para este mensaje**).</span><span class="sxs-lookup"><span data-stu-id="d177e-216">After you select a row's check box, you can find related records for the message by clicking the **Find related** button that appears, or by selecting **More options** ![More](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Find related records for this message**).</span></span>

<span data-ttu-id="d177e-217">Para obtener más información sobre el identificador de mensaje, vea la sección de identificador de mensaje anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="d177e-217">For more information about the Message ID, see the Message ID section earlier in this topic.</span></span>

#### <a name="message-trace-details"></a><span data-ttu-id="d177e-218">Detalles de seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="d177e-218">Message trace details</span></span>

<span data-ttu-id="d177e-219">En el resultado del informe de resumen, puede ver detalles acerca de un mensaje mediante cualquiera de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d177e-219">In the summary report output, you can view details about a message by using either of the following methods:</span></span>

- <span data-ttu-id="d177e-220">Seleccione la fila (haga clic en cualquier lugar en la fila, excepto la casilla de verificación).</span><span class="sxs-lookup"><span data-stu-id="d177e-220">Select the row (click anywhere in the row except the check box).</span></span>

- <span data-ttu-id="d177e-221">Seleccione la casilla de verificación de la fila y haga clic en **más opciones** ![más](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Ver detalles del mensaje**.</span><span class="sxs-lookup"><span data-stu-id="d177e-221">Select the row's check box and click **More options** ![More](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **View message details**.</span></span>

   ![Detalles después de hacer doble clic en una fila en los resultados de seguimiento de mensajes de informe de resumen en el centro de cumplimiento de seguridad &](media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

<span data-ttu-id="d177e-223">Los detalles de seguimiento de mensaje contienen la siguiente información adicional que no está presente en el informe de resumen:</span><span class="sxs-lookup"><span data-stu-id="d177e-223">The message trace details contain the following additional information that's not present in the summary report:</span></span>

- <span data-ttu-id="d177e-p127">**Eventos de mensaje**: esta sección contiene las clasificaciones que ayudan a clasificar las acciones que realiza el servicio en los mensajes. Algunos de los eventos más interesantes que pueden surgir son:</span><span class="sxs-lookup"><span data-stu-id="d177e-p127">**Message events**: This section contains classifications that help categorize the actions that the service takes on messages. Some of the more interesting events that you might encounter are:</span></span>

   - <span data-ttu-id="d177e-226">**Recepción**: el servicio recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d177e-226">**Receive**: The message was received by the service.</span></span>

   - <span data-ttu-id="d177e-227">**Enviar**: el mensaje fue enviado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="d177e-227">**Send**: The message was sent by the service.</span></span>

   - <span data-ttu-id="d177e-228">**Error**: no se pudo entregar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d177e-228">**Fail**: The message failed to be delivered.</span></span>

   - <span data-ttu-id="d177e-229">**Entregar**: el mensaje se entregó a un buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="d177e-229">**Deliver**: The message was delivered to a mailbox.</span></span>

   - <span data-ttu-id="d177e-230">**Expandir**: el mensaje se envió a un grupo de distribución que se ha expandido.</span><span class="sxs-lookup"><span data-stu-id="d177e-230">**Expand**: The message was sent to a distribution group that was expanded.</span></span>

   - <span data-ttu-id="d177e-231">**Transferir**: se movieron destinatarios a un mensaje bifurcado debido a la conversión de contenido, los límites de destinatarios del mensaje o los agentes.</span><span class="sxs-lookup"><span data-stu-id="d177e-231">**Transfer**: Recipients were moved to a bifurcated message because of content conversion, message recipient limits, or agents.</span></span>

   - <span data-ttu-id="d177e-232">**Defer**: la entrega del mensaje se pospuso y es posible que se vuelva a intentar más adelante.</span><span class="sxs-lookup"><span data-stu-id="d177e-232">**Defer**: The message delivery was postponed and might be re-attempted later.</span></span>

   - <span data-ttu-id="d177e-p128">**Resuelto**: el mensaje se ha redirigido a una dirección de destinatario nuevo basada en una búsqueda de Active Directory. Cuando esto ocurre, la dirección del destinatario original aparece en una fila independiente en el seguimiento de mensajes junto con el estado de entrega final para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d177e-p128">**Resolved**: The message was redirected to a new recipient address based on an Active Directory look up. When this happens, the original recipient address is listed in a separate row in the message trace along with the final delivery status for the message.</span></span>

   <span data-ttu-id="d177e-235">Tenga en cuenta que incluso un mensaje sin incidentes que se entrega correctamente generará varias entradas de **evento** en el seguimiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="d177e-235">Note that even an uneventful message that's successfully delivered will generate multiple **Event** entries in the message trace.</span></span>

- <span data-ttu-id="d177e-236">**Obtener más información**: esta sección contiene los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="d177e-236">**More information**: This section contains the following details:</span></span>

   - <span data-ttu-id="d177e-p129">**Identificador de mensaje**: este valor se describe en la sección de [Identificador de mensaje](#message-id) anteriormente en este tema. Por ejemplo, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span><span class="sxs-lookup"><span data-stu-id="d177e-p129">**Message ID**: This value is described in the [Message ID](#message-id) section earlier in this topic. For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

   - <span data-ttu-id="d177e-239">**Tamaño del mensaje**</span><span class="sxs-lookup"><span data-stu-id="d177e-239">**Message size**</span></span>

   - <span data-ttu-id="d177e-p130">**Dirección IP**: la dirección IP del equipo que envió el mensaje. Para los mensajes salientes enviados desde Exchange Online, este valor está en blanco.</span><span class="sxs-lookup"><span data-stu-id="d177e-p130">**From IP**: The IP address of the computer that sent the message. For outbound messages sent from Exchange Online, this value is blank.</span></span>

   - <span data-ttu-id="d177e-p131">**Para IP**: la dirección IP o direcciones donde el servicio ha tratado de entregar el mensaje. Si el mensaje tiene varios destinatarios, éstos se muestran. Para los mensajes entrantes enviados a Exchange Online, este valor está en blanco.</span><span class="sxs-lookup"><span data-stu-id="d177e-p131">**To IP**: The IP address or addresses where the service attempted to deliver the message. If the message has multiple recipients, these are displayed. For inbound messages sent to Exchange Online, this value is blank.</span></span>

### <a name="enhanced-summary-reports"></a><span data-ttu-id="d177e-245">Informes de resumen mejorados</span><span class="sxs-lookup"><span data-stu-id="d177e-245">Enhanced summary reports</span></span>

<span data-ttu-id="d177e-p132">Disponibles informes de resumen mejorada (completados) están disponibles en la sección **informes de descargables** en el seguimiento de mensajes de principio. La siguiente información está disponible en el informe:</span><span class="sxs-lookup"><span data-stu-id="d177e-p132">Available (completed) Enhanced summary reports are available in the **Downloadable reports** section at the beginning message trace. The following information is available in the report:</span></span>

- <span data-ttu-id="d177e-248">**origin_timestamp**<sup>\*</sup>: la fecha y la hora cuando el mensaje se recibió inicialmente por el servicio, mediante la zona horaria UTC configurada.</span><span class="sxs-lookup"><span data-stu-id="d177e-248">**origin_timestamp**<sup>\*</sup>: The date and time when the message was initially received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="d177e-249">**sender_address**: dirección de correo electrónico del remitente (*alias*@*dominio*).</span><span class="sxs-lookup"><span data-stu-id="d177e-249">**sender_address**: The sender's email address (*alias*@*domain*).</span></span>

- <span data-ttu-id="d177e-p133">**Recipient_status**: el estado de la entrega del mensaje al destinatario. Si el mensaje se envió a varios destinatarios, se muestran todos los destinatarios y el estado correspondiente para cada una, con el formato: \< *dirección de correo electrónico*\>##\<*estado*\>. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d177e-p133">**Recipient_status**: The status of the delivery of the message to the recipient. If the message was sent to multiple recipients, it will show all the recipients and the corresponding status for each, in the format: \<*email address*\>##\<*status*\>. For example:</span></span>

   - <span data-ttu-id="d177e-253">**Enviar ##Receive,** significa que el mensaje se ha recibido por el servicio y se envió al destino previsto.</span><span class="sxs-lookup"><span data-stu-id="d177e-253">**##Receive, Send** means the message was received by the service and was sent to the intended destination.</span></span>

   - <span data-ttu-id="d177e-254">**Se producirá un error en ##Receive,** significa que el mensaje se recibió por el servicio pero entrega al destino previsto no se pudo.</span><span class="sxs-lookup"><span data-stu-id="d177e-254">**##Receive, Fail** means the message was received by the service but delivery to the intended destination failed.</span></span>

   - <span data-ttu-id="d177e-255">**Entregar ##Receive,** significa que el mensaje se ha recibido por el servicio y se entregó al buzón de correo del destinatario.</span><span class="sxs-lookup"><span data-stu-id="d177e-255">**##Receive, Deliver** means the message was received by the service and was delivered to the recipient's mailbox.</span></span>

- <span data-ttu-id="d177e-256">**message_subject**: los primeros 256 caracteres del campo de **asunto** del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d177e-256">**message_subject**: The first 256 characters of the message's **Subject** field.</span></span>

- <span data-ttu-id="d177e-257">**total_bytes**: el tamaño del mensaje en bytes, incluidos los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="d177e-257">**total_bytes**: The size of the message in bytes, including attachments.</span></span>

- <span data-ttu-id="d177e-p134">**message_id**: este valor se describe en la sección de [Identificador de mensaje](#message-id) anteriormente en este tema. Por ejemplo, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span><span class="sxs-lookup"><span data-stu-id="d177e-p134">**message_id**: This value is described in the [Message ID](#message-id) section earlier in this topic. For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

- <span data-ttu-id="d177e-p135">**network_message_id**: un valor de identificador de mensaje únicos que son válidas para todas las copias del mensaje que podría crearse debido a la expansión de grupos de distribución o de bifurcación. Un valor de ejemplo es `1341ac7b13fb42ab4d4408cf7f55890f`.</span><span class="sxs-lookup"><span data-stu-id="d177e-p135">**network_message_id**: A unique message ID value that persists across all copies of the message that might be created due to bifurcation or distribution group expansion. An example value is `1341ac7b13fb42ab4d4408cf7f55890f`.</span></span>

- <span data-ttu-id="d177e-262">**original_client_ip**: la dirección IP del cliente del remitente.</span><span class="sxs-lookup"><span data-stu-id="d177e-262">**original_client_ip**: The IP address of the sender's client.</span></span>

- <span data-ttu-id="d177e-263">**direccionalidad**: indica si el mensaje se envió como entrante (1) a su organización, o si se envió saliente (2) en la organización.</span><span class="sxs-lookup"><span data-stu-id="d177e-263">**directionality**: Indicates whether the message was sent inbound (1) to your organization, or whether it was sent outbound (2) from your organization.</span></span>

- <span data-ttu-id="d177e-p136">**connector_id**: el nombre del conector de origen o de destino. Para obtener más información acerca de los conectores en Exchange Online, vea [Configurar el flujo de correo mediante conectores en Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="d177e-p136">**connector_id**: The name of the source or destination connector. For more information about connectors in Exchange Online, see [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

- <span data-ttu-id="d177e-266">**delivery_priority**<sup>\*</sup>: si el mensaje se envió con prioridad **alta**, **baja**o **Normal** .</span><span class="sxs-lookup"><span data-stu-id="d177e-266">**delivery_priority**<sup>\*</sup>: Whether the message was sent with **High**, **Low**, or **Normal** priority.</span></span>

<span data-ttu-id="d177e-267"><sup>\*</sup>Estas propiedades sólo están disponibles en los informes de resumen mejorada.</span><span class="sxs-lookup"><span data-stu-id="d177e-267"><sup>\*</sup>These properties are only available in Enhanced summary reports.</span></span>

### <a name="extended-reports"></a><span data-ttu-id="d177e-268">Informes ampliados</span><span class="sxs-lookup"><span data-stu-id="d177e-268">Extended reports</span></span>

<span data-ttu-id="d177e-p137">Informes de Extended (completados) disponibles están disponibles en la sección **informes de Downloadable** al principio de seguimiento de mensajes. Prácticamente toda la información de un informe de resumen de mejorada está disponible en un informe de Extended (a excepción de **origin_timestamp** y **delivery_priority**). La siguiente información adicional sólo está disponible en un informe de Extended:</span><span class="sxs-lookup"><span data-stu-id="d177e-p137">Available (completed) Extended reports are available in the **Downloadable reports** section at the beginning of message trace. Virtually all of the information from an Enhanced summary report is available in an Extended report (with the exception of **origin_timestamp** and **delivery_priority**). The following additional information is only available in an Extended report:</span></span>

- <span data-ttu-id="d177e-272">**client_ip**: la dirección IP del servidor de correo electrónico o el cliente de mensajería que envió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d177e-272">**client_ip**: The IP address of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="d177e-273">**client_hostname**: el nombre de host o el FQDN del servidor de correo electrónico o el cliente de mensajería que envió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d177e-273">**client_hostname**: The host name or FQDN of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="d177e-274">**server_ip**: la dirección IP del servidor de origen o de destino.</span><span class="sxs-lookup"><span data-stu-id="d177e-274">**server_ip**: The IP address of the source or destination server.</span></span>

- <span data-ttu-id="d177e-275">**server_hostname**: el nombre de host o el FQDN del servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="d177e-275">**server_hostname**: The host name or FQDN of the destination server.</span></span>

- <span data-ttu-id="d177e-p138">**source_context**: información adicional asociada con el campo de **origen** . Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d177e-p138">**source_context**: Extra information associated with the **source** field. For example:</span></span>

   - `Protocol Filter Agent`

   - `3489061114359050000`

- <span data-ttu-id="d177e-p139">**origen**: Exchange Online el componente que es responsable del evento. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d177e-p139">**source**: The Exchange Online component that's responsible for the event. For example:</span></span>

   - `AGENT`

   - `MAILBOXRULE`

   - `SMTP`

- <span data-ttu-id="d177e-280">**IdDeSuceso**: estos se corresponden con los valores de **evento de mensaje** que se explican en la sección [Buscar los registros relacionados para este mensaje](#find-related-records-for-this-message) .</span><span class="sxs-lookup"><span data-stu-id="d177e-280">**event_id**: These correspond to the **Message event** values that are explained in the [Find related records for this message](#find-related-records-for-this-message) section.</span></span>

- <span data-ttu-id="d177e-281">**internal_message_id**: un identificador de mensaje que es asignado por el servidor de Exchange Online que actualmente se está procesando el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d177e-281">**internal_message_id**: A message identifier that's assigned by the Exchange Online server that's currently processing the message.</span></span>

- <span data-ttu-id="d177e-p140">**recipient_address**: las direcciones de correo electrónico de los destinatarios del mensaje. Varias direcciones de correo electrónico están separadas por el carácter de punto y coma (;).</span><span class="sxs-lookup"><span data-stu-id="d177e-p140">**recipient_address**: The email addresses of the message's recipients. Multiple email addresses are separated by the semicolon character (;).</span></span>

- <span data-ttu-id="d177e-284">**recipient_count**: el número total de destinatarios en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d177e-284">**recipient_count**: The total number of recipients in the message.</span></span>

- <span data-ttu-id="d177e-285">**related_recipient_address**: se utiliza con `EXPAND`, `REDIRECT`, y `RESOLVE` direcciones que están asociadas con el mensaje de correo electrónico de eventos para mostrar los demás destinatarios.</span><span class="sxs-lookup"><span data-stu-id="d177e-285">**related_recipient_address**: Used with `EXPAND`, `REDIRECT`, and `RESOLVE` events to display other recipient email addresses that are associated with the message.</span></span>

- <span data-ttu-id="d177e-p141">**referencia**: este campo contiene información adicional para tipos específicos de eventos. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d177e-p141">**reference**: This field contains additional information for specific types of events. For example:</span></span>

   - <span data-ttu-id="d177e-p142">**DSN**: contiene el vínculo de informe, que es el valor de **message_id** de la notificación de estado de entrega asociada (también conocido como un DSN, informe de no entrega, NDR o mensaje de rebote) si se genera un DSN con posterioridad a este evento. Si se trata de un mensaje de DSN, este campo contiene el valor **message_id** del mensaje original que se generó el DSN para.</span><span class="sxs-lookup"><span data-stu-id="d177e-p142">**DSN**: Contains the report link, which is the **message_id** value of the associated delivery status notification (also known as a DSN, non-delivery report, NDR, or bounce message) if a DSN is generated subsequent to this event. If this is a DSN message, this field contains the **message_id** value of the original message that the DSN was generated for.</span></span>

   - <span data-ttu-id="d177e-290">**Expandir**: contiene el valor de **related_recipient_address** de los mensajes relacionados.</span><span class="sxs-lookup"><span data-stu-id="d177e-290">**EXPAND**: Contains the **related_recipient_address** value of the related messages.</span></span>

   - <span data-ttu-id="d177e-291">**Recepción**: es posible que contienen el valor **message_id** del mensaje relacionado si el mensaje fue generado por otros procesos (por ejemplo, las reglas de bandeja de entrada).</span><span class="sxs-lookup"><span data-stu-id="d177e-291">**RECEIVE**: Might contain the **message_id** value of the related message if the message was generated by other processes (for example, Inbox rules).</span></span>

   - <span data-ttu-id="d177e-292">**Enviar**: contiene el valor de **internal_message_id** de todos los mensajes de DSN.</span><span class="sxs-lookup"><span data-stu-id="d177e-292">**SEND**: Contains the **internal_message_id** value of any DSN messages.</span></span>

   - <span data-ttu-id="d177e-293">**Transferir**: contiene el valor de **internal_message_id** del mensaje que se va a bifurca (por ejemplo, mediante la conversión del contenido, los límites de destinatarios de mensaje o agentes).</span><span class="sxs-lookup"><span data-stu-id="d177e-293">**TRANSFER**: Contains the **internal_message_id** value of the message that's being forked (for example, by content conversion, message recipient limits, or agents).</span></span>

   - <span data-ttu-id="d177e-294">**MAILBOXRULE**: contiene el valor de **internal_message_id** del mensaje entrante que ha provocado la regla de bandeja de entrada generar el mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="d177e-294">**MAILBOXRULE**: Contains the **internal_message_id** value of the inbound message that caused the Inbox rule to generate the outbound message.</span></span>

   <span data-ttu-id="d177e-295">Para el resto de los tipos de eventos, este campo suele estar en blanco.</span><span class="sxs-lookup"><span data-stu-id="d177e-295">For other types of events, this field is usually blank.</span></span>

- <span data-ttu-id="d177e-p143">**return_path**: la dirección de correo electrónico devuelto especificada por el comando **MAIL FROM** que envió el mensaje. Aunque este campo nunca está vacío, puede tener el valor de la dirección de remitente null representado como `<>`.</span><span class="sxs-lookup"><span data-stu-id="d177e-p143">**return_path**: The return email address specified by the **MAIL FROM** command that sent the message. Although this field is never empty, it can have the null sender address value represented as `<>`.</span></span>

- <span data-ttu-id="d177e-p144">**message_info**: información adicional sobre el mensaje. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d177e-p144">**message_info**: Additional information about the message. For example:</span></span>

   - <span data-ttu-id="d177e-p145">El origen mensaje fecha y hora en UTC para `DELIVER` y `SEND` eventos. La fecha y hora de origen es la hora cuando el mensaje escrito en primer lugar la organización de Exchange Online. La fecha y hora UTC se representa en el formato de fecha y hora ISO 8601: `yyyy-mm-ddThh:mm:ss.fffZ`, donde `yyyy` = año, `mm` = mes, `dd` = día, `T` indica el principio del componente de hora, `hh` = hora, `mm` = minuto, `ss` = segundo, `fff` = las fracciones de segundo, y `Z` significa `Zulu`, que es otra forma para indicar la hora UTC.</span><span class="sxs-lookup"><span data-stu-id="d177e-p145">The message origination date-time in UTC for `DELIVER` and `SEND` events. The origination date-time is the time when the message first entered the Exchange Online organization. The UTC date-time is represented in the ISO 8601 date-time format: `yyyy-mm-ddThh:mm:ss.fffZ`, where `yyyy` = year, `mm` = month, `dd` = day, `T` indicates the beginning of the time component, `hh` = hour, `mm` = minute, `ss` = second, `fff` = fractions of a second, and `Z` signifies `Zulu`, which is another way to denote UTC.</span></span>

   - <span data-ttu-id="d177e-p146">Errores de autenticación. Por ejemplo, es posible que vea el valor `11a` y el tipo de autenticación que se usó cuando se produjo el error de autenticación.</span><span class="sxs-lookup"><span data-stu-id="d177e-p146">Authentication errors. For example, you might see the value `11a` and the type of authentication that was used when the authentication error occurred.</span></span>

- <span data-ttu-id="d177e-305">**tenant_id**: un valor GUID que representa la organización de Exchange Online (por ejemplo, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).</span><span class="sxs-lookup"><span data-stu-id="d177e-305">**tenant_id**: A GUID value that represents the Exchange Online organization (for example, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).</span></span>

- <span data-ttu-id="d177e-306">**original_server_ip**: la dirección IP del servidor original.</span><span class="sxs-lookup"><span data-stu-id="d177e-306">**original_server_ip**: The IP address of the original server.</span></span>

- <span data-ttu-id="d177e-p147">**custom_data**: contiene los datos relacionados con los tipos de eventos específicos. Para obtener más información, consulte las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="d177e-p147">**custom_data**: Contains data related to specific event types. For more information, see the following sections.</span></span>

#### <a name="customdata-values"></a><span data-ttu-id="d177e-309">valores de custom_data</span><span class="sxs-lookup"><span data-stu-id="d177e-309">custom_data values</span></span>

<span data-ttu-id="d177e-p148">El campo **custom_data** para un `AGENTINFO` (evento) se usa por una variedad de agentes Exchange Online para registrar los detalles de procesamiento de mensajes. En las secciones siguientes se describen algunas de los agentes más interesantes.</span><span class="sxs-lookup"><span data-stu-id="d177e-p148">The **custom_data** field for an `AGENTINFO` event is used by a variety of Exchange Online agents to log message processing details. Some of the more interesting agents are described in the following sections.</span></span>

#### <a name="spam-filter-agent"></a><span data-ttu-id="d177e-312">Agente de filtro de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="d177e-312">Spam filter agent</span></span>

<span data-ttu-id="d177e-p149">Un valor de **custom_data** que comienza con `S:SFA` va desde el agente de filtro de spam. En la siguiente tabla se describen los detalles de la clave:</span><span class="sxs-lookup"><span data-stu-id="d177e-p149">A **custom_data** value that starts with `S:SFA` is from the spam filter agent. The key details are described in the following table:</span></span>

|<span data-ttu-id="d177e-315">**Valor**</span><span class="sxs-lookup"><span data-stu-id="d177e-315">**Value**</span></span>|<span data-ttu-id="d177e-316">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d177e-316">**Description**</span></span>|
|:-----|:-----|
|`SFV=NSPM`|<span data-ttu-id="d177e-317">El mensaje se marcó como correo seguro y se envió a los destinatarios correspondientes.</span><span class="sxs-lookup"><span data-stu-id="d177e-317">The message was marked as non-spam and was sent to the intended recipients.</span></span>|
|`SFV=SPM`|<span data-ttu-id="d177e-318">El filtro de contenido marcó el mensaje como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="d177e-318">The message was marked as spam by the content filter.</span></span>|
|`SFV=BLK`|<span data-ttu-id="d177e-319">Se omitió el filtrado y se bloqueó el mensaje porque proviene de un remitente bloqueado.</span><span class="sxs-lookup"><span data-stu-id="d177e-319">Filtering was skipped and the message was blocked because it originated from a blocked sender.</span></span>|
|`SFV=SKS`|<span data-ttu-id="d177e-p150">El mensaje se marcó como correo no deseado antes de que el filtro de contenido lo procesara. Esto incluye los mensajes que coinciden con una regla de transporte que marca el mensaje automáticamente como correo no deseado y omite otros tipos de filtrado.</span><span class="sxs-lookup"><span data-stu-id="d177e-p150">The message was marked as spam prior to being processed by the content filter. This includes messages where the message matched a Transport rule to automatically mark it as spam and bypass all additional filtering.</span></span>|
|`SCL=<number>`|<span data-ttu-id="d177e-322">Para más información sobre los distintos valores SCL y su significado, vea [Niveles de confianza de correo no deseado](https://technet.microsoft.com/library/jj200686.aspx).</span><span class="sxs-lookup"><span data-stu-id="d177e-322">For more information about the different SCL values and what they mean, see [Spam confidence levels](https://technet.microsoft.com/library/jj200686.aspx).</span></span>|
|`PCL=<number>`|<span data-ttu-id="d177e-p151">Valor de nivel de confianza de protección antiphishing (PCL) del mensaje. Se puede interpretar del mismo modo que los valores de SCL descritos en [Niveles de confianza de correo no deseado](https://technet.microsoft.com/library/jj200686.aspx).  </span><span class="sxs-lookup"><span data-stu-id="d177e-p151">The Phishing Confidence Level (PCL) value of the message. These can be interpreted the same way as the SCL values documented in [Spam confidence levels](https://technet.microsoft.com/library/jj200686.aspx).</span></span>|
|`DI=SB`|<span data-ttu-id="d177e-325">Se bloqueó el remitente del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d177e-325">The sender of the message was blocked.</span></span>|
|`DI=SQ`|<span data-ttu-id="d177e-326">El mensaje se puso en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="d177e-326">The message was quarantined.</span></span>|
|`DI=SD`|<span data-ttu-id="d177e-327">El mensaje se eliminó.</span><span class="sxs-lookup"><span data-stu-id="d177e-327">The message was deleted.</span></span>|
|`DI=SJ`|<span data-ttu-id="d177e-328">El mensaje se envió a la carpeta de correo no deseado del destinatario.</span><span class="sxs-lookup"><span data-stu-id="d177e-328">The message was sent to the recipient's Junk Email folder.</span></span>|
|`DI=SN`|<span data-ttu-id="d177e-p152">El mensaje se enrutó a través del grupo de entrega de mayor riesgo. Para obtener más información, vea el [grupo de alto riesgo de entrega para los mensajes salientes](https://technet.microsoft.com/library/jj200746.aspx).</span><span class="sxs-lookup"><span data-stu-id="d177e-p152">The message was routed through the higher risk delivery pool. For more information, see [High-risk delivery pool for outbound messages](https://technet.microsoft.com/library/jj200746.aspx).</span></span>|
|`DI=SO`|<span data-ttu-id="d177e-331">El mensaje se enrutó a través del grupo de entrega saliente normal.</span><span class="sxs-lookup"><span data-stu-id="d177e-331">The message was routed through the normal outbound delivery pool.</span></span>|
|<span data-ttu-id="d177e-332">' SFS = [a]</span><span class="sxs-lookup"><span data-stu-id="d177e-332">\`SFS=[a]</span></span>|<span data-ttu-id="d177e-333">SFS = [b]'</span><span class="sxs-lookup"><span data-stu-id="d177e-333">SFS=[b]\`</span></span>|<span data-ttu-id="d177e-334">Indica que se coincidió con reglas de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="d177e-334">This denotes that spam rules were matched.</span></span>|
|`IPV=CAL`|<span data-ttu-id="d177e-335">El mensaje se permitió a través de los filtros de correo no deseado porque la dirección IP estaba incluida en una lista de direcciones IP permitidas en el filtro de conexión.</span><span class="sxs-lookup"><span data-stu-id="d177e-335">The message was allowed through the spam filters because the IP address was specified in an IP Allow list in the connection filter.</span></span>|
|`H=<EHLOstring>`|<span data-ttu-id="d177e-336">La cadena HELO o EHLO del servidor de correo electrónico de conexión.</span><span class="sxs-lookup"><span data-stu-id="d177e-336">The HELO or EHLO string of the connecting email server.</span></span>|
|`PTR=<ReverseDNS>`|<span data-ttu-id="d177e-337">Registro PTR de la dirección IP de envío, también denominado dirección DNS inversa.</span><span class="sxs-lookup"><span data-stu-id="d177e-337">The PTR record of the sending IP address, also known as the reverse DNS address.</span></span>|

<span data-ttu-id="d177e-338">Un valor de **custom_data** de ejemplo para un mensaje que se filtra como correo no deseado como esta:</span><span class="sxs-lookup"><span data-stu-id="d177e-338">An example **custom_data** value for a message that's filtered for spam like this:</span></span>

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a><span data-ttu-id="d177e-339">Agente de filtro de malware</span><span class="sxs-lookup"><span data-stu-id="d177e-339">Malware filter agent</span></span>

<span data-ttu-id="d177e-p153">Un valor de **custom_data** que comienza con `S:AMA` va desde el agente de filtro de malware. En la siguiente tabla se describen los detalles de la clave:</span><span class="sxs-lookup"><span data-stu-id="d177e-p153">A **custom_data** value that starts with `S:AMA` is from the malware filter agent. The key details are described in the following table:</span></span>

|<span data-ttu-id="d177e-342">**Valor**</span><span class="sxs-lookup"><span data-stu-id="d177e-342">**Value**</span></span>|<span data-ttu-id="d177e-343">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d177e-343">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d177e-344">' AMA = SUMA</span><span class="sxs-lookup"><span data-stu-id="d177e-344">\`AMA=SUM</span></span>|<span data-ttu-id="d177e-345">v=1</span><span class="sxs-lookup"><span data-stu-id="d177e-345">v=1</span></span>|<span data-ttu-id="d177e-346">` or `AMA=EV</span><span class="sxs-lookup"><span data-stu-id="d177e-346">` or `AMA=EV</span></span>|<span data-ttu-id="d177e-347">v = 1'</span><span class="sxs-lookup"><span data-stu-id="d177e-347">v=1\`</span></span>|<span data-ttu-id="d177e-p154">El mensaje se determinó que contengan malware. `SUM` indica cualquier número de motores de podría ha detectado el malware. `EV` indica que se detectó el malware por un motor específico. Cuando se detecta malware por un motor de que esto desencadena las acciones posteriores.</span><span class="sxs-lookup"><span data-stu-id="d177e-p154">The message was determined to contain malware. `SUM` indicates the malware could've been detected by any number of engines. `EV` indicates the malware was detected by a specific engine. When malware is detected by an engine this triggers the subsequent actions.</span></span>|
|`Action=r`|<span data-ttu-id="d177e-352">El mensaje se reemplazó.</span><span class="sxs-lookup"><span data-stu-id="d177e-352">The message was replaced.</span></span>|
|`Action=p`|<span data-ttu-id="d177e-353">El mensaje se omitió.</span><span class="sxs-lookup"><span data-stu-id="d177e-353">The message was bypassed.</span></span>|
|`Action=d`|<span data-ttu-id="d177e-354">El mensaje se difirió.</span><span class="sxs-lookup"><span data-stu-id="d177e-354">The message was deferred.</span></span>|
|`Action=s`|<span data-ttu-id="d177e-355">El mensaje se eliminó.</span><span class="sxs-lookup"><span data-stu-id="d177e-355">The message was deleted.</span></span>|
|`Action=st`|<span data-ttu-id="d177e-356">El mensaje se omitió.</span><span class="sxs-lookup"><span data-stu-id="d177e-356">The message was bypassed.</span></span>|
|`Action=sy`|<span data-ttu-id="d177e-357">El mensaje se omitió.</span><span class="sxs-lookup"><span data-stu-id="d177e-357">The message was bypassed.</span></span>|
|`Action=ni`|<span data-ttu-id="d177e-358">El mensaje se rechazó.</span><span class="sxs-lookup"><span data-stu-id="d177e-358">The message was rejected.</span></span>|
|`Action=ne`|<span data-ttu-id="d177e-359">El mensaje se rechazó.</span><span class="sxs-lookup"><span data-stu-id="d177e-359">The message was rejected.</span></span>|
|`Action=b`|<span data-ttu-id="d177e-360">El mensaje se bloqueó.</span><span class="sxs-lookup"><span data-stu-id="d177e-360">The message was blocked.</span></span>|
|`Name=<malware>`|<span data-ttu-id="d177e-361">Se detectó el nombre del malware.</span><span class="sxs-lookup"><span data-stu-id="d177e-361">The name of the malware that was detected.</span></span>|
|`File=<filename>`|<span data-ttu-id="d177e-362">El nombre del archivo que contiene el malware.</span><span class="sxs-lookup"><span data-stu-id="d177e-362">The name of the file that contained the malware.</span></span>|

<span data-ttu-id="d177e-363">Un valor de **custom_data** de ejemplo para un mensaje que contiene el malware tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="d177e-363">An example **custom_data** value for a message that contains malware looks like this:</span></span>

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a><span data-ttu-id="d177e-364">Agente de reglas de transporte</span><span class="sxs-lookup"><span data-stu-id="d177e-364">Transport rule agent</span></span>

<span data-ttu-id="d177e-p155">Un valor de **custom_data** que comienza con`S:TRA` va desde el agente de reglas de transporte para las reglas de flujo de correo (también conocida como reglas de transporte). En la siguiente tabla se describen los detalles de la clave:</span><span class="sxs-lookup"><span data-stu-id="d177e-p155">A **custom_data** value that starts with`S:TRA` is from the transport rule agent for mail flow rules (also known as transport rules). The key details are described in the following table:</span></span>

|<span data-ttu-id="d177e-367">**Valor**</span><span class="sxs-lookup"><span data-stu-id="d177e-367">**Value**</span></span>|<span data-ttu-id="d177e-368">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d177e-368">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d177e-369">' ETR</span><span class="sxs-lookup"><span data-stu-id="d177e-369">\`ETR</span></span>|<span data-ttu-id="d177e-370">ruleId =<guid>\`</span><span class="sxs-lookup"><span data-stu-id="d177e-370">ruleId=<guid>\`</span></span>|<span data-ttu-id="d177e-371">El identificador de regla coincidente.</span><span class="sxs-lookup"><span data-stu-id="d177e-371">The rule ID that was matched.</span></span>|
|`St=<datetime>`|<span data-ttu-id="d177e-372">La fecha y la hora en UTC cuando se produjo la coincidencia de regla.</span><span class="sxs-lookup"><span data-stu-id="d177e-372">The date and time in UTC when the rule match occurred.</span></span>|
|`Action=<ActionDefinition>`|<span data-ttu-id="d177e-p156">La acción que se ha aplicado. Para obtener una lista de acciones disponibles, vea [Mail flow acciones de regla en Exchange Online](https://technet.microsoft.com/library/jj919237.aspx).</span><span class="sxs-lookup"><span data-stu-id="d177e-p156">The action that was applied. For a list of available actions, see [Mail flow rule actions in Exchange Online](https://technet.microsoft.com/library/jj919237.aspx).</span></span>|
|`Mode=<Mode>`|<span data-ttu-id="d177e-p157">El modo de la regla. Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="d177e-p157">The mode of the rule. Valid values are: </span></span><br/><span data-ttu-id="d177e-377">• **Exigir**: se exigirán todas las acciones de la regla.</span><span class="sxs-lookup"><span data-stu-id="d177e-377">• **Enforce**: All actions on the rule will be enforced.</span></span> <br/><span data-ttu-id="d177e-378">• **Probar con sugerencias de directiva:**: acciones de cualquier sugerencia de directiva que se van a enviar, pero no se actuará sobre otras acciones de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d177e-378">• **Test with Policy Tips:**: Any Policy Tip actions will be sent, but other enforcement actions will not be acted on.</span></span> <br/><span data-ttu-id="d177e-379">• **Probar sin sugerencias de directiva**: las acciones aparecerán en un archivo de registro, pero no se notificará remitentes de ninguna manera y no se actuará sobre las acciones.</span><span class="sxs-lookup"><span data-stu-id="d177e-379">• **Test without Policy Tips**: Actions will be listed in a log file, but senders will not be notified in any way, and enforcement actions will not be acted on.</span></span>|

<span data-ttu-id="d177e-380">Un valor de **custom_data** de ejemplo para un mensajes que coincide con las condiciones de una regla de flujo de correo tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="d177e-380">An example **custom_data** value for a messages that matches the conditions of a mail flow rule looks like this:</span></span>

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`

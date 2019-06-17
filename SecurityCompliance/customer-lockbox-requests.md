---
title: Solicitudes de caja de seguridad del cliente de Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre las solicitudes de caja de caja del cliente que le permiten controlar cómo un ingeniero de soporte técnico de Microsoft puede tener acceso a los datos cuando se tiene un problema.
ms.openlocfilehash: f3cfdec6521cd5fe0bcb7007b27ce128ae3b2a1d
ms.sourcegitcommit: 62447503300376aa95dd05fb5276f93a9f6a20b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2019
ms.locfileid: "34927583"
---
# <a name="customer-lockbox-in-office-365"></a>Caja de caja de cliente en Office 365

> [!NOTE]
> En este artículo se proporcionan instrucciones de implementación y configuración para una característica que actualmente solo está disponible para las organizaciones que tienen una suscripción de Microsoft 365 E5, Office 365 E5, protección de la información y cumplimiento o complemento avanzado de cumplimiento.

La caja de caja del cliente garantiza que Microsoft no pueda obtener acceso al contenido para realizar una operación de servicio sin su aprobación explícita. Lockbox del cliente le ofrece el flujo de trabajo de aprobación para las solicitudes de acceso al contenido.

Ocasionalmente, los ingenieros de Microsoft ayudan a solucionar problemas y solucionar problemas notificados por los clientes en el proceso de soporte. Normalmente, los problemas se arreglan mediante amplias herramientas de telemetría y depuración que Microsoft pone a su servicio. Sin embargo, en algunos casos es necesario que un ingeniero de Microsoft tenga acceso al contenido del cliente para determinar la causa raíz y corregir el problema. La caja de caja del cliente requiere que el ingeniero solicite el acceso del cliente como paso final en el flujo de trabajo de aprobación. Esto proporciona a las organizaciones la opción de aprobar o denegar estas solicitudes y proporcionar control de acceso directo al cliente.

### <a name="customer-lockbox-overview-video"></a>Vídeo de información general del Lockbox del cliente

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

> [!NOTE]
> La caja de seguridad del cliente admite solicitudes para acceder a datos en Exchange Online, SharePoint Online y OneDrive para la empresa. Para recomendar el soporte para otros servicios de Office 365, envíe una solicitud a [UserVoice de office 365](https://office365.uservoice.com/).

## <a name="customer-lockbox-workflow"></a>Flujo de trabajo del Lockbox del cliente

Los pasos siguientes describen el flujo de trabajo típico cuando un ingeniero de Microsoft inicia una solicitud de caja de caja del cliente:

1. Alguien de una organización tiene un problema con su buzón de correo de Office 365.

2. Una vez que el usuario solucione el problema, pero no puede corregirlo, abrirá una solicitud de soporte técnico con soporte técnico de Microsoft.

3. Un ingeniero de soporte técnico revisa la solicitud de servicio y determina la necesidad de tener acceso al contenido de Exchange online del cliente para reparar el problema.

4. El ingeniero de soporte técnico inicia sesión en la herramienta de solicitud de caja de herramientas del cliente y realiza una solicitud de acceso a datos especificando el nombre del inquilino del cliente, el número de solicitud de servicio y la duración estimada para la cual se necesita acceso a los datos.

5. Una vez que un administrador de soporte de Microsoft aprueba la solicitud, el Lockbox del cliente envía al aprobador designado en la organización del cliente una notificación de correo electrónico sobre la solicitud de acceso pendiente de Microsoft.

    ![Ejemplo de notificación de correo electrónico del Lockbox del cliente](media/CustomerLockbox1.png)

   > [!NOTE]
   > Cualquier usuario que tenga asignado el rol de administrador aprobador de [acceso de Lockbox de cliente](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) en el centro de administración de Microsoft 365 puede aprobar solicitudes de caja de caja de cliente.

7. El aprobador inicia sesión en el centro de administración de 365 de Microsoft y aprueba la solicitud. Este paso desencadena la creación de un registro de auditoría disponible mediante la búsqueda en el registro de auditoría de Office 365. Para obtener más información, consulte la sección [Auditing Customer Lockbox](#auditing-customer-lockbox-requests) requests.

   Si el cliente rechaza la solicitud o la solicitud no se aprueba en un plazo de 12 horas, la solicitud expira y no se concede acceso al ingeniero de Microsoft.

   > [!IMPORTANT]
   > Microsoft no incluye ningún vínculo en las notificaciones de correo electrónico de caja del cliente que requieran que inicie sesión en Office 365.

8. Una vez que el cliente aprueba la solicitud, el ingeniero de Microsoft recibe el mensaje de aprobación, inicia sesión en Exchange Online y corrige el problema del cliente. Los ingenieros de Microsoft tienen la duración solicitada para solucionar el problema después de que el acceso se haya revocado automáticamente.

> [!NOTE]
> Todas las acciones realizadas por un ingeniero de Microsoft se registran en el registro de auditoría de Office 365. Puede buscar y revisar estos registros de auditoría y se pueden buscar y revisar.

## <a name="turn-customer-lockbox-requests-on-or-off"></a>Activar o desactivar las solicitudes de caja de caja de clientes

Un administrador de Office 365 puede activar los controles de caja de caja del cliente en el centro de administración de Microsoft 365. Cuando la caja de las cajas de trabajo del cliente está activada, Microsoft debe obtener la aprobación de la organización antes de obtener acceso a cualquiera de sus contenidos.

> [!NOTE]
> Para llevar a cabo el siguiente procedimiento, debe ser administrador global de la organización de Microsoft 365 u Office 365 o tener asignado el rol de administrador de aprobador de **acceso de Lockbox del cliente** .

1. Vaya a [https://admin.microsoft.com](https://admin.microsoft.com) e inicie sesión con su cuenta profesional o educativa.

2. Haga clic en **configuración > privacidad & seguridad**.

    ![Edición de la configuración de la caja de opciones del cliente en el centro de administración](media/CustomerLockbox2.png)

3. En el icono **Lockbox del cliente** , haga clic en **Editar**y, a continuación, mueva el botón de alternancia a **activado** o desactivado para activar o desactivar la característica. ****

    ![Require approval for Customer Lockbox](media/CustomerLockbox4.png)

## <a name="approve-or-deny-a-customer-lockbox-request"></a>Aprobar o denegar una solicitud de caja de caja del cliente

> [!NOTE]
> Para llevar a cabo el siguiente procedimiento, debe ser administrador global de la organización de Microsoft 365 u Office 365 o tener asignado el rol de administrador de aprobador de **acceso de Lockbox del cliente** .

1. Vaya a [https://admin.microsoft.com](https://admin.microsoft.com) e inicie sesión con su cuenta profesional o educativa.

2. Haga clic en **soporte > solicitudes de caja de caja del cliente**.

    ![Haga clic en soporte técnico y en solicitudes de caja de caja del cliente](media/CustomerLockbox5.png)

    Se muestra una lista de solicitudes de caja de caja de clientes.

    ![Lista de solicitudes de caja de caja del cliente](media/CustomerLockbox6.png)

3. Seleccione una solicitud de caja de caja del cliente y haga clic en **aprobar** o denegar. ****

    ![Aprobar o denegar solicitudes de caja de caja de cliente](media/CustomerLockbox7.png)

    Se muestra un mensaje de confirmación sobre la aprobación de la solicitud de caja de trabajo del cliente.

    ![Aprobar o denegar solicitudes de caja de caja de cliente](media/CustomerLockbox8.png)

## <a name="auditing-customer-lockbox-requests"></a>Auditoría de solicitudes de caja de comprobación del cliente 

Los registros de auditoría que corresponden a las solicitudes de caja de seguridad del cliente se registran en el registro de auditoría de Office 365 y se puede tener acceso a ellos mediante la [herramienta de búsqueda de registros de auditoría](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance) del centro de seguridad & cumplimiento de Office 365. Las acciones relacionadas con un cliente que aceptan o deniegan una solicitud de caja de control del cliente y las acciones realizadas por los ingenieros de Microsoft (cuando se aprueban las solicitudes de acceso) se registran en el registro de auditoría de Office 365. Puede buscar y revisar estos registros de auditoría.

> [!NOTE]
> Debe tener asignado el rol registros de auditoría con permiso de vista o registros de auditoría en Exchange Online para buscar en el registro de auditoría de 365 de Office. Para obtener más información, vea [Buscar en el registro de auditoría del Centro de seguridad y cumplimiento de Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin).

### <a name="search-the-audit-log-for-activity-related-to-customer-lockbox-requests"></a>Buscar en el registro de auditoría actividades relacionadas con solicitudes de caja de control del cliente

Esta es la manera de crear una consulta de búsqueda de registro de auditoría para devolver registros de auditoría relacionados con la caja de caja del cliente:

1. Vaya a [https://protection.office.com](https://protection.office.com).
  
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.

3. En el panel izquierdo del centro de seguridad & cumplimiento, haga clic en buscar en el**registro de auditoría**de **& investigación** > .

    Se muestra la página de **búsqueda de registros de auditoría** .

    ![Página de búsqueda de registros de auditoría](media/auditlogsearch1.png)
  
4. Configure los siguientes criterios de búsqueda:

    a. **Actividades** : Deje este campo en blanco para que la búsqueda devuelva registros de auditoría para todas las actividades. Esto es necesario para devolver los registros de auditoría relacionados con las solicitudes de caja de control del cliente y la actividad correspondiente realizada por los ingenieros de Microsoft.

    b. Fecha de **Inicio** y **fecha** de finalización: Seleccione un intervalo de fechas y horas para mostrar los eventos que se produjeron dentro de ese período.

    c. **Usuarios** : Deje este campo en blanco.

    d. **Archivo, carpeta o sitio** : Deje este campo en blanco.

5. Haga clic en **Buscar** para ejecutar la búsqueda con los criterios de búsqueda. 

    Los resultados de la búsqueda se cargan y, después de unos segundos, se muestran en **resultados** en la página de **búsqueda de registros de auditoría** .

6. Haga clic en **filtrar resultados** en la página de resultados de búsqueda y realice una de las siguientes acciones:

   - Para mostrar registros de auditoría relacionados con un aprobador en la organización que apruebe o deniegue una solicitud de caja de control del cliente: en el cuadro de la columna **actividad** , escriba **set-AccessToCustomerDataRequest**.

   - Para mostrar registros de auditoría relacionados con un ingeniero de Microsoft llevando a cabo acciones en respuesta a una solicitud de caja de control del cliente aprobada: en el cuadro de la columna **usuario** , escriba **operador de Microsoft**. Tenga en cuenta que la acción realizada por el ingeniero se muestra en la columna **actividad** .

      ![Filtrar por "operador de Microsoft" para mostrar registros de auditoría](media/CustomerLockbox10.png)

7. En la lista de resultados, haga clic en un registro de auditoría para mostrarlo.

### <a name="audit-record-for-a-customer-lockbox-access-request"></a>Registro de auditoría para una solicitud de acceso de Lockbox de cliente

Cuando una persona de su organización aprueba o deniega una solicitud de caja de control del cliente, se registra un registro de auditoría en el registro de auditoría de Office 365. Este registro contiene la siguiente información. 

| Propiedad Audit record| Descripción|
|:---------- |:----------|
| Fecha       | La fecha y la hora en que se aprobó o denegó la solicitud de caja de caja del cliente.
| Dirección IP | La dirección IP del equipo que el aprobador ha usado para aprobar o denegar una solicitud. |
| User       | La cuenta de servicio BOXServiceAccount\[@\]customerforest. Prod.Outlook.com.            |
| Actividad   | Set-AccessToCustomerDataRequest; se trata de la actividad de auditoría que se registra al aprobar o denegar una solicitud de caja de control del cliente.                                |
| Elemento       | El GUID de la solicitud de caja de caja del cliente                             |

En la siguiente captura de pantalla se muestra un ejemplo de un registro de auditoría que se corresponde con una solicitud de caja de control de cliente aprobada. Si se denegó una solicitud de caja de caja del cliente, el valor del parámetro **ApprovalDecision** sería **Deny**.

![Registro de auditoría para una solicitud de caja de control de cliente aprobada](media/CustomerLockbox9.png)

> [!TIP]
> Para mostrar información más detallada en un registro de auditoría, haga clic en **más información**.

### <a name="audit-record-for-an-action-performed-by-a-microsoft-engineer"></a>Registro de auditoría para una acción realizada por un ingeniero de Microsoft

Como se ha explicado anteriormente, las acciones realizadas por un ingeniero de Microsoft después de que se aprueba una solicitud de caja de control del cliente (y esto puede tener como resultado el acceso al contenido del cliente) se registran en el registro de auditoría. Estos registros contienen la siguiente información.

| Propiedad Audit record| Descripción|
|:---------- |:----------|
| Fecha       | Fecha y hora en que se realizó la acción. Tenga en cuenta que la hora en que se realizó esta acción será en un plazo de 4 horas desde el momento en que se aprobó la solicitud de caja de tiempo del cliente.              |
| Dirección IP | La dirección IP del equipo que utilizó el ingeniero de Microsoft. |
| User       | Operador de Microsoft; Este valor indica que este registro está relacionado con una solicitud de caja de caja del cliente.                                  |
| Actividad   | Nombre de la actividad realizada por el ingeniero de Microsoft.|
| Elemento       | \<está\>                                             |


## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

#### <a name="which-office-365-services-does-customer-lockbox-apply-to"></a>¿A qué servicios de Office 365 se aplica el Lockbox de clientes?

La caja de seguridad del cliente es compatible actualmente con Exchange Online, SharePoint Online y OneDrive para la empresa.

#### <a name="is-customer-lockbox-available-to-all-office-365-customers"></a>¿La caja de bloqueo del cliente está disponible para todos los clientes de Office 365?

La caja de comprobación del cliente se incluye en las suscripciones de Microsoft 365 u Office 365 E5 y se puede Agregar a otros planes con una suscripción de protección y cumplimiento de la información o una suscripción complementaria de cumplimiento avanzado. Para obtener más información, consulte [planes y precios](https://products.office.com/business/office-365-enterprise-e5-business-software) .

#### <a name="what-is-customer-content"></a>¿Qué es el contenido del cliente?

El contenido del cliente es los datos creados por los usuarios de servicios y aplicaciones de Office 365. Algunos ejemplos de contenido de cliente son:

- Cuerpo de correo electrónico o datos adjuntos de correo electrónico

- Contenido del sitio de SharePoint

- Información en el cuerpo de un archivo de SharePoint

- Cuerpo de archivo de presentación de Skype empresarial

- Mensajes instantáneos (mi) o conversaciones de voz

- BLOB generado por el cliente o datos de almacenamiento estructurados (por ejemplo, contenedores SQL)

- Información de seguridad de propiedad del cliente (por ejemplo, certificados, claves de cifrado y contraseñas)

- Inferencias y todas las inferencias subsiguientes, si el contenido del cliente se mantiene

Para obtener información adicional acerca del contenido del cliente en Office 365, consulte el [centro de confianza de office 365](https://products.office.com/en-US/business/office-365-trust-center-privacy/).

#### <a name="who-is-notified-when-there-is-a-request-to-access-my-content"></a>¿Quién recibe una notificación cuando hay una solicitud para obtener acceso a mi contenido?

Los administradores globales y todos los usuarios que tengan asignado el rol de administrador de aprobador de acceso de Lockbox de cliente recibirán notificación. También son los mismos usuarios que pueden aprobar solicitudes de caja de caja de cliente.

#### <a name="who-can-approve-or-reject-these-requests-in-my-organization"></a>¿Quién puede aprobar o rechazar estas solicitudes en mi organización?

Los administradores globales y todos los usuarios que tengan asignado el rol de administrador de aprobación de acceso de Lockbox del cliente pueden aprobar solicitudes de caja de caja de cliente. Los clientes controlan estas asignaciones de roles en sus organizaciones.

#### <a name="how-do-i-opt-in-to-customer-lockbox"></a>¿Cómo puedo optar por las cajas de caja del cliente?

Un administrador global puede habilitar y configurar las cajas de caja de clientes en el centro de administración de Microsoft 365 o Microsoft 365.

#### <a name="if-i-approve-a-customer-lockbox-request-what-can-the-engineer-do-and-how-will-i-know-what-the-microsoft-engineer-did"></a>Si aprobar una solicitud de caja de caja de cliente, ¿qué puede hacer el ingeniero y cómo sé qué hizo el ingeniero de Microsoft?

Después de aprobar la solicitud de caja de caja de un cliente, el ingeniero de Microsoft concedió estos privilegios necesarios para acceder al contenido del cliente mediante cmdlets aprobados previamente. Las acciones realizadas por los ingenieros de Microsoft en respuesta a las solicitudes de caja de seguridad del cliente se registran y se puede tener acceso a ellas en el registro de auditoría del centro de seguridad & cumplimiento de Office 365.

#### <a name="how-do-i-know-that-microsoft-follows-the-approval-process"></a>¿Cómo sé que Microsoft sigue el proceso de aprobación?

Puede aplicar una referencia cruzada a las notificaciones de aprobación de correo electrónico que se envían a los administradores y los aprobadores de la organización con el historial de solicitudes de caja de trabajo del cliente en el centro de administración de Microsoft 365.

La caja de comprobación del cliente se incluye en el último [Informe de auditoría SOC 1 SSAE 16](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports). Para obtener más información, puede encontrar los últimos informes en el [portal de confianza de servicios de Microsoft](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).

#### <a name="can-microsoft-modify-the-list-of-approvers-for-my-tenant-if-not-how-is-it-prevented"></a>¿Puede Microsoft modificar la lista de aprobadores de mi espacio empresarial? Si no es así, ¿cómo se impide?

Solo un administrador global de su organización puede especificar quiénes pueden aprobar las solicitudes de caja de caja de cliente. Esto significa que solo los miembros del grupo de administradores globales en Azure Active Directory pueden especificar quién puede aprobar la solicitud. La pertenencia al grupo global de administradores en Azure Active Directory solo se administra en la organización.

#### <a name="what-if-i-need-more-information-about-a-content-access-request-to-approve-it"></a>¿Qué debo hacer si necesito más información sobre una solicitud de acceso a contenido para aprobarla?

Cada solicitud de caja de caja de cliente contiene un número de solicitud de servicio de Office 365. Puede ponerse en contacto con el soporte técnico de Microsoft y hacer referencia a este número de servicio para obtener más información sobre la solicitud.

#### <a name="when-a-customer-lockbox-request-is-approved-how-long-are-the-permissions-valid"></a>Cuando se aprueba una solicitud de caja de caja de cliente, ¿cuánto tiempo tienen los permisos válidos?

Actualmente, el período máximo para los permisos de acceso concedidos al ingeniero de Microsoft es de 4 horas. El ingeniero de Microsoft también puede solicitar un período más corto.

#### <a name="how-can-i-get-a-history-of-all-customer-lockbox-requests"></a>¿Cómo puedo obtener un historial de todas las solicitudes de caja de caja de cliente?

Todas las solicitudes de caja de caja de cliente se ven en el centro de administración de Microsoft 365.

#### <a name="how-do-i-correlate-the-content-access-requests-with-the-related-audit-logs"></a>¿Cómo se relacionan las solicitudes de acceso a contenido con los registros de auditoría relacionados?

La fuente de actividades del centro de cumplimiento contiene actividades de registro de caja de comprobación del cliente. Los clientes pueden hacer una referencia cruzada de las actividades del registro de Lockbox del cliente desde la fuente de actividades en la solicitud de correo electrónico que reciben.

#### <a name="what-happens-when-a-customer-doesnt-respond-to-a-customer-lockbox-request"></a>¿Qué sucede cuando un cliente no responde a una solicitud de caja de caja del cliente?

Las solicitudes de caja de caja de cliente tienen una duración predeterminada de 12 horas. Si no responde a una solicitud en un plazo de 12 horas, la solicitud expirará.

#### <a name="what-does-microsoft-do-when-a-customer-rejects-a-customer-lockbox-request"></a>¿Qué hace Microsoft cuando un cliente rechaza una solicitud de caja de caja del cliente?

Si un cliente rechaza una solicitud de caja de caja del cliente, no se produce ningún acceso al contenido del cliente. Si un usuario de su organización sigue experimentando un problema de servicio que requiere que Microsoft tenga acceso al contenido del cliente para resolver el problema, el problema del servicio puede persistir y Microsoft lo informará al usuario.

#### <a name="does-customer-lockbox-protect-against-data-requests-from-law-enforcement-agencies-or-other-third-parties"></a>¿Protege el Lockbox del cliente contra las solicitudes de datos de los cuerpos de cumplimiento de la ley u otras terceras partes?

No. Microsoft toma en serio las solicitudes de terceros sobre los datos de los clientes. Como proveedor de servicios en la nube, Microsoft siempre aboga por la privacidad de los datos del cliente. En el caso de que recibamos una citación, Microsoft siempre intenta redirigir al cliente a la otra persona para obtener la información. (Lea el blog de Brad Martínez: [proteger los datos de clientes de la supervisión gubernamental](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Periódicamente publicamos [información detallada](https://www.microsoft.com/en-us/corporate-responsibility/lerr) sobre las solicitudes de cumplimiento de la ley que recibe Microsoft.

Consulte el [centro de confianza de Microsoft](https://www.microsoft.com/en-us/trustcenter/default.aspx) sobre las solicitudes de datos de terceros y la sección "revelación de datos de clientes" en los [términos de servicios en línea](https://www.microsoft.com/Licensing/product-licensing/products.aspx) para obtener más información.

#### <a name="how-does-microsoft-ensure-that-a-member-of-its-staff-doesnt-have-standing-access-to-customer-content-in-office-365-applications"></a>¿Cómo garantiza Microsoft que un miembro del personal no tiene acceso permanente al contenido del cliente en las aplicaciones de Office 365?

Microsoft implementa medidas preventivas extensivas mediante sistemas de control de acceso y medidas de detectives para identificar y solucionar los intentos de burlar estos sistemas de control de acceso. Office 365 opera con los principios de privilegios mínimos y acceso Just-in-Time. Por lo tanto, ningún personal de Microsoft tiene permiso para acceder al contenido de los clientes de forma continua. Si se concede el permiso, es por una duración limitada. 

Office 365 usa un sistema de control de acceso denominado *Lockbox* para procesar solicitudes de permisos que permiten realizar funciones operativas y administrativas dentro del servicio. Un operador debe solicitar acceso al contenido del cliente mediante el uso de las cajas de caja, lo que, a su vez, requiere que una segunda persona realice una acción en la solicitud (por ejemplo, aprobarla) antes de conceder el acceso. Esa segunda persona no puede ser el solicitante y debe estar designada para aprobar el acceso al contenido del cliente. Solo si la solicitud se aprueba, el operador adquiere el acceso temporal al contenido del cliente. Una vez expirado el período de elevación, el Lockbox revoca el acceso.

Consulte los términos de [servicios en línea](https://www.microsoft.com/licensing/product-licensing/products) para obtener más información sobre los procedimientos de seguridad general de Microsoft.

#### <a name="under-what-circumstances-do-microsoft-engineers-need-access-to-my-content"></a>¿En qué circunstancias los ingenieros de Microsoft necesitan acceso a mi contenido?

El escenario más común donde los ingenieros de Microsoft necesitan tener acceso al contenido de los clientes es cuando el cliente realiza una solicitud de soporte técnico que requiere acceso para la solución de problemas. Un principio básico de Office 365 es que el servicio funciona sin Microsoft Access para el contenido del cliente. Casi todas las operaciones de servicio realizadas por Microsoft son totalmente automatizadas y la implicación humana está muy controlada y se abstrae del contenido del cliente. El objetivo de Office 365 es el acceso al contenido del cliente para admitir el servicio no es necesario hasta que el cliente apruebe una solicitud específica para Microsoft Access.

#### <a name="i-already-thought-my-data-was-secure-with-the-microsoft-cloud-so-why-do-i-need-customer-lockbox"></a>Ya pensé que mis datos estaban seguros con la nube de Microsoft, ¿por qué necesito la caja de seguridad del cliente?

La caja de caja del cliente proporciona una capa de control adicional al ofrecer a los clientes la capacidad de otorgar autorización de acceso explícito para las operaciones de servicio. Al demostrar que se han implementado los procedimientos para la autorización explícita de acceso a datos, la caja de seguridad del cliente también ayuda a los clientes a cumplir ciertas obligaciones de cumplimiento, como HIPAA y FEDRAMP.

---
title: Aplicar protección a los datos personales de Office 365
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Obtenga información sobre cómo usar las directivas DLP para proteger datos personales en Office 365.
ms.openlocfilehash: c0b78611a81452ecd8cb8993842c26f6012bb736
ms.sourcegitcommit: 15983a08a4ae9c2050344172c7e957830ce3867e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2019
ms.locfileid: "30373951"
---
# <a name="apply-protection-to-personal-data-in-office-365"></a>Aplicar protección a los datos personales de Office 365

La protección de información personal en Office 365 incluye el uso de funciones de prevención de pérdida de datos. Con las directivas de prevención de pérdida de datos (DLP) del Centro de seguridad y cumplimiento de Office 365, puede identificar, supervisar y proteger automáticamente información confidencial en todo Office 365.

En este tema se describe cómo se usan las DLP para proteger los datos personales. Este tema también muestra otras capacidades de protección que pueden usarse para cumplir el RGPD, incluyendo la configuración de permisos en bibliotecas de SharePoint y el uso de directivas de acceso de dispositivo.

## <a name="apply-protection-using-data-loss-prevention-in-office-365"></a>Aplicar protección mediante la prevención de pérdida de datos en Office 365

Con la DLP, puede:

-   Identificar información confidencial en varias ubicaciones.

-   Evitar el uso compartido accidental de información confidencial.

-   Ayudar a los usuarios a aprender a cumplir sin interrumpir el flujo de trabajo.

-   Ver informes de DLP con contenido que coincida con las directivas DLP de su organización.

Para obtener más información, consulte [Información general sobre directivas de prevención de pérdida de datos](https://support.office.com/es-ES/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e).

![Opciones para crear una directiva de prevención de pérdida de datos](Media/Apply-protection-to-personal-data-in-Office-365-image1.png)

Esta ilustración muestra las opciones para crear una directiva DLP:

-   Elija la protección que se aplicará. La protección puede incluir:

    -   Sugerencias de directiva para los usuarios

    -   Informes de correo electrónico para los administradores

    -   Impedir el uso compartido externamente, internamente, o ambos

-   Elija los criterios para aplicar la protección. Aplique la protección a los documentos con este tipo de contenido: puede configurar la directiva para usar tipos de información confidencial o etiquetas.

### <a name="using-dlp-for-gdpr-compliance"></a>Uso de DLP para el cumplimiento de RGPD

Uno de los usos principales de DLP de Office 365 es identificar datos personales relacionados con temas de datos de la UE en su entorno de Office 365. DLP de Office 365 puede notificar a sus equipos de cumplimiento dónde se almacena información personal en SharePoint Online y OneDrive para la Empresa o cuándo los usuarios envían correo electrónico con información personal. DLP puede proporcionar sugerencias de directiva a sus empleados cuando trabajan con información personal de residentes de la UE.

Instruir y aumentar el conocimiento sobre dónde se almacenan los datos de residentes de la UE en su entorno y cómo sus empleados pueden administrarlos representa un nivel de protección de información con DLP de Office 365. A menudo, los empleados que ya tengan acceso a este tipo de información requieren este acceso para realizar su trabajo diario. Al aplicar directivas DLP para ayudar a cumplir con el RGPD no necesitará restringir el acceso.

Sin embargo, el cumplimiento del RGPD normalmente implica una evaluación de riesgos de la organización desde la perspectiva de la seguridad de la información y legal, la identificación de qué tipo de información personal se almacena y dónde, así como si hay una justificación legal para almacenar y procesar la información. Con esta evaluación, implementar directivas para proteger la organización y cumplir con el RGPD puede hacer necesario quitar el acceso de los empleados a los documentos que contengan información personal para temas de datos de la UE. En los casos donde se requiera protección adicional, puede configurar protección adicional de DLP.

En la siguiente tabla se muestran tres configuraciones para incrementar la protección mediante DLP. La primera configuración, reconocimiento, puede usarse como punto mínimo inicial y nivel de protección para RGPD.

### <a name="example-protection-levels-that-can-be-configured-with-dlp-policies-and-used-for-gdpr-compliance"></a>Ejemplo de niveles de protección que pueden configurarse con directivas DLP y utilizarse para el cumplimiento de RGPD

<table>
<thead>
<tr class="header">
<th align="left"><strong>Nivel de protección</strong></th>
<th align="left"><strong>Configuración de DLP para documentos con información personal relacionada con datos de la UE</strong></th>
<th align="left"><strong>Beneficios y riesgos</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Reconocimiento</td>
<td align="left"><p>Envíe notificaciones por correo electrónico a equipos de cumplimiento cuando estos datos se encuentren en documentos de SharePoint Online y OneDrive para la Empresa.</p>
<p>Personalice y muestre sugerencias de directiva a los empleados en SharePoint y OneDrive para la Empresa al acceder a documentos que contienen datos.</p>
<p>Detecte y notifique cuándo se comparten datos.</p></td>
<td align="left"><p>Informe al personal con equipos de cumplimiento, así como mediante los empleados, sobre dónde se almacenan los datos.</p>
<p>Forme a los empleados sobre la directiva corporativa para controlar documentos que contienen este tipo de datos.</p>
<p>Impida que los empleados compartan datos de forma interna o externa.</p>
<p>Puede revisar los informes DLP de datos compartidos y decidir si quiere aumentar la protección.</p></td>
</tr>
<tr class="even">
<td align="left">Evitar el uso compartido externo</td>
<td align="left"><p>Restrinja el acceso a documentos que contienen estos datos en SharePoint Online y OneDrive para la Empresa cuando ese contenido se comparta con usuarios externos.</p>
<p>Evite el envío de correos electrónicos con documentos que contienen datos a destinatarios externos.</p>
<p>Detecte y notifique cuándo se comparten datos.</p></td>
<td align="left"><p>Evite el uso compartido externo de datos y permita a los empleados trabajar con esos datos de forma interna.</p>
<p>Puede revisar los informes DLP de datos compartidos de forma interna y decidir si quiere aumentar la protección.</p></td>
</tr>
<tr class="odd">
<td align="left">Evitar el uso compartido interno y externo</td>
<td align="left"><p>Restrinja el acceso a documentos que contienen datos en SharePoint Online y OneDrive para la Empresa cuando ese contenido se comparta de forma interna o externa.</p>
<p>Evite enviar correos electrónicos que contienen datos a destinatarios internos o externos.</p></td>
<td align="left"><p>Evita el uso compartido interno y externo de estos datos.</p>
<p>Es posible que los empleados puedan completar tareas que requieran el uso de estos datos.</p>
<p>Puede revisar los informes DLP de datos compartidos de forma interna o externa y decidir si es necesario entrenamiento para los usuarios finales.</p></td>
</tr>
</tbody>
</table>

Nota: A medida que aumentan los niveles de protección, la capacidad de los usuarios de acceder a información disminuirá en algunos casos y podría afectar a su productividad o capacidad para completar las tareas del día a día. Aumentar los niveles de protección implementando directivas que afectan a los empleados normalmente viene acompañado de aprendizaje para usuarios finales para instruirlos sobre las directivas de seguridad y procedimientos y ayudarles a seguir siendo productivos en un entorno más seguro.

### <a name="example-dlp-policy-for-gdpr--awareness"></a>Ejemplo de directiva DLP para RGPD: reconocimiento 

Nombre: Reconocimiento de datos personales sujetos a RGPD.

Descripción: muestre sugerencias de directiva a los empleados, notifique a los equipos de cumplimiento cuando se encuentran estos datos en documentos de SharePoint Online y OneDrive para la Empresa, detecte y notifique cuando estos datos se comparten fuera de su organización.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Control</strong></th>
<th align="left"><strong>Configuración</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Elegir qué información quiere proteger</td>
<td align="left">Seleccione una plantilla de directiva personalizada.</td>
</tr>
<tr class="even">
<td align="left">Ubicaciones</td>
<td align="left">Todas las ubicaciones en Office 365</td>
</tr>
<tr class="odd">
<td align="left">Encontrar contenido que incluya</td>
<td align="left">Haga clic en "Editar" y agregue todos los tipos de información confidencial creados en su entorno.</td>
</tr>
<tr class="even">
<td align="left">Detectar si este contenido se comparte</td>
<td align="left">Active esta casilla y seleccione "con usuarios externos a la organización".</td>
</tr>
<tr class="odd">
<td align="left">Notificar a los usuarios cuando el contenido coincide con la configuración de directiva</td>
<td align="left"><p>Active esta casilla ("Mostrar sugerencias de directiva a los usuarios y enviarles una notificación por correo electrónico".)</p>
<p>Haga clic en "Personalizar la información y el correo electrónico" y adáptelos a su entorno. Consulte las notificaciones predeterminadas en este artículo: <a href="https://support.office.com/en-us/article/Send-email-notifications-and-show-policy-tips-for-DLP-policies-87496bc5-9601-4473-8021-cb05c71369c1?ui=en-US&amp;rs=en-US&amp;ad=US">Enviar notificaciones de correo electrónico y mostrar las sugerencias de directiva de directivas DLP</a>.</p></td>
</tr>
<tr class="even">
<td align="left">Detectar si se está compartiendo una cantidad determinada de información confidencial a la vez</td>
<td align="left"><p>"Detectar el contenido que se está compartiendo que incluye: un mínimo de ___ instancias del mismo tipo de información confidencial": establézcalo en 1.</p>
<p>"Enviar informes de incidentes por correo electrónico": active esta casilla. Haga clic en "Elegir qué incluir en el informe y quién lo recibe". Asegúrese de agregar al equipo de cumplimiento.</p>
<p>"Restringir quién puede acceder al contenido e invalidar la directiva": desactive esta casilla para recibir notificaciones sobre información confidencial sin impedir que los usuarios accedan a esa información.</p></td>
</tr>
</tbody>
</table>

“Todas las ubicaciones” incluye:

-   SharePoint Online

-   Cuentas de OneDrive para la Empresa

-   Buzones de Exchange

Dado que la búsqueda de contenido actualmente no permite comprobar los tipos de información confidencial con el correo electrónico, considere la posibilidad de crear directivas independientes de Exchange con un subconjunto de tipos de información confidencial de cada directiva y supervisar la implementación de estas directivas.

## <a name="additional-protection-you-can-apply-to-protect-personal-data-in-office-365"></a>Protección adicional que puede aplicar para proteger los datos personales de Office 365

Las directivas de protección de pérdida de datos, las etiquetas y los tipos de información confidencial le ayudan a identificar los documentos que contienen datos específicos y a aplicar la protección. Sin embargo, estas protecciones dependen de que se configuren los permisos adecuados para el acceso a datos, de que las cuentas de usuario no estén en peligro y de que los dispositivos estén en buen estado.

En la siguiente ilustración se detalla protección adicional que puede aplicar para proteger el acceso a datos personales.

![Protección adicional para proteger el acceso a datos personales](Media/Apply-protection-to-personal-data-in-Office-365-image2.png)

Para la accesibilidad, la siguiente tabla contiene la misma información que la ilustración.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Ámbito de protección</strong></th>
<th align="left"><strong>Capacidades</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Protección de documentos y de correo electrónico (incluye el correo en tránsito, pero no los buzones en reposo actualmente)</td>
<td align="left"><p>Tipos de información confidencial</p>
<p>Etiquetas de Office</p>
<p>Directivas de prevención de pérdida de datos</p>
<p>Preguntas más frecuentes sobre el cifrado de mensajes para correo electrónico en Office 365</p></td>
</tr>
<tr class="even">
<td align="left">Protección de sitios y bibliotecas (incluye SharePoint Online y OneDrive para la Empresa)</td>
<td align="left"><p>Permisos para bibliotecas y sitios de SharePoint Online y OneDrive para la Empresa</p>
<p>Directivas de uso compartido externo para SharePoint Online y OneDrive para la Empresa (nivel de sitio)</p>
<p>Directivas de acceso a dispositivos de nivel de sitio</p></td>
</tr>
<tr class="odd">
<td align="left">Protección de acceso de servicio (incluye el acceso a todos los servicios de Office 365)</td>
<td align="left"><p>Protección de acceso a dispositivo e identidad en el conjunto de aplicaciones Enterprise Mobility + Security (EMS)</p>
<p>Privileged Access Management</p>
<p>Funciones de seguridad de Windows 10</p></td>
</tr>
</tbody>
</table>

En el resto de este artículo se proporciona más información sobre cada una de estas categorías de protección.

### <a name="capabilities-that-are-ok-to-use-with-gdpr"></a>Funcionalidades que puede usar con RGPD

Puede usar las siguientes funcionalidades en un entorno configurado para el cumplimiento del RGPD. Estas funcionalidades no son necesarias para el cumplimiento del RGPD, pero se pueden usar sin afectar negativamente a su capacidad para descubrir, proteger, supervisar e informar sobre los datos relacionados con el cumplimiento del RGPD.

Clave de cliente: permite a los clientes proporcionar y mantener el control sobre las claves de cifrado que se usan para cifrar los datos almacenados en Office 365. Se recomienda solo para los clientes con una necesidad normativa de administrar sus propias claves de cifrado.

Caja de seguridad del cliente: la Caja de seguridad del cliente le permite controlar cómo un ingeniero de soporte técnico de Microsoft accede a los datos, si es necesario, para solucionar un problema técnico de forma individual. Puede controlar si quiere permitir que el ingeniero de soporte técnico acceda a los datos o no. Se proporciona una fecha de expiración con cada solicitud.

## <a name="site-and-library-level-protection"></a>Protección de bibliotecas y sitios

### <a name="permissions-for-sharepoint-and-onedrive-for-business-libraries"></a>Permisos para bibliotecas de SharePoint y OneDrive para la Empresa

Use los permisos de SharePoint para proporcionar o restringir el acceso de usuarios al sitio o a su contenido. Agregue usuarios individuales o grupos de Azure Active Directory a los grupos de SharePoint predeterminados, o bien cree un grupo personalizado para obtener un control más preciso.

![Niveles de permisos de control total a solo vista](Media/Apply-protection-to-personal-data-in-Office-365-image3.png)

La ilustración indica los niveles de permisos de control total a solo vista. La siguiente tabla contiene la misma información.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Control total</strong></th>
<th align="left"><strong>Diseño</strong></th>
<th align="left"><strong>Editar</strong></th>
<th align="left"><strong>Colaborar</strong></th>
<th align="left"><strong>Lectura</strong></th>
<th align="left"><strong>Solo vista</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"></td>
<td align="left">Colaborar, aprobar y personalizar</td>
<td align="left">Colaborar, agregar, editar y eliminar listas (no solo elementos)</td>
<td align="left">Ver, agregar, actualizar y eliminar elementos de lista y documentos</td>
<td align="left">Ver y descargar</td>
<td align="left">Ver sin descargar</td>
</tr>
</tbody>
</table>

Más información:

-   [Información sobre los niveles de permisos en SharePoint](https://support.office.com/es-ES/article/Understanding-permission-levels-in-SharePoint-87ecbb0e-6550-491a-8826-c075e4859848)

-   [Información sobre los grupos de SharePoint](https://support.office.com/es-ES/article/Understanding-SharePoint-groups-94d9b261-161e-4ace-829e-eca1c8cd2eb8)

### <a name="external-sharing-policies-for-sharepoint-and-onedrive-for-business-libraries"></a>Directivas de uso compartido externo para las bibliotecas de SharePoint y OneDrive para la Empresa

Muchas organizaciones permiten el uso compartido para admitir la colaboración. Descubra cómo se configuran las opciones aplicables a todo el inquilino. Después, revise la configuración de uso compartido externo para los sitios que contienen datos personales.

Un usuario externo es alguien de fuera de la organización que está invitado para acceder a sus sitios y documentos de SharePoint Online pero no tiene una licencia para su suscripción a SharePoint Online o Microsoft Office 365.

Las directivas de uso compartido externo se aplican a SharePoint Online y OneDrive para la Empresa.

-   Debe ser administrador de SharePoint Online para configurar las directivas de uso compartido.

-   Debe ser propietario del sitio o tener permisos de control total para compartir un sitio o documentos con usuarios externos.

En la siguiente tabla se resumen los controles que puede configurar.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Categoría de control</strong></th>
<th align="left"><strong>Opciones</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Tipo de uso compartido</td>
<td align="left"><p>No permitir el uso compartido fuera de su organización (puede establecerse para colecciones de sitios individuales)</p>
<p>Permitir el uso compartido solo para usuarios externos autenticados (permitir nuevos o limitar existentes, puede establecerse para colecciones de sitios individuales)*</p>
<p>Permitir el uso compartido con usuarios externos con un vínculo de acceso anónimo (puede establecerse para colecciones de sitios individuales)</p>
<p>Limitar el uso compartido externo mediante dominios (lista de permitidos y denegados)</p>
<p>Elegir el tipo de vínculo predeterminado (anónimo, para compartir en la empresa o restringido)</p>
</td>
</tr>
<tr class="even">
<td align="left">Qué pueden hacer los usuarios externos</td>
<td align="left"><p>Evitar que los usuarios externos puedan compartir archivos, carpetas, o sitios de los que no son propietarios</p>
<p>Requerir que los usuarios externos acepten invitaciones de uso compartido con la misma cuenta a la que se envió la invitación</p></td>
</tr>
<tr class="odd">
<td align="left">Notificaciones</td>
<td align="left"><p>Actualmente, solo está disponible en OneDrive para la Empresa. Envíe una notificación a los propietarios cuando:</p>
- <p>Los usuarios invitan a otros usuarios externos a los archivos compartidos</p>
- <p>Los usuarios externos aceptan invitaciones de acceso a archivos</p>
- <p>Se crea o modifica un vínculo de acceso anónimo</p></td>
</tr>
</tbody>
</table>

Más información:

-   
  [Administrar el uso compartido externo en su entorno de SharePoint Online](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&rs=en-US&ad=US)

-   [Compartir documentos o sitios con personas fuera de su organización](https://support.office.com/es-ES/article/Share-sites-or-documents-with-people-outside-your-organization-80e49744-e30f-44db-8d51-16661b1d4232)

### <a name="site-level-device-access-policies"></a>Directivas de acceso a dispositivos de nivel de sitio

SharePoint Online y OneDrive para la Empresa le permiten configurar directivas de acceso de dispositivo a nivel de sitio. Esto le permite configurar más protección para sitios con datos confidenciales.

Si configura directivas de acceso de dispositivo de nivel de sitio, no olvide coordinarlas con directivas de nivel de inquilino y con las directivas de acceso que se configuran en Azure Active Directory, Intune e Intune App Management.

Las directivas de acceso de dispositivo para SharePoint y OneDrive para la empresa la compatibilidad con directivas en Azure Active Directory y Microsoft Intune según el escenario que va a implementar. En la siguiente tabla se resumen los objetivos que puede conseguir con las directivas de acceso de dispositivo y se indica qué productos requieren la compatibilidad con directivas.

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">Solo permitir el acceso desde ubicaciones de direcciones IP específicas</th>
<th align="left">Impedir que los usuarios descarguen archivos en dispositivos de dominios no combinados</th>
<th align="left">Bloquear el acceso en los dispositivos sin dominios combinados</th>
<th align="left">Impedir que los usuarios descarguen archivos en dispositivos no compatibles</th>
<th align="left">Bloquear el acceso de dispositivos no compatibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Centro de administración de SharePoint</td>
<td align="left">Sí</td>
<td align="left">Sí</td>
<td align="left">Sí</td>
<td align="left">Sí</td>
<td align="left">Sí</td>
</tr>
<tr class="even">
<td align="left">Azure Active Directory</td>
<td align="left"></td>
<td align="left">Sí</td>
<td align="left">Sí</td>
<td align="left">Sí</td>
<td align="left">Sí</td>
</tr>
<tr class="odd">
<td align="left">Microsoft Intune</td>
<td align="left"></td>
<td align="left"></td>
<td align="left"></td>
<td align="left">Sí</td>
<td align="left">Sí</td>
</tr>
</tbody>
</table>

Más información: [Centro de administración de SharePoint Online: Controlar el acceso desde dispositivos no administrados](https://support.office.com/en-us/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&rs=en-US&ad=US).

## <a name="service-access-protection-for-identities-and-devices"></a>Protección de acceso a servicios de identidades y dispositivos

Microsoft le recomienda que configure la protección de identidades y dispositivos que acceden al servicio. El esfuerzo de proteger el acceso a servicios de Office 365 también puede usarse para proteger el acceso a otros servicios SaaS, servicios PaaS e incluso aplicaciones de otros proveedores de nube.

La protección de acceso para identidades y dispositivos proporciona una línea base de protección para asegurarse de que las identidades no están en peligro, los dispositivos son seguros y los datos de la organización a los que se acceden desde dispositivos están aislados y protegidos.

Para ver recomendaciones para comenzar e instrucciones de configuración, consulte [Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles](https://docs.microsoft.com/es-ES/microsoft-365-enterprise/microsoft-security-guidance).

Para entornos de identidad híbridos con AD FS, consulte [Opciones y directivas de seguridad recomendadas](https://docs.microsoft.com/es-ES/microsoft-365-enterprise/microsoft-security-guidance).

En la siguiente ilustración se describe cómo se relacionan los servicios en la nube (SaaS, PaaS), los tipos de cuenta (cuentas de dominio de inquilino y cuentas B2B) y las funciones de acceso de servicio. Es importante que tenga en cuenta qué funciones pueden usarse con cuentas B2B.

![Servicios en la nube, tipos de cuenta y las funciones de acceso](Media/Apply-protection-to-personal-data-in-Office-365-image4.png)

Para la accesibilidad, el resto de esta sección describe esta ilustración.

### <a name="cloud-services"></a>Servicios en la nube

Azure Active Directory proporciona acceso de identidad a cualquier servicio de nube, incluidos los proveedores que no son de Microsoft como Amazon Web Services. La ilustración muestra Office 365, "Otras aplicaciones SaaS" y "Aplicación PaaS". Las flechas apuntan de Azure Active Directory a cada uno de estos servicios, lo que muestra que puede usarse Azure Active Directory para la autenticación de todos estos tipos de aplicaciones.

### <a name="types-of-accounts"></a>Tipos de cuentas

Las cuentas de dominio de inquilino son cuentas que agrega a su inquilino y administra directamente. Las cuentas B2B son cuentas de usuarios fuera de la organización a los que invita a colaborar. Pueden ser otras cuentas de Office 365, otras cuentas de la organización o cuentas de consumidor (como Gmail). En la ilustración se muestran dos tipos de cuenta en Azure Active Directory.

### <a name="capabilities"></a>Capacidades

Las capacidades de la siguiente tabla protegen las identidades y dispositivos. La tabla indica qué funcionalidades pueden usarse también con cuentas B2B, como en la ilustración.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Función</strong></th>
<th align="left"><strong>Funciona con cuentas de dominio de inquilino</strong></th>
<th align="left"><strong>Funciona con cuentas B2B de Azure (sin licencia adicional)</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Autenticación multifactor y acceso condicional</td>
<td align="left">Sí</td>
<td align="left">Sí</td>
</tr>
<tr class="even">
<td align="left">Azure AD Identity Protection</td>
<td align="left">Sí</td>
<td align="left">Sí</td>
</tr>
<tr class="odd">
<td align="left">Azure AD Privileged Identity Management</td>
<td align="left">Sí</td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left">Administración de aplicaciones (MAM)</td>
<td align="left">Sí</td>
<td align="left"></td>
</tr>
<tr class="odd">
<td align="left">Inscripción y administración de dispositivos</td>
<td align="left">Sí</td>
<td align="left">Solo una organización puede administrar un dispositivo</td>
</tr>
<tr class="even">
<td align="left">Funciones de seguridad de Windows 10 (el acceso condicional basado en el cumplimiento de dispositivo requiere la administración de dispositivos)</td>
<td align="left">Sí</td>
<td align="left">Sí</td>
</tr>
</tbody>
</table>

Puede agregar licencias a cuentas B2B para conceder a estos usuarios funciones adicionales, si es necesario, para proteger el acceso a datos personales en su entorno.

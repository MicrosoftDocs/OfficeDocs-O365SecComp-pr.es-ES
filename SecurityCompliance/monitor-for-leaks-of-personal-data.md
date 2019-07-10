---
title: Supervisar pérdidas de datos personales
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Obtenga información sobre las tres herramientas que puede usar para supervisar pérdidas de datos personales.
ms.openlocfilehash: d8e3854ad5d08517aae0bf0790561758478e87a2
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35597956"
---
# <a name="monitor-for-leaks-of-personal-data"></a>Supervisar pérdidas de datos personales

Existen muchas herramientas que pueden usarse para supervisar el uso y transporte de datos personales. En este tema se describen tres herramientas que funcionan bien.

![Herramientas para supervisar el uso y transporte de datos personales](Media/Monitor-for-leaks-of-personal-data-image1.png)

En la ilustración:

-   Comience con los informes de prevención de pérdida de datos de Office 365 para supervisar datos personales en SharePoint Online, OneDrive para la Empresa y correo electrónico en tránsito. Proporcionan mayor nivel de detalle de supervisión de datos personales. No obstante, estos informes no incluyen todos los servicios de Office 365.

-   Después, use directivas de alerta y el registro de Office 365 para supervisar la actividad de los servicios de Office 365. Configure la supervisión continua o busque el registro de auditoría para investigar un incidente. El registro de auditoría de Office 365 funciona en todos los servicios de Office 365: Sway, Power BI, eDiscovery, Dynamics 365, Microsoft Flow, Microsoft Teams, actividad administrativa, OneDrive para la Empresa, SharePoint Online, correo en tránsito y buzones de correo en reposo. Las conversaciones de Skype se incluyen en los buzones en reposo.

-   Por último, use Microsoft Cloud App Security para supervisar los archivos con datos confidenciales de otros proveedores de SaaS. Próximamente se podrán usar los tipos de información confidencial de Office 365 y las etiquetas unificadas en Azure Information Protection y Office con Cloud App Security. Puede configurar directivas que se aplican a todas las aplicaciones específicas (como cuadro) o a aplicaciones SaaS. Cloud App Security no busca archivos en Exchange Online, incluidos los archivos adjuntos de correo electrónico.

## <a name="office-365-data-loss-prevention-reports"></a>Informes de prevención de pérdida de datos de Office 365

Después de crear las directivas de prevención de pérdida de datos (DLP), deberá comprobar que su funcionamiento es el deseado y que le ayudan a cumplir las normativas. Con los informes DLP en Office 365, puede ver rápidamente el número de coincidencias de directivas DLP, reemplazos o falsos positivos; comprobar si la tendencia es ascendente o descendente a lo largo del tiempo; filtrar el informe de maneras diferentes; y ver detalles adicionales seleccionando un punto en una línea del gráfico.

Puede usar los informes DLP para lo siguiente:

-   Centrarse en períodos de tiempo específicos y comprender las causas de los picos y las tendencias.

-   Descubrir los procesos de negocio que infringen las directivas DLP de su organización.

-   Comprender cualquier impacto de negocio de las directivas DLP.

-   Ver las justificaciones enviadas por los usuarios cuando resuelven una sugerencia de directiva reemplazando la directiva o informando de un falso positivo.

-   Comprobar el cumplimiento de una directiva DLP específica mostrando las coincidencias de dicha directiva.

-   Ver una lista de los archivos con datos confidenciales que coincida con las directivas DLP en el panel de detalles.

Además, puede usar los informes DLP para ajustar las directivas DLP a medida que las ejecuta en modo de prueba.

Los informes DLP están en el centro de seguridad y el centro de cumplimiento. Vaya a Informes \> Ver informes. En Prevención de pérdida de datos (DLP), elija Coincidencias de regla y directiva DLP o Falsos positivos y reemplazos de DLP.

Para obtener más información, consulte [Ver los informes de prevención de pérdida de datos](https://support.office.com/es-ES/article/View-the-reports-for-data-loss-prevention-41eb4324-c513-4fa5-91c8-8fbd8aaba83b).

![Informe que muestra coincidencias de directivas DLP](Media/Monitor-for-leaks-of-personal-data-image2.png)

## <a name="office-365-audit-log-and-alert-policies"></a>Directivas de alerta y registro de auditoría de Office 365

El registro de auditoría de Office 365 contiene eventos de Exchange Online, SharePoint Online, OneDrive para la Empresa, Azure Active Directory, Microsoft Teams, Power BI, Sway y otros servicios de Office 365.

El centro de seguridad y el centro de cumplimiento ofrecen dos formas de supervisar e informar en el registro de auditoría de Office 365:

-   Configurar directivas de alerta, ver alertas y supervisar tendencias: use la directiva de alerta y el panel de herramientas de alerta en el centro de seguridad o el centro de cumplimiento.

-   Buscar el registro de auditoría directamente: busque todos los eventos en un intervalo de fechas especificado, o puede filtrar los resultados basándose en criterios específicos, como la acción, el usuario que la realizó o el objeto de destino.

Los equipos de seguridad y cumplimiento de información pueden usar estas herramientas para revisar proactivamente las actividades realizadas por los usuarios finales y los administradores en los servicios de Office 365. Pueden configurarse alertas automáticas para enviar notificaciones por correo electrónico cuando se producen ciertas actividades en colecciones de sitios específicos, por ejemplo, cuando se comparte el contenido de los sitios que se sabe que contiene información relacionada con RGPD. Esto permite que los equipos contacten con usuarios para asegurarse de que se siguen directivas de seguridad corporativa, así como proporcionar aprendizaje adicional.

Los equipos de seguridad de información también pueden buscar en el registro de auditoría para investigar las posibles infracciones de datos y determinar la causa raíz y la extensión de la infracción. Esta función integrada facilita el cumplimiento de los artículos 33 y 34 del RGPD, que requieren que se proporcionen notificaciones a la autoridad de control del RGPD y a los propietarios de los datos sujetos a una infracción en un período de tiempo determinado. Las entradas del registro de auditoría solo se conservan durante 90 días en el servicio, por lo que a menudo se recomienda, y muchas organizaciones lo requieren, que estos registros se conserven durante largos períodos de tiempo.

Existen soluciones que se adhieren a los Registros de auditoría unificados mediante la API de Actividad de administración de Microsoft y pueden almacenar entradas de registro según sea necesario, y proporcionar paneles avanzados y alertas. Un ejemplo es el [Microsoft Operations Management Suite  (OMS)](https://docs.microsoft.com/es-ES/azure/operations-management-suite/oms-solution-office-365).

Más información sobre las directivas de alerta y buscar en el registro de auditoría:

-   
  [Directivas de alerta en los centros de seguridad y cumplimiento de Microsoft 365](https://support.office.com/es-ES/article/Alert-policies-in-the-Office-365-Security-Compliance-Center-8927B8B9-C5BC-45A8-A9F9-96C732E58264)

-   
  [Buscar en el registro de auditoría de actividad de usuario y administración de Office 365](https://support.office.com/es-ES/article/Search-the-audit-log-for-user-and-admin-activity-in-Office-365-57CA5138-0AE0-4D34-BD40-240441EF2FB6) (introducción)

-   
  [Activar o desactivar la búsqueda de registros de auditoría de Office 365](https://support.office.com/es-ES/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)

-   
  [Buscar en el registro de auditoría](https://support.office.com/es-ES/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US)

-   [Search-UnifiedAuditLog](https://technet.microsoft.com/en-us/library/mt238501(v=exchg.160).aspx) (cmdlet) 

-   
  [Propiedades detalladas del registro de auditoría de Office 365](https://support.office.com/es-ES/article/Detailed-properties-in-the-Office-365-audit-log-ce004100-9e7f-443e-942b-9b04098fcfc3)

## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security

Microsoft Cloud App Security le ayuda a descubrir otras aplicaciones SaaS en uso en las redes y los datos confidenciales que se envían a y desde estas aplicaciones.

Microsoft Cloud App Security es un servicio completo que proporciona mayor visibilidad, controles pormenorizados y protección contra amenazas mejorada para las aplicaciones de la nube. Identifica más de 15.000 aplicaciones de nube en la red de todos los dispositivos y le proporciona puntuación de riesgo y análisis y evaluación de riesgos continua. No se requieren agentes: la información se recopila de los firewalls y servidores proxy para proporcionarle visibilidad completa y un contexto de uso de la nube y shadow IT.

Para entender mejor su entorno de nube, la característica de investigación Cloud App Security proporciona visibilidad detallada de todas las actividades, archivos y cuentas para las aplicaciones administradas y autorizadas. Puede obtener información detallada sobre el nivel de un archivo y descubrir a dónde se transfieren los datos en las aplicaciones de la nube.

Para obtener ejemplos, la siguiente ilustración muestra dos directivas Cloud App Security que pueden ayudarle con el RGPD.

![Directivas de Cloud App Security de ejemplo](Media/Monitor-for-leaks-of-personal-data-image3.png)

Las primera directiva envía una alerta cuando se comparten archivos con un atributo DCP predefinido o una expresión personalizada que elija fuera de la organización desde las aplicaciones SaaS que elija.

La segunda directiva bloquea las descargas de archivos en cualquier dispositivo no administrado. Usted elige los atributos de los archivos que se buscarán y las aplicaciones SaaS a las que desee que se aplique la directiva.

Estos tipos de atributo estarán pronto disponibles en Cloud App Security:

-   Tipos de información confidencial de Office 365

-   Etiquetas unificadas en Office 365 y Azure Information Protection

### <a name="cloud-app-security-dashboard"></a>Panel de Cloud App Security

Si aún no empezó a usar Cloud App Security, inícielo. Para obtener acceso a Cloud App Security: <https://portal.cloudappsecurity.com>.

Nota: No olvide habilitar "Analizar automáticamente archivos de etiquetas de clasificación de Azure Information Protection" (en la configuración General) al comenzar a usar Cloud App Security o antes de asignar etiquetas. Tras la configuración, Cloud App Security no vuelve a examinar los archivos existentes hasta que se modifican.

![Panel en el que se muestra información de alertas](Media/Monitor-for-leaks-of-personal-data-image4.png)

Más información:

-   
  [Implementar Cloud App Security](https://docs.microsoft.com/es-ES/cloud-app-security/getting-started-with-cloud-app-security)

-   [Más información sobre Microsoft Cloud App Security](https://www.microsoft.com/en-us/cloud-platform/cloud-app-security)

-   
  [Bloqueo de descargas de información confidencial con el proxy de Microsoft Cloud App Security](https://docs.microsoft.com/es-ES/cloud-app-security/use-case-proxy-block-session-aad)

## <a name="example-file-and-activity-policies-to-detect-sharing-of-personal-data"></a>Directivas de archivo y actividad de ejemplo para detectar el uso compartido de datos personales

### <a name="detect-sharing-of-files-containing-pii--credit-card-number"></a>Detectar el uso compartido de archivos que contengan DCP: número de tarjeta de crédito

Envíe una alerta cuando se comparte un archivo que contiene un número de tarjeta de crédito desde una aplicación de nube autorizada.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Control</strong></th>
<th align="left"><strong>Configuración</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Tipo de directiva</td>
<td align="left">Directiva de archivo</td>
</tr>
<tr class="even">
<td align="left">Plantilla de directiva</td>
<td align="left">Sin plantilla</td>
</tr>
<tr class="odd">
<td align="left">Gravedad de directiva</td>
<td align="left">Alta</td>
</tr>
<tr class="even">
<td align="left">Categoría</td>
<td align="left">DLP</td>
</tr>
<tr class="odd">
<td align="left">Configuración del filtro</td>
<td align="left"><p>Nivel de acceso = público (Internet), público, externo</p>
<p>Aplicación = &lt;seleccione aplicaciones&gt; (use esta opción si desea limitar la supervisión a aplicaciones SaaS específicas)</p></td>
</tr>
<tr class="even">
<td align="left">Aplicar a</td>
<td align="left">Todos los archivos, todos los propietarios</td>
</tr>
<tr class="odd">
<td align="left">Control de contenido</td>
<td align="left"><p>Incluye los archivos que coinciden con una expresión actual: Todos los países: Finanzas: Número de tarjeta de crédito</p>
<p>No requerir contexto relevante: desactivado (esto coincidirá con palabras clave como regex)</p>
<p>Incluir archivos con al menos 1 coincidencia</p>
<p>Quitar máscara de los últimos 4 caracteres de la infracción: activada</p></td>
</tr>
<tr class="even">
<td align="left">Alertas</td>
<td align="left"><p>Crear una alerta para cada archivo coincidente: activada</p>
<p>Límite de alertas diario: 1000</p>
<p>Seleccionar una alerta como correo electrónico: activada</p>
<p>Para: infosec@contoso.com</p></td>
</tr>
<tr class="odd">
<td align="left">Gobierno</td>
<td align="left"><p>Microsoft OneDrive para la Empresa</p>
<p>Hacer privado: comprobar Quitar usuarios externos</p>
<p>Resto de opciones: desactivadas</p>
<p>Microsoft SharePoint Online</p>
<p>Hacer privado: comprobar Quitar usuarios externos</p>
<p>Resto de opciones: desactivadas</p></td>
</tr>
</tbody>
</table>

Directivas similares:

-   Detectar el uso compartido de archivos que contengan DCP: dirección de correo electrónico

-   Detectar el uso compartido de archivos que contengan DCP: número de pasaporte

### <a name="detect-customer-or-hr-data-in-box-or-onedrive-for-business"></a>Detectar Datos de recursos humanos o Datos de cliente en Box o OneDrive para la Empresa

Envía una alerta cuando se carga un archivo etiquetado como Datos de recursos humanos o Datos de cliente en OneDrive para la Empresa o Box.

Notas:

-   La supervisión de Box requiere un conector configurado con el SDK API Connector.

-   Esta directiva requiere funcionalidades que actualmente están en versión preliminar privada.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Control</strong></th>
<th align="left"><strong>Configuración</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Tipo de directiva</td>
<td align="left">Directiva de actividad</td>
</tr>
<tr class="even">
<td align="left">Plantilla de directiva</td>
<td align="left">Sin plantilla</td>
</tr>
<tr class="odd">
<td align="left">Gravedad de directiva</td>
<td align="left">Alta</td>
</tr>
<tr class="even">
<td align="left">Categoría</td>
<td align="left">Control de uso compartido</td>
</tr>
<tr class="odd">
<td align="left">Actúa en</td>
<td align="left">Actividad única</td>
</tr>
<tr class="even">
<td align="left">Configuración del filtro</td>
<td align="left"><p>Tipo de actividad = cargar archivo</p>
<p>Aplicación = Microsoft OneDrive para la Empresa y Box</p>
<p>Etiqueta de clasificación (actualmente en versión preliminar privada): Azure Information Protection = datos del cliente, recursos humanos (datos de salario, recursos humanos), datos de empleado</p></td>
</tr>
<tr class="odd">
<td align="left">Alertas</td>
<td align="left"><p>Crear una alerta: activada</p>
<p>Límite de alertas diario: 1000</p>
<p>Seleccionar una alerta como correo electrónico: activada</p>
<p>Para: infosec@contoso.com</p></td>
</tr>
<tr class="even">
<td align="left">Gobierno</td>
<td align="left"><p>Todas las aplicaciones</p>
<p>Poner el usuario en cuarentena: comprobar</p>
<p>Resto de opciones: desactivadas</p>
<p>Office 365</p>
<p>Poner el usuario en cuarentena: comprobar</p>
<p>Resto de opciones: desactivadas</p></td>
</tr>
</tbody>
</table>

Directivas similares:

-   Detectar descargas grandes de Datos de clientes o Datos de recursos humanos: envía una alerta cuando se detecta que un solo usuario está descargando un gran número de archivos que contienen datos de recursos humanos o de clientes en un breve período de tiempo.

-   Detectar el uso compartido de Datos de clientes y Datos de recursos humanos: envía una alerta cuando se comparten archivos con Datos de clientes o de recursos humanos.

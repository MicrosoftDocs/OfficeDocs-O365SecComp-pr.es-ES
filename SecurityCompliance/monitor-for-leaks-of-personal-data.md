---
title: Supervisar pérdidas de datos personales
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: Obtenga información sobre las tres herramientas que puede usar para supervisar pérdidas de datos personales.
ms.openlocfilehash: b2ff4e686c3131260327b1c935603693eaa7f816
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272415"
---
# <a name="monitor-for-leaks-of-personal-data"></a><span data-ttu-id="160d5-103">Supervisar pérdidas de datos personales</span><span class="sxs-lookup"><span data-stu-id="160d5-103">Monitor for leaks of personal data</span></span>

<span data-ttu-id="160d5-p101">Existen muchas herramientas que pueden usarse para supervisar el uso y transporte de datos personales. En este tema se describen tres herramientas que funcionan bien.</span><span class="sxs-lookup"><span data-stu-id="160d5-p101">There are many tools that can be used to monitor the use and transport of personal data. This topic describes three tools that work well.</span></span>

![Herramientas para supervisar el uso y transporte de datos personales](Media/Monitor-for-leaks-of-personal-data-image1.png)

<span data-ttu-id="160d5-107">En la ilustración:</span><span class="sxs-lookup"><span data-stu-id="160d5-107">In the illustration:</span></span>

-   <span data-ttu-id="160d5-p102">Comience con los informes de prevención de pérdida de datos de Office 365 para supervisar datos personales en SharePoint Online, OneDrive para la Empresa y correo electrónico en tránsito. Proporcionan mayor nivel de detalle de supervisión de datos personales. No obstante, estos informes no incluyen todos los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="160d5-p102">Start with Office 365 data loss prevention reports for monitoring personal data in SharePoint Online, OneDrive for Business, and email in transit. These provide the greatest level of detail for monitoring personal data. However, these reports don’t include all services in Office 365.</span></span>

-   <span data-ttu-id="160d5-p103">Después, use directivas de alerta y el registro de Office 365 para supervisar la actividad de los servicios de Office 365. Configure la supervisión continua o busque el registro de auditoría para investigar un incidente. El registro de auditoría de Office 365 funciona en todos los servicios de Office 365: Sway, Power BI, eDiscovery, Dynamics 365, Microsoft Flow, Microsoft Teams, actividad administrativa, OneDrive para la Empresa, SharePoint Online, correo en tránsito y buzones de correo en reposo. Las conversaciones de Skype se incluyen en los buzones en reposo.</span><span class="sxs-lookup"><span data-stu-id="160d5-p103">Next, use alert policies and the Office 365 audit log to monitor activity across Office 365 services. Setup ongoing monitoring or search the audit log to investigate an incident. The Office 365 audit log works across Office 365 services — Sway, PowerBI, eDiscovery, Dynamics 365, Microsoft Flow, Microsoft Teams, Admin activity, OneDrive for Business, SharePoint Online, mail in transit, and mailboxes at rest. Skype conversations are included in mailboxes at rest.</span></span>

-   <span data-ttu-id="160d5-p104">Por último, use Microsoft Cloud App Security para supervisar los archivos con datos confidenciales de otros proveedores de SaaS. Próximamente se podrán usar los tipos de información confidencial de Office 365 y las etiquetas unificadas en Azure Information Protection y Office con Cloud App Security. Puede configurar directivas que se aplican a todas las aplicaciones específicas (como cuadro) o a aplicaciones SaaS. Cloud App Security no busca archivos en Exchange Online, incluidos los archivos adjuntos de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="160d5-p104">Finally, Use Microsoft Cloud App Security to monitor files with sensitive data in other SaaS providers. Coming soon is the ability to use Office 365 sensitive information types and unified labels across Azure Information Protection and Office with Cloud App Security. You can setup policies that apply to all of your SaaS apps or specific apps (like Box). Cloud App Security doesn’t discover files in Exchange Online, including files attached to email.</span></span>

## <a name="office-365-data-loss-prevention-reports"></a><span data-ttu-id="160d5-119">Informes de prevención de pérdida de datos de Office 365</span><span class="sxs-lookup"><span data-stu-id="160d5-119">Office 365 data loss prevention reports</span></span>

<span data-ttu-id="160d5-p105">Después de crear las directivas de prevención de pérdida de datos (DLP), deberá comprobar que su funcionamiento es el deseado y que le ayudan a cumplir las normativas. Con los informes DLP en Office 365, puede ver rápidamente el número de coincidencias de directivas DLP, reemplazos o falsos positivos; comprobar si la tendencia es ascendente o descendente a lo largo del tiempo; filtrar el informe de maneras diferentes; y ver detalles adicionales seleccionando un punto en una línea del gráfico.</span><span class="sxs-lookup"><span data-stu-id="160d5-p105">After you create your data loss prevention (DLP) policies, you’ll want to verify that they’re working as you intended and helping you to stay compliant. With the DLP reports in Office 365, you can quickly view the number of DLP policy matches, overrides, or false positives; see whether they’re trending up or down over time; filter the report in different ways; and view additional details by selecting a point on a line on the graph.</span></span>

<span data-ttu-id="160d5-122">Puede usar los informes DLP para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="160d5-122">You can use the DLP reports to:</span></span>

-   <span data-ttu-id="160d5-123">Centrarse en períodos de tiempo específicos y comprender las causas de los picos y las tendencias.</span><span class="sxs-lookup"><span data-stu-id="160d5-123">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>

-   <span data-ttu-id="160d5-124">Descubrir los procesos de negocio que infringen las directivas DLP de su organización.</span><span class="sxs-lookup"><span data-stu-id="160d5-124">Discover business processes that violate your organization’s DLP policies.</span></span>

-   <span data-ttu-id="160d5-125">Comprender cualquier impacto de negocio de las directivas DLP.</span><span class="sxs-lookup"><span data-stu-id="160d5-125">Understand any business impact of the DLP policies.</span></span>

-   <span data-ttu-id="160d5-126">Ver las justificaciones enviadas por los usuarios cuando resuelven una sugerencia de directiva reemplazando la directiva o informando de un falso positivo.</span><span class="sxs-lookup"><span data-stu-id="160d5-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy or reporting a false positive.</span></span>

-   <span data-ttu-id="160d5-127">Comprobar el cumplimiento de una directiva DLP específica mostrando las coincidencias de dicha directiva.</span><span class="sxs-lookup"><span data-stu-id="160d5-127">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>

-   <span data-ttu-id="160d5-128">Ver una lista de los archivos con datos confidenciales que coincida con las directivas DLP en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="160d5-128">View a list of files with sensitive data that matches your DLP policies in the details pane.</span></span>

<span data-ttu-id="160d5-129">Además, puede usar los informes DLP para ajustar las directivas DLP a medida que las ejecuta en modo de prueba.</span><span class="sxs-lookup"><span data-stu-id="160d5-129">In addition, you can use the DLP reports to fine tune your DLP policies as you run them in test mode.</span></span>

<span data-ttu-id="160d5-p106">Los informes DLP están en el Centro de seguridad y Cumplimiento. Vaya a Informes \> Ver informes. En Prevención de pérdida de datos (DLP), vaya a Coincidencias de regla y directiva DLP o a Falsos positivos y reemplazos de DLP.</span><span class="sxs-lookup"><span data-stu-id="160d5-p106">DLP reports are in Security and Compliance center. Navigate to Reports \> View reports. Under Data loss prevention (DLP), go to either DLP policy and rule matches or DLP false positives and overrides.</span></span>

<span data-ttu-id="160d5-133">Para obtener más información, consulte [Ver los informes de prevención de pérdida de datos](https://support.office.com/es-ES/article/View-the-reports-for-data-loss-prevention-41eb4324-c513-4fa5-91c8-8fbd8aaba83b).</span><span class="sxs-lookup"><span data-stu-id="160d5-133">For more information, see [View the reports for data loss prevention](https://support.office.com/es-ES/article/View-the-reports-for-data-loss-prevention-41eb4324-c513-4fa5-91c8-8fbd8aaba83b).</span></span>

![Informe que muestra coincidencias de directivas DLP](Media/Monitor-for-leaks-of-personal-data-image2.png)

## <a name="office-365-audit-log-and-alert-policies"></a><span data-ttu-id="160d5-135">Directivas de alerta y registro de auditoría de Office 365</span><span class="sxs-lookup"><span data-stu-id="160d5-135">Office 365 audit log and alert policies</span></span>

<span data-ttu-id="160d5-136">El registro de auditoría de Office 365 contiene eventos de Exchange Online, SharePoint Online, OneDrive para la Empresa, Azure Active Directory, Microsoft Teams, Power BI, Sway y otros servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="160d5-136">The Office 365 audit log contains events from Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory, Microsoft Teams, Power BI, Sway, and other Office 365 services.</span></span>

<span data-ttu-id="160d5-137">El Centro de seguridad y cumplimiento de Office 365 ofrece dos formas de supervisar e informar en el registro de auditoría de Office 365:</span><span class="sxs-lookup"><span data-stu-id="160d5-137">The Office 365 Security and Compliance Center provides two ways to monitor and report against the Office 365 audit log:</span></span>

-   <span data-ttu-id="160d5-138">Configurar directivas de alerta ver alertas y supervisar tendencias: use la nueva directiva de alerta y el panel de herramientas de alerta en el Centro de seguridad y cumplimiento de Office 365.</span><span class="sxs-lookup"><span data-stu-id="160d5-138">Setup alert policies, view alerts, and monitor trends — Use the new alert policy and alert dashboard tools in the Office 365 Security & Compliance Center.</span></span>

-   <span data-ttu-id="160d5-p107">Buscar el registro de auditoría directamente: busque todos los eventos en un intervalo de fechas especificado, o puede filtrar los resultados basándose en criterios específicos, como la acción, el usuario que la realizó o el objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="160d5-p107">Search the audit log directly — Search for all events in a specified date rage. Or you can filter the results based on specific criteria, such as the user who performed the action, the action, or the target object.</span></span>

<span data-ttu-id="160d5-p108">Los equipos de seguridad y cumplimiento de información pueden usar estas herramientas para revisar proactivamente las actividades realizadas por los usuarios finales y los administradores en los servicios de Office 365. Pueden configurarse alertas automáticas para enviar notificaciones por correo electrónico cuando se producen ciertas actividades en colecciones de sitios específicos, por ejemplo, cuando se comparte el contenido de los sitios que se sabe que contiene información relacionada con RGPD. Esto permite que los equipos contacten con usuarios para asegurarse de que se siguen directivas de seguridad corporativa, así como proporcionar aprendizaje adicional.</span><span class="sxs-lookup"><span data-stu-id="160d5-p108">Information security and compliance teams can use these tools to proactively review activities performed by both end users and administrators across Office 365 services. Automatic alerts can be configured to send email notifications when certain activities occur on specific site collections - for example when content is shared from sites known to contain GDPR related information. This allows those teams to follow up with users to ensure that corporate security policies are followed, or to provide additional training.</span></span>

<span data-ttu-id="160d5-p109">Los equipos de seguridad de información también pueden buscar en el registro de auditoría para investigar las posibles infracciones de datos y determinar la causa raíz y la extensión de la infracción. Esta función integrada facilita el cumplimiento de los artículos 33 y 34 del RGPD, que requieren que se proporcionen notificaciones a la autoridad de control del RGPD y a los propietarios de los datos sujetos a una infracción en un período de tiempo determinado. Las entradas del registro de auditoría solo se conservan durante 90 días en el servicio, por lo que a menudo se recomienda, y muchas organizaciones lo requieren, que estos registros se conserven durante largos períodos de tiempo.</span><span class="sxs-lookup"><span data-stu-id="160d5-p109">Information security teams can also search the audit log to investigate suspected data breaches and determine both root cause and the extent of the breach. This built in capability facilitates compliance with article 33 and 34 of the GDPR, which require notifications be provided to the GDPR supervisory authority and to the data subjects themselves of a data breach within a specific time period. Audit log entries are only retained for 90 days within the service - it is often recommended and many organizations required that these logs be retained for longer periods of time.</span></span>

<span data-ttu-id="160d5-p110">Existen soluciones que se adhieren a los Registros de auditoría unificados mediante la API de Actividad de administración de Microsoft y pueden almacenar entradas de registro según sea necesario, y proporcionar paneles avanzados y alertas. Un ejemplo es el [Microsoft Operations Management Suite  (OMS)](https://docs.microsoft.com/es-ES/azure/operations-management-suite/oms-solution-office-365).</span><span class="sxs-lookup"><span data-stu-id="160d5-p110">Solutions are available which subscribe to the Unified Audit Logs through the Microsoft Management Activity API and can both store log entries as needed, and provide advanced dashboards and alerts. One example is [Microsoft Operations Management Suite (OMS)](https://docs.microsoft.com/es-ES/azure/operations-management-suite/oms-solution-office-365).</span></span>

<span data-ttu-id="160d5-149">Más información sobre las directivas de alerta y buscar en el registro de auditoría:</span><span class="sxs-lookup"><span data-stu-id="160d5-149">More information about alert policies and searching the audit log:</span></span>

-   [<span data-ttu-id="160d5-150">Directivas de alerta en el Centro de seguridad y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="160d5-150">Alert policies in the Office 365 Security & Compliance Center</span></span>](https://support.office.com/es-ES/article/Alert-policies-in-the-Office-365-Security-Compliance-Center-8927B8B9-C5BC-45A8-A9F9-96C732E58264)

-   <span data-ttu-id="160d5-151">[Buscar en el registro de auditoría de actividad de usuario y administración de Office 365](https://support.office.com/es-ES/article/Search-the-audit-log-for-user-and-admin-activity-in-Office-365-57CA5138-0AE0-4D34-BD40-240441EF2FB6) (introducción)</span><span class="sxs-lookup"><span data-stu-id="160d5-151">[Search the audit log for user and admin activity in Office 365](https://support.office.com/es-ES/article/Search-the-audit-log-for-user-and-admin-activity-in-Office-365-57CA5138-0AE0-4D34-BD40-240441EF2FB6) (introduction)</span></span>

-   [<span data-ttu-id="160d5-152">Activar o desactivar la búsqueda de registros de auditoría de Office 365</span><span class="sxs-lookup"><span data-stu-id="160d5-152">Turn Office 365 audit log search on or off</span></span>](https://support.office.com/es-ES/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)

-   <span data-ttu-id="160d5-153">
  [Buscar en el registro de auditoría del Centro de seguridad y cumplimiento de Office 365](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US)</span><span class="sxs-lookup"><span data-stu-id="160d5-153">[Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US)</span></span>

-   <span data-ttu-id="160d5-154">
  [Search-UnifiedAuditLog](https://technet.microsoft.com/en-us/library/mt238501(v=exchg.160).aspx) (cmdlet)</span><span class="sxs-lookup"><span data-stu-id="160d5-154">[Search-UnifiedAuditLog](https://technet.microsoft.com/en-us/library/mt238501(v=exchg.160).aspx) (cmdlet)</span></span> 

-   [<span data-ttu-id="160d5-155">Propiedades detalladas del registro de auditoría de Office 365</span><span class="sxs-lookup"><span data-stu-id="160d5-155">Detailed properties in the Office 365 audit log</span></span>](https://support.office.com/es-ES/article/Detailed-properties-in-the-Office-365-audit-log-ce004100-9e7f-443e-942b-9b04098fcfc3)

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="160d5-156">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="160d5-156">Microsoft Cloud App Security</span></span>

<span data-ttu-id="160d5-157">Microsoft Cloud App Security le ayuda a descubrir otras aplicaciones SaaS en uso en las redes y los datos confidenciales que se envían a y desde estas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="160d5-157">Microsoft Cloud App Security helps you discover other SaaS apps in use across your networks and sensitive data that is sent to and from these apps.</span></span>

<span data-ttu-id="160d5-p111">Microsoft Cloud App Security es un servicio completo que proporciona mayor visibilidad, controles pormenorizados y protección contra amenazas mejorada para las aplicaciones de la nube. Identifica más de 15.000 aplicaciones de nube en la red de todos los dispositivos y le proporciona puntuación de riesgo y análisis y evaluación de riesgos continua. No se requieren agentes: la información se recopila de los firewalls y servidores proxy para proporcionarle visibilidad completa y un contexto de uso de la nube y shadow IT.</span><span class="sxs-lookup"><span data-stu-id="160d5-p111">Microsoft Cloud App Security is a comprehensive service providing deep visibility, granular controls and enhanced threat protection for your cloud apps. It identifies more than 15,000 cloud applications in your network-from all devices-and provides risk scoring and ongoing risk assessment and analytics. No agents required: information is collected from your firewalls and proxies to give you complete visibility and context for cloud usage and shadow IT.</span></span>

<span data-ttu-id="160d5-p112">Para entender mejor su entorno de nube, la característica de investigación Cloud App Security proporciona visibilidad detallada de todas las actividades, archivos y cuentas para las aplicaciones administradas y autorizadas. Puede obtener información detallada sobre el nivel de un archivo y descubrir a dónde se transfieren los datos en las aplicaciones de la nube.</span><span class="sxs-lookup"><span data-stu-id="160d5-p112">To better understand your cloud environment, Cloud App Security investigate feature provides deep visibility into all activities, files and accounts for sanctioned and managed apps. You can gain detailed information on a file level and discover where data travels in the cloud apps.</span></span>

<span data-ttu-id="160d5-163">Para obtener ejemplos, la siguiente ilustración muestra dos directivas Cloud App Security que pueden ayudarle con el RGPD.</span><span class="sxs-lookup"><span data-stu-id="160d5-163">For examples, the following illustration demonstrates two Cloud App Security policies that can help with GDPR.</span></span>

![Directivas de Cloud App Security de ejemplo](Media/Monitor-for-leaks-of-personal-data-image3.png)

<span data-ttu-id="160d5-165">Las primera directiva envía una alerta cuando se comparten archivos con un atributo DCP predefinido o una expresión personalizada que elija fuera de la organización desde las aplicaciones SaaS que elija.</span><span class="sxs-lookup"><span data-stu-id="160d5-165">The first policy alerts when files with a predefined PII attribute or custom expression that you choose is shared outside the organization from the SaaS apps that you choose.</span></span>

<span data-ttu-id="160d5-p113">La segunda directiva bloquea las descargas de archivos en cualquier dispositivo no administrado. Usted elige los atributos de los archivos que se buscarán y las aplicaciones SaaS a las que desee que se aplique la directiva.</span><span class="sxs-lookup"><span data-stu-id="160d5-p113">The second policy blocks downloads of files to any unmanaged device. You choose the attributes within the files to look for and the SaaS apps you want the policy to apply to.</span></span>

<span data-ttu-id="160d5-168">Estos tipos de atributo estarán pronto disponibles en Cloud App Security:</span><span class="sxs-lookup"><span data-stu-id="160d5-168">These attribute types are coming soon to Cloud App Security:</span></span>

-   <span data-ttu-id="160d5-169">Tipos de información confidencial de Office 365</span><span class="sxs-lookup"><span data-stu-id="160d5-169">Office 365 sensitive information types</span></span>

-   <span data-ttu-id="160d5-170">Etiquetas unificadas en Office 365 y Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="160d5-170">Unified labels across Office 365 and Azure Information Protection</span></span>

### <a name="cloud-app-security-dashboard"></a><span data-ttu-id="160d5-171">Panel de Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="160d5-171">Cloud App Security dashboard</span></span>

<span data-ttu-id="160d5-p114">Si aún no empezó a usar Cloud App Security, inícielo. Para obtener acceso a Cloud App Security: <https://portal.cloudappsecurity.com>.</span><span class="sxs-lookup"><span data-stu-id="160d5-p114">If you haven’t yet started to use Cloud App Security, begin by starting it up. To access Cloud App Security: <https://portal.cloudappsecurity.com>.</span></span>

<span data-ttu-id="160d5-p115">Nota: No olvide habilitar "Analizar automáticamente archivos de etiquetas de clasificación de Azure Information Protection" (en la configuración General) al comenzar a usar Cloud App Security o antes de asignar etiquetas. Tras la configuración, Cloud App Security no vuelve a examinar los archivos existentes hasta que se modifican.</span><span class="sxs-lookup"><span data-stu-id="160d5-p115">Note: Be sure to enable ‘Automatically scan files for Azure Information Protection classification labels’ (in General settings) when getting started with Cloud App Security or before you assign labels. After setup, Cloud App Security does not scan existing files again until they are modified.</span></span>

![Panel en el que se muestra información de alertas](Media/Monitor-for-leaks-of-personal-data-image4.png)

<span data-ttu-id="160d5-177">Más información:</span><span class="sxs-lookup"><span data-stu-id="160d5-177">More information:</span></span>

-   [<span data-ttu-id="160d5-178">Implementar Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="160d5-178">Deploy Cloud App Security</span></span>](https://docs.microsoft.com/es-ES/cloud-app-security/getting-started-with-cloud-app-security)

-   [<span data-ttu-id="160d5-179">Más información sobre Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="160d5-179">More information about Microsoft Cloud App Security</span></span>](https://www.microsoft.com/es-ES/cloud-platform/cloud-app-security)

-   [<span data-ttu-id="160d5-180">Bloqueo de descargas de información confidencial con el proxy de Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="160d5-180">Block downloads of sensitive information using the Microsoft Cloud App Security proxy</span></span>](https://docs.microsoft.com/es-ES/cloud-app-security/use-case-proxy-block-session-aad)

## <a name="example-file-and-activity-policies-to-detect-sharing-of-personal-data"></a><span data-ttu-id="160d5-181">Directivas de archivo y actividad de ejemplo para detectar el uso compartido de datos personales</span><span class="sxs-lookup"><span data-stu-id="160d5-181">Example file and activity policies to detect sharing of personal data</span></span>

### <a name="detect-sharing-of-files-containing-pii--credit-card-number"></a><span data-ttu-id="160d5-182">Detectar el uso compartido de archivos que contengan DCP: número de tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="160d5-182">Detect sharing of files containing PII — Credit card number</span></span>

<span data-ttu-id="160d5-183">Envíe una alerta cuando se comparte un archivo que contiene un número de tarjeta de crédito desde una aplicación de nube autorizada.</span><span class="sxs-lookup"><span data-stu-id="160d5-183">Alert when a file containing a credit card number is shared from an approved cloud app.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="160d5-184"><strong>Control</strong></span><span class="sxs-lookup"><span data-stu-id="160d5-184"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="160d5-185"><strong>Configuración</strong></span><span class="sxs-lookup"><span data-stu-id="160d5-185"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="160d5-186">Tipo de directiva</span><span class="sxs-lookup"><span data-stu-id="160d5-186">Policy type</span></span></td>
<td align="left"><span data-ttu-id="160d5-187">Directiva de archivo</span><span class="sxs-lookup"><span data-stu-id="160d5-187">File policy</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="160d5-188">Plantilla de directiva</span><span class="sxs-lookup"><span data-stu-id="160d5-188">Policy template</span></span></td>
<td align="left"><span data-ttu-id="160d5-189">Sin plantilla</span><span class="sxs-lookup"><span data-stu-id="160d5-189">No template</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="160d5-190">Gravedad de directiva</span><span class="sxs-lookup"><span data-stu-id="160d5-190">Policy severity</span></span></td>
<td align="left"><span data-ttu-id="160d5-191">Alta</span><span class="sxs-lookup"><span data-stu-id="160d5-191">High</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="160d5-192">Categoría</span><span class="sxs-lookup"><span data-stu-id="160d5-192">Category</span></span></td>
<td align="left"><span data-ttu-id="160d5-193">DLP</span><span class="sxs-lookup"><span data-stu-id="160d5-193">DLP</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="160d5-194">Configuración del filtro</span><span class="sxs-lookup"><span data-stu-id="160d5-194">Filter settings</span></span></td>
<td align="left"><p><span data-ttu-id="160d5-195">Nivel de acceso = público (Internet), público, externo</span><span class="sxs-lookup"><span data-stu-id="160d5-195">Access level = Public (Internet), Public, External</span></span></p>
<p><span data-ttu-id="160d5-196">Aplicación = &lt;seleccione aplicaciones&gt; (use esta opción si desea limitar la supervisión a aplicaciones SaaS específicas)</span><span class="sxs-lookup"><span data-stu-id="160d5-196">App = &lt;select apps&gt; (use this setting if you want to limit monitoring to specific SaaS apps)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="160d5-197">Aplicar a</span><span class="sxs-lookup"><span data-stu-id="160d5-197">Apply to</span></span></td>
<td align="left"><span data-ttu-id="160d5-198">Todos los archivos, todos los propietarios</span><span class="sxs-lookup"><span data-stu-id="160d5-198">All files, all owners</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="160d5-199">Control de contenido</span><span class="sxs-lookup"><span data-stu-id="160d5-199">Content inspection</span></span></td>
<td align="left"><p><span data-ttu-id="160d5-200">Incluye los archivos que coinciden con una expresión actual: Todos los países: Finanzas: Número de tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="160d5-200">Includes files that match a present expression: All countries: Finance: Credit card number</span></span></p>
<p><span data-ttu-id="160d5-201">No requerir contexto relevante: desactivado (esto coincidirá con palabras clave como regex)</span><span class="sxs-lookup"><span data-stu-id="160d5-201">Don’t require relevant context: unchecked (this will match keywords as well as regex)</span></span></p>
<p><span data-ttu-id="160d5-202">Incluir archivos con al menos 1 coincidencia</span><span class="sxs-lookup"><span data-stu-id="160d5-202">Includes files with at least 1 match</span></span></p>
<p><span data-ttu-id="160d5-203">Quitar máscara de los últimos 4 caracteres de la infracción: activada</span><span class="sxs-lookup"><span data-stu-id="160d5-203">Unmask the last 4 characters of the violation: checked</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="160d5-204">Alertas</span><span class="sxs-lookup"><span data-stu-id="160d5-204">Alerts</span></span></td>
<td align="left"><p><span data-ttu-id="160d5-205">Crear una alerta para cada archivo coincidente: activada</span><span class="sxs-lookup"><span data-stu-id="160d5-205">Create an alert for each matching file: checked</span></span></p>
<p><span data-ttu-id="160d5-206">Límite de alertas diario: 1000</span><span class="sxs-lookup"><span data-stu-id="160d5-206">Daily alert limit: 1000</span></span></p>
<p><span data-ttu-id="160d5-207">Seleccionar una alerta como correo electrónico: activada</span><span class="sxs-lookup"><span data-stu-id="160d5-207">Select an alert as email: checked</span></span></p>
<p><span data-ttu-id="160d5-208">Para: infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="160d5-208">To: infosec@contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="160d5-209">Gobierno</span><span class="sxs-lookup"><span data-stu-id="160d5-209">Governance</span></span></td>
<td align="left"><p><span data-ttu-id="160d5-210">Microsoft OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="160d5-210">Microsoft OneDrive for Business</span></span></p>
<p><span data-ttu-id="160d5-211">Hacer privado: comprobar Quitar usuarios externos</span><span class="sxs-lookup"><span data-stu-id="160d5-211">Make private: check Remove External Users</span></span></p>
<p><span data-ttu-id="160d5-212">Resto de opciones: desactivadas</span><span class="sxs-lookup"><span data-stu-id="160d5-212">All other settings: unchecked</span></span></p>
<p><span data-ttu-id="160d5-213">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="160d5-213">Microsoft SharePoint Online</span></span></p>
<p><span data-ttu-id="160d5-214">Hacer privado: comprobar Quitar usuarios externos</span><span class="sxs-lookup"><span data-stu-id="160d5-214">Make private: check Remove External Users</span></span></p>
<p><span data-ttu-id="160d5-215">Resto de opciones: desactivadas</span><span class="sxs-lookup"><span data-stu-id="160d5-215">All other settings: unchecked</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="160d5-216">Directivas similares:</span><span class="sxs-lookup"><span data-stu-id="160d5-216">Similar policies:</span></span>

-   <span data-ttu-id="160d5-217">Detectar el uso compartido de archivos que contengan DCP: dirección de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="160d5-217">Detect sharing of Files containing PII - Email Address</span></span>

-   <span data-ttu-id="160d5-218">Detectar el uso compartido de archivos que contengan DCP: número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="160d5-218">Detect sharing of Files containing PII - Passport Number</span></span>

### <a name="detect-customer-or-hr-data-in-box-or-onedrive-for-business"></a><span data-ttu-id="160d5-219">Detectar Datos de recursos humanos o Datos de cliente en Box o OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="160d5-219">Detect Customer or HR Data in Box or OneDrive for Business</span></span>

<span data-ttu-id="160d5-220">Envía una alerta cuando se carga un archivo etiquetado como Datos de recursos humanos o Datos de cliente en OneDrive para la Empresa o Box.</span><span class="sxs-lookup"><span data-stu-id="160d5-220">Alert when a file labeled as Customer Data or HR Data is uploaded to OneDrive for Business or Box.</span></span>

<span data-ttu-id="160d5-221">Notas:</span><span class="sxs-lookup"><span data-stu-id="160d5-221">Notes:</span></span>

-   <span data-ttu-id="160d5-222">La supervisión de Box requiere un conector configurado con el SDK API Connector.</span><span class="sxs-lookup"><span data-stu-id="160d5-222">Box monitoring requires a connector be configured using the API Connector SDK.</span></span>

-   <span data-ttu-id="160d5-223">Esta directiva requiere funcionalidades que actualmente están en versión preliminar privada.</span><span class="sxs-lookup"><span data-stu-id="160d5-223">This policy requires capabilities that are currently in private preview.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="160d5-224"><strong>Control</strong></span><span class="sxs-lookup"><span data-stu-id="160d5-224"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="160d5-225"><strong>Configuración</strong></span><span class="sxs-lookup"><span data-stu-id="160d5-225"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="160d5-226">Tipo de directiva</span><span class="sxs-lookup"><span data-stu-id="160d5-226">Policy type</span></span></td>
<td align="left"><span data-ttu-id="160d5-227">Directiva de actividad</span><span class="sxs-lookup"><span data-stu-id="160d5-227">Activity policy</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="160d5-228">Plantilla de directiva</span><span class="sxs-lookup"><span data-stu-id="160d5-228">Policy template</span></span></td>
<td align="left"><span data-ttu-id="160d5-229">Sin plantilla</span><span class="sxs-lookup"><span data-stu-id="160d5-229">No template</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="160d5-230">Gravedad de directiva</span><span class="sxs-lookup"><span data-stu-id="160d5-230">Policy severity</span></span></td>
<td align="left"><span data-ttu-id="160d5-231">Alta</span><span class="sxs-lookup"><span data-stu-id="160d5-231">High</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="160d5-232">Categoría</span><span class="sxs-lookup"><span data-stu-id="160d5-232">Category</span></span></td>
<td align="left"><span data-ttu-id="160d5-233">Control de uso compartido</span><span class="sxs-lookup"><span data-stu-id="160d5-233">Sharing Control</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="160d5-234">Actúa en</span><span class="sxs-lookup"><span data-stu-id="160d5-234">Act on</span></span></td>
<td align="left"><span data-ttu-id="160d5-235">Actividad única</span><span class="sxs-lookup"><span data-stu-id="160d5-235">Single activity</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="160d5-236">Configuración del filtro</span><span class="sxs-lookup"><span data-stu-id="160d5-236">Filter settings</span></span></td>
<td align="left"><p><span data-ttu-id="160d5-237">Tipo de actividad = cargar archivo</span><span class="sxs-lookup"><span data-stu-id="160d5-237">Activity type = Upload File</span></span></p>
<p><span data-ttu-id="160d5-238">Aplicación = Microsoft OneDrive para la Empresa y Box</span><span class="sxs-lookup"><span data-stu-id="160d5-238">App = Microsoft OneDrive for Business and Box</span></span></p>
<p><span data-ttu-id="160d5-239">Etiqueta de clasificación (actualmente en versión preliminar privada): Azure Information Protection = datos del cliente, recursos humanos (datos de salario, recursos humanos), datos de empleado</span><span class="sxs-lookup"><span data-stu-id="160d5-239">Classification Label (currently in private preview): Azure Information Protection = Customer Data, Human Resources—Salary Data, Human Resources—Employee Data</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="160d5-240">Alertas</span><span class="sxs-lookup"><span data-stu-id="160d5-240">Alerts</span></span></td>
<td align="left"><p><span data-ttu-id="160d5-241">Crear una alerta: activada</span><span class="sxs-lookup"><span data-stu-id="160d5-241">Create an alert: checked</span></span></p>
<p><span data-ttu-id="160d5-242">Límite de alertas diario: 1000</span><span class="sxs-lookup"><span data-stu-id="160d5-242">Daily alert limit: 1000</span></span></p>
<p><span data-ttu-id="160d5-243">Seleccionar una alerta como correo electrónico: activada</span><span class="sxs-lookup"><span data-stu-id="160d5-243">Select an alert as email: checked</span></span></p>
<p><span data-ttu-id="160d5-244">Para: infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="160d5-244">To: infosec@contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="160d5-245">Gobierno</span><span class="sxs-lookup"><span data-stu-id="160d5-245">Governance</span></span></td>
<td align="left"><p><span data-ttu-id="160d5-246">Todas las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="160d5-246">All apps</span></span></p>
<p><span data-ttu-id="160d5-247">Poner el usuario en cuarentena: comprobar</span><span class="sxs-lookup"><span data-stu-id="160d5-247">Put user in quarantine: check</span></span></p>
<p><span data-ttu-id="160d5-248">Resto de opciones: desactivadas</span><span class="sxs-lookup"><span data-stu-id="160d5-248">All other settings: unchecked</span></span></p>
<p><span data-ttu-id="160d5-249">Office 365</span><span class="sxs-lookup"><span data-stu-id="160d5-249">Office 365</span></span></p>
<p><span data-ttu-id="160d5-250">Poner el usuario en cuarentena: comprobar</span><span class="sxs-lookup"><span data-stu-id="160d5-250">Put user in quarantine: check</span></span></p>
<p><span data-ttu-id="160d5-251">Resto de opciones: desactivadas</span><span class="sxs-lookup"><span data-stu-id="160d5-251">All other settings: unchecked</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="160d5-252">Directivas similares:</span><span class="sxs-lookup"><span data-stu-id="160d5-252">Similar policies:</span></span>

-   <span data-ttu-id="160d5-253">Detectar descargas grandes de Datos de clientes o Datos de recursos humanos: envía una alerta cuando se detecta que un solo usuario está descargando un gran número de archivos que contienen datos de recursos humanos o de clientes en un breve período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="160d5-253">Detect large downloads of Customer data or HR Data — Alert when a large number of files containing customer data or HR data have been detected being downloaded by a single user within a short period of time.</span></span>

-   <span data-ttu-id="160d5-254">Detectar el uso compartido de Datos de clientes y Datos de recursos humanos: envía una alerta cuando se comparten archivos con Datos de clientes o de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="160d5-254">Detect Sharing of Customer and HR Data — Alert when files containing Customer or HR Data are shared.</span></span>

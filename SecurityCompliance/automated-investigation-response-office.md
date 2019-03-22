---
title: Investigación y respuesta automatizadas (AIR) con Office 365 Threat Intelligence
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/21/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Obtenga información sobre las capacidades de investigación y respuesta automatizadas en Office 365 Advanced Threat Protection.
ms.openlocfilehash: c2d5acd0bf26dc28b30f26488adf47de2c834fb6
ms.sourcegitcommit: a56128c7be5d59e976851c27301031e19fa1997d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2019
ms.locfileid: "30736505"
---
# <a name="automated-investigation-and-response-air-with-office-365-threat-intelligence"></a><span data-ttu-id="add0d-103">Investigación y respuesta automatizadas (AIR) con Office 365 Threat Intelligence</span><span class="sxs-lookup"><span data-stu-id="add0d-103">Automated Investigation and Response (AIR) with Office 365 Threat Intelligence</span></span>

<span data-ttu-id="add0d-104">La investigación y respuesta automatizada (AIR) (próximamente en las [capacidades de investigación y respuesta de amenazas de Office 365](office-365-ti.md)) le permite ejecutar la investigación y la corrección automáticas para las amenazas bien conocidas que ya existen en el mercado.</span><span class="sxs-lookup"><span data-stu-id="add0d-104">Automated Investigation and Response (AIR) (coming soon to [Office 365 Threat investigation and response capabilities](office-365-ti.md)) enables you to run automated investigation and remediation to well-known threats that exist today.</span></span> <span data-ttu-id="add0d-105">Lea este artículo para obtener información general sobre AIR y cómo puede ayudar a su organización a mitigar las amenazas de forma más eficaz y eficiente.</span><span class="sxs-lookup"><span data-stu-id="add0d-105">Read this article to get an overview of AIR and how it can help your organization mitigate threats more effectively and efficiently.</span></span> <span data-ttu-id="add0d-106">Tolearn más información sobre cuándo estará disponible AIR, consulte el [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="add0d-106">Tolearn more about when AIR will be available, see the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

## <a name="alerts"></a><span data-ttu-id="add0d-107">Alertas</span><span class="sxs-lookup"><span data-stu-id="add0d-107">Alerts</span></span>

<span data-ttu-id="add0d-108">Las [alertas](alert-policies.md#viewing-alerts) representan desencadenadores de flujos de trabajo del equipo de operaciones de seguridad para respuesta ante incidentes.</span><span class="sxs-lookup"><span data-stu-id="add0d-108">[Alerts](alert-policies.md#viewing-alerts) represent triggers for Security Operations team workflows for incident response.</span></span> <span data-ttu-id="add0d-109">Establecer prioridades en el conjunto de alertas adecuadas para la investigación mientras se asegura de que no hay amenazas sin direcciones es un reto.</span><span class="sxs-lookup"><span data-stu-id="add0d-109">Prioritizing the right set of alerts for investigation while making sure no threats are unaddressed is challenging.</span></span> <span data-ttu-id="add0d-110">Cuando las investigaciones en las alertas se realizan manualmente, los equipos de operaciones de seguridad deben buscar y correlacionar las entidades (por ejemplo, el contenido, los dispositivos y los usuarios) en riesgo de amenazas.</span><span class="sxs-lookup"><span data-stu-id="add0d-110">When investigations into alerts are performed manually, Security Operations teams must hunt and correlate entities (e.g. content, devices and users) at risk from threats.</span></span> <span data-ttu-id="add0d-111">Estas tareas y flujos de trabajo son muy lentos y implican el uso de varias herramientas y sistemas.</span><span class="sxs-lookup"><span data-stu-id="add0d-111">Such tasks and workflows are very time consuming and involve multiple tools and systems.</span></span> <span data-ttu-id="add0d-112">Con AIR, la investigación y la respuesta se automatizan en alertas clave de seguridad y administración de amenazas que activan automáticamente las guías de respuesta de seguridad.</span><span class="sxs-lookup"><span data-stu-id="add0d-112">With AIR, investigation and response are automated into key security and threat management alerts that trigger your security response playbooks automatically.</span></span> 

<span data-ttu-id="add0d-113">para ver las alertas, en el centro de cumplimiento de & de seguridad de Office 365, elija **alertas** > **ver alertas**.</span><span class="sxs-lookup"><span data-stu-id="add0d-113">To view alerts, in the Office 365 Security & Compliance Center, choose **Alerts** > **View alerts**.</span></span>

![Alertas que vinculan a investigaciones](media/air-alerts-page-details.png) 

<span data-ttu-id="add0d-115">Seleccione una alerta para ver sus detalles y, desde allí, use el vínculo **Ver investigación** para ir a la [investigación](#investigation-graph)correspondiente.</span><span class="sxs-lookup"><span data-stu-id="add0d-115">Select an alert to view its details, and from there, use the **View investigation** link to go to the corresponding [investigation](#investigation-graph).</span></span>

## <a name="security-playbooks"></a><span data-ttu-id="add0d-116">Guías de seguridad</span><span class="sxs-lookup"><span data-stu-id="add0d-116">Security playbooks</span></span>

<span data-ttu-id="add0d-117">Las guías de seguridad son directivas de back-end que están en el corazón de la automatización de la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="add0d-117">Security playbooks are back-end policies that are at the heart of automation in Microsoft Threat Protection.</span></span> <span data-ttu-id="add0d-118">Las guías de seguridad que se proporcionan en AIR se basan en escenarios comunes de seguridad del mundo real.</span><span class="sxs-lookup"><span data-stu-id="add0d-118">The security playbooks provided in AIR are based on common real-world security scenarios.</span></span> <span data-ttu-id="add0d-119">Una guía de seguridad se inicia automáticamente cuando se desencadena una alerta dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="add0d-119">A security playbook is launched automatically when an alert is triggered within your organization.</span></span> <span data-ttu-id="add0d-120">Una vez que se activa la alerta, la guía asociada se ejecuta automáticamente.</span><span class="sxs-lookup"><span data-stu-id="add0d-120">Once the alert triggers, the associated playbook is run automatically.</span></span> <span data-ttu-id="add0d-121">La guía ejecuta una investigación en la que se examinan todos los metadatos asociados (incluidos los mensajes de correo electrónico, usuarios, asuntos, remitentes, etc.) y, según sus conclusiones, se recomienda un conjunto de acciones que el equipo de seguridad de su organización puede llevar a controlar y mitigar la amenaza.</span><span class="sxs-lookup"><span data-stu-id="add0d-121">The playbook runs an investigation, looking at all the associated metadata (including email messages, users, subjects, senders, etc.) and, based on its findings, recommends a set of actions that your organization's security team can take to control and mitigate the threat.</span></span> 

<span data-ttu-id="add0d-122">Las guías de seguridad que recibirá con AIR están diseñadas para enfrentarse a las amenazas más frecuentes a las que se enfrentan las organizaciones en la actualidad.</span><span class="sxs-lookup"><span data-stu-id="add0d-122">The security playbooks you'll get with AIR are designed to tackle the most frequent threats that organizations face today.</span></span> <span data-ttu-id="add0d-123">Se basan en la información de las operaciones de seguridad y los equipos de respuesta ante incidentes, incluidos los que ayudan a defender activos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="add0d-123">They're based on input from Security Operations and Incident Response teams, including those who help defend Microsoft assets.</span></span>

### <a name="security-playbooks-are-rolling-out-in-phases"></a><span data-ttu-id="add0d-124">Las guías de seguridad se implementan en fases</span><span class="sxs-lookup"><span data-stu-id="add0d-124">Security playbooks are rolling out in phases</span></span>

<span data-ttu-id="add0d-125">Como parte del aire, las guías de seguridad se implementan en fases</span><span class="sxs-lookup"><span data-stu-id="add0d-125">As part of AIR, security playbooks are rolling out in phases</span></span>

- <span data-ttu-id="add0d-126">**Fase 1 (abril de 2019)**: las guías incluyen recomendaciones que los administradores de seguridad revisan y aprueban.</span><span class="sxs-lookup"><span data-stu-id="add0d-126">**Phase 1 (April 2019)**: Playbooks include recommendations that security administrators review and approve.</span></span> 

- <span data-ttu-id="add0d-127">**Fase 2 (junio de 2019)**: los administradores de seguridad tendrán la opción de permitir que las guías de seguridad tomen medidas automáticamente, sin interacción administrativa.</span><span class="sxs-lookup"><span data-stu-id="add0d-127">**Phase 2 (June 2019)**: Security administrators will have the option to allow security playbooks to take action automatically, without administrative interaction.</span></span>

<span data-ttu-id="add0d-128">La fase 1 incluirá las guías siguientes:</span><span class="sxs-lookup"><span data-stu-id="add0d-128">Phase 1 will include the following playbooks:</span></span>
- <span data-ttu-id="add0d-129">Mensaje de phish notificado por el usuario</span><span class="sxs-lookup"><span data-stu-id="add0d-129">User-reported phish message</span></span>
- <span data-ttu-id="add0d-130">Dirección URL haga clic en cambio de veredicto y vínculos seguros ATP de bloqueo</span><span class="sxs-lookup"><span data-stu-id="add0d-130">URL click verdict change and ATP Safe Links block override</span></span>
- <span data-ttu-id="add0d-131">ZAP de malware</span><span class="sxs-lookup"><span data-stu-id="add0d-131">Malware ZAP</span></span>
- <span data-ttu-id="add0d-132">ZAP de phish</span><span class="sxs-lookup"><span data-stu-id="add0d-132">Phish ZAP</span></span>
- <span data-ttu-id="add0d-133">Investigaciones manuales (con el explorador)</span><span class="sxs-lookup"><span data-stu-id="add0d-133">Manual investigations (using Explorer)</span></span>

<span data-ttu-id="add0d-134">Hay varias guías más planeadas para la fase 2.</span><span class="sxs-lookup"><span data-stu-id="add0d-134">Several more playbooks are planned for Phase 2.</span></span>

### <a name="playbooks-include-investigation-and-recommendations"></a><span data-ttu-id="add0d-135">Las guías incluyen investigación y recomendaciones</span><span class="sxs-lookup"><span data-stu-id="add0d-135">Playbooks include investigation and recommendations</span></span>

<span data-ttu-id="add0d-136">Cada guía incluye:</span><span class="sxs-lookup"><span data-stu-id="add0d-136">Each playbook includes:</span></span> 
- <span data-ttu-id="add0d-137">una investigación raíz,</span><span class="sxs-lookup"><span data-stu-id="add0d-137">a root investigation,</span></span> 
- <span data-ttu-id="add0d-138">pasos para buscar otras posibles amenazas y</span><span class="sxs-lookup"><span data-stu-id="add0d-138">steps to hunt down other potential threats, and</span></span> 
- <span data-ttu-id="add0d-139">corrección de amenazas recomendada.</span><span class="sxs-lookup"><span data-stu-id="add0d-139">recommended threat remediation.</span></span>

<span data-ttu-id="add0d-140">Cada paso de alto nivel incluye varios pasos secundarios que se ejecutan para proporcionar una respuesta profunda, detallada y exhaustiva a las amenazas.</span><span class="sxs-lookup"><span data-stu-id="add0d-140">Each high-level step includes many sub-steps that are executed to provide a deep, detailed, and exhaustive response to threats.</span></span>

## <a name="example-user-reported-phish-message"></a><span data-ttu-id="add0d-141">Ejemplo: mensaje de phish notificado por el usuario</span><span class="sxs-lookup"><span data-stu-id="add0d-141">Example: User-reported phish message</span></span>

<span data-ttu-id="add0d-142">Cuando un usuario de la organización envía un mensaje de correo electrónico y lo notifica a Microsoft mediante el [complemento de mensajes de informe para Outlook o Outlook Web Access](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="add0d-142">When a user in your organization submits an email message and reports it to Microsoft by using the [Report Message add-in for Outlook or Outlook Web Access](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="add0d-143">Esto desencadena una alerta informativa basada en el sistema que inicia automáticamente la guía de la investigación.</span><span class="sxs-lookup"><span data-stu-id="add0d-143">This triggers a system-based informational alert that automatically launches the investigation playbook.</span></span>

<span data-ttu-id="add0d-144">Durante la fase de investigación raíz, se evalúan varios aspectos del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="add0d-144">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="add0d-145">Entre estos, incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="add0d-145">These include:</span></span>
- <span data-ttu-id="add0d-146">Una determinación del tipo de amenaza que podría ser;</span><span class="sxs-lookup"><span data-stu-id="add0d-146">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="add0d-147">Quién lo envió;</span><span class="sxs-lookup"><span data-stu-id="add0d-147">Who sent it;</span></span>
- <span data-ttu-id="add0d-148">Dónde se envió el correo electrónico desde (infraestructura de envío);</span><span class="sxs-lookup"><span data-stu-id="add0d-148">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="add0d-149">Si se han entregado o bloqueado otras instancias del correo electrónico;</span><span class="sxs-lookup"><span data-stu-id="add0d-149">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="add0d-150">Una evaluación de nuestros analistas;</span><span class="sxs-lookup"><span data-stu-id="add0d-150">An assessment from our analysts;</span></span>
- <span data-ttu-id="add0d-151">Si el correo electrónico está asociado con alguna de las campañas conocidas;</span><span class="sxs-lookup"><span data-stu-id="add0d-151">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="add0d-152">etc.</span><span class="sxs-lookup"><span data-stu-id="add0d-152">and more.</span></span>

<span data-ttu-id="add0d-153">Una vez completada la investigación raíz, la guía proporciona una lista de acciones recomendadas para llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="add0d-153">After the root investigation is complete, the playbook provides a list of recommended actions to take.</span></span>
  
<span data-ttu-id="add0d-154">A continuación, se ejecutan varios pasos de la caza:</span><span class="sxs-lookup"><span data-stu-id="add0d-154">Next, several hunting steps are executed:</span></span>

- <span data-ttu-id="add0d-155">Se buscan mensajes de correo electrónico similares en otros clústeres de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="add0d-155">Similar email messages in other email clusters are searched.</span></span>
- <span data-ttu-id="add0d-156">La señal se comparte con otras plataformas, como [ATP de Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="add0d-156">The signal is shared with other platforms, such as [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="add0d-157">Se determina si los usuarios han hecho clic en el mensaje de correo electrónico sospechoso.</span><span class="sxs-lookup"><span data-stu-id="add0d-157">A determination is made on whether any users have clicked through on the suspicious email message.</span></span>
- <span data-ttu-id="add0d-158">Se realiza una comprobación entre Office 365 [EOP](eop/exchange-online-protection-eop.md) y [ATP](office-365-atp.md) para ver si hay otros mensajes similares que hayan informado los usuarios.</span><span class="sxs-lookup"><span data-stu-id="add0d-158">A check is done across Office 365 [EOP](eop/exchange-online-protection-eop.md) and [ATP](office-365-atp.md) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="add0d-159">Se realiza una comprobación para ver si un usuario se ha puesto en peligro.</span><span class="sxs-lookup"><span data-stu-id="add0d-159">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="add0d-160">Esta comprobación aprovecha las señales en [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) y [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlacionando los eventos o alertas relacionados.</span><span class="sxs-lookup"><span data-stu-id="add0d-160">This check leverages signals across [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related events or alerts.</span></span> 

<span data-ttu-id="add0d-161">Durante la fase de caza, los riesgos y las amenazas se asignan a varios pasos de caza.</span><span class="sxs-lookup"><span data-stu-id="add0d-161">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span>  

<span data-ttu-id="add0d-162">La corrección es la fase final de la guía.</span><span class="sxs-lookup"><span data-stu-id="add0d-162">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="add0d-163">Durante esta fase, se realizan pasos de corrección, basados en las fases de investigación y de caza.</span><span class="sxs-lookup"><span data-stu-id="add0d-163">During this phase, remediation steps are taken, based on theinvestigation and hunting phases.</span></span>  

## <a name="getting-started"></a><span data-ttu-id="add0d-164">Introducción</span><span class="sxs-lookup"><span data-stu-id="add0d-164">Getting started</span></span>

<span data-ttu-id="add0d-165">Para acceder a sus investigaciones, como administrador global de Office 365 o administrador de seguridad, vaya al centro de seguridad de Office 365[https://protection.office.com](https://protection.office.com)_AMP_ Compliance Center () e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="add0d-165">To access your investigations, as an Office 365 global administrator or security administrator, Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span> <span data-ttu-id="add0d-166">A continuación, siga uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="add0d-166">Then, do one of the following:</span></span>

- <span data-ttu-id="add0d-167">En el panel de navegación de la izquierda, vaya a**investigaciones**de **Administración** > de amenazas.</span><span class="sxs-lookup"><span data-stu-id="add0d-167">In the left navigation, go to **Threat management** > **Investigations**.</span></span>

    <span data-ttu-id="add0d-168">o</span><span class="sxs-lookup"><span data-stu-id="add0d-168">or</span></span>

- <span data-ttu-id="add0d-169">Visite el panel de administración de amenazas (en el centro de seguridad & cumplimiento, vaya a **Threat Management** > **Dashboard**).</span><span class="sxs-lookup"><span data-stu-id="add0d-169">Visit the Threat management dashboard (In the Security & Compliance Center, go to **Threat management** > **Dashboard**).</span></span>

![Widgets de aire](media/air-widgets.png)

<span data-ttu-id="add0d-171">Los widgets de AIR aparecerán en la parte superior del [Panel de seguridad](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="add0d-171">Your AIR widgets will appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="add0d-172">Seleccione un widget para empezar.</span><span class="sxs-lookup"><span data-stu-id="add0d-172">Select a widget to get started.</span></span>

### <a name="automated-investigations"></a><span data-ttu-id="add0d-173">Investigaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="add0d-173">Automated investigations</span></span>

<span data-ttu-id="add0d-174">La página investigaciones automatizadas muestra las investigaciones de su organización y sus Estados actuales.</span><span class="sxs-lookup"><span data-stu-id="add0d-174">The automated investigations page shows your organization's investigations and their current states.</span></span>

![Página principal de investigación para AIR](media/air-maininvestigationpage.png) 
  
<span data-ttu-id="add0d-176">Puede:</span><span class="sxs-lookup"><span data-stu-id="add0d-176">You can:</span></span>
- <span data-ttu-id="add0d-177">Vaya directamente a una investigación (seleccione un **identificador de investigación**).</span><span class="sxs-lookup"><span data-stu-id="add0d-177">Navigate directly to an investigation (select an **Investigation ID**).</span></span>
- <span data-ttu-id="add0d-178">Aplicar filtros.</span><span class="sxs-lookup"><span data-stu-id="add0d-178">Apply filters.</span></span> <span data-ttu-id="add0d-179">Elija entre el **tipo de investigación**, **el intervalo de tiempo**, el **Estado**o una combinación de estos.</span><span class="sxs-lookup"><span data-stu-id="add0d-179">Choose from **Investigation Type**, **Time range**, **Status**, or a combination of these.</span></span>
- <span data-ttu-id="add0d-180">ExPorte los datos a un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="add0d-180">Export the data to a CSV file.</span></span>

### <a name="investigation-graph"></a><span data-ttu-id="add0d-181">Gráfico de investigación</span><span class="sxs-lookup"><span data-stu-id="add0d-181">Investigation graph</span></span>

<span data-ttu-id="add0d-182">Al abrir una investigación específica, verá la página gráfico de investigación.</span><span class="sxs-lookup"><span data-stu-id="add0d-182">When you open a specific investigation, you see the investigation graph page.</span></span> <span data-ttu-id="add0d-183">En esta página se muestran todas las entidades distintas: mensajes de correo electrónico, usuarios (y sus actividades) y dispositivos que se investigaron automáticamente como parte de la alerta que se activó.</span><span class="sxs-lookup"><span data-stu-id="add0d-183">This page shows all the different entities: email messages, users (and their activities), and devices that were automatically investigated as part of the alert that was triggered.</span></span>

![Página de gráfico de investigación de aire](media/air-investigationgraphpage.png)

<span data-ttu-id="add0d-185">Puede:</span><span class="sxs-lookup"><span data-stu-id="add0d-185">You can:</span></span>
- <span data-ttu-id="add0d-186">Obtenga información general visual de la investigación actual.</span><span class="sxs-lookup"><span data-stu-id="add0d-186">Get a visual overview of the current investigation.</span></span>
- <span data-ttu-id="add0d-187">Ver un resumen de los intervalos de investigación.</span><span class="sxs-lookup"><span data-stu-id="add0d-187">View a summary of the investigation timings.</span></span>
- <span data-ttu-id="add0d-188">Seleccione un nodo de la visualización para ver los detalles de ese nodo.</span><span class="sxs-lookup"><span data-stu-id="add0d-188">Select a node in the visualization to view details for that node.</span></span>
- <span data-ttu-id="add0d-189">Seleccione una pestaña en la parte superior para ver los detalles de esa pestaña.</span><span class="sxs-lookup"><span data-stu-id="add0d-189">Select a tab across the top to view details for that tab.</span></span>

### <a name="alert-investigation"></a><span data-ttu-id="add0d-190">Investigación de alertas</span><span class="sxs-lookup"><span data-stu-id="add0d-190">Alert investigation</span></span>

<span data-ttu-id="add0d-191">En la pestaña **alertas** de una investigación, puede ver todas las alertas relevantes para la investigación.</span><span class="sxs-lookup"><span data-stu-id="add0d-191">On the **Alerts** tab for an investigation, you can see all of the alerts relevant to the investigation.</span></span> <span data-ttu-id="add0d-192">Los detalles incluyen la alerta que desencadenó la investigación y otras alertas, como el inicio de sesión peligroso, la descarga masiva, etc., que están correlacionados con la investigación.</span><span class="sxs-lookup"><span data-stu-id="add0d-192">Details include the alert that triggered the investigation and other alerts, such as risky sign-in, mass download, etc., that are correlated to the investigation.</span></span> <span data-ttu-id="add0d-193">En esta página, un analista de seguridad también puede ver detalles adicionales de alertas individuales.</span><span class="sxs-lookup"><span data-stu-id="add0d-193">From this page, a security analyst can also view additional details on individual alerts.</span></span>

![Página de alertas de AIR](media/air-investigationalertspage.png)

<span data-ttu-id="add0d-195">Puede:</span><span class="sxs-lookup"><span data-stu-id="add0d-195">You can:</span></span>
- <span data-ttu-id="add0d-196">Obtenga información general visual de la alerta desencadenadora actual y de cualquier alerta asociada.</span><span class="sxs-lookup"><span data-stu-id="add0d-196">Get a visual overview of the current triggering alert and any associated alerts.</span></span>
- <span data-ttu-id="add0d-197">Seleccione una alerta de la lista para abrir una página emergente que muestre los detalles de la alerta completa.</span><span class="sxs-lookup"><span data-stu-id="add0d-197">Select an alert in the list to open a fly-out page that shows full alert details.</span></span>

### <a name="email-investigation"></a><span data-ttu-id="add0d-198">Investigación de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="add0d-198">Email investigation</span></span>

<span data-ttu-id="add0d-199">En la pestaña **correo electrónico** de una investigación, puede ver todos los clústeres de correo electrónico identificados como parte de la investigación.</span><span class="sxs-lookup"><span data-stu-id="add0d-199">On the **Email** tab for an investigation, you can see all the email clusters identified as part of the investigation.</span></span> 

<span data-ttu-id="add0d-200">Dado el volumen total de correo electrónico que los usuarios de una organización envían y reciben, el proceso de</span><span class="sxs-lookup"><span data-stu-id="add0d-200">Given the sheer volume of email that users in an organization send and receive, the process of</span></span> 
- <span data-ttu-id="add0d-201">agrupación de mensajes de correo electrónico en función de atributos similares de un encabezado, cuerpo, dirección URL y datos adjuntos del mensaje;</span><span class="sxs-lookup"><span data-stu-id="add0d-201">clustering email messages based on similar attributes from a message header, body, URL and attachment;</span></span> 
- <span data-ttu-id="add0d-202">separar el correo electrónico malintencionado del correo electrónico bueno; y</span><span class="sxs-lookup"><span data-stu-id="add0d-202">separating malicious email from the good email; and</span></span> 
- <span data-ttu-id="add0d-203">realizar acciones en mensajes de correo electrónico malintencionados</span><span class="sxs-lookup"><span data-stu-id="add0d-203">taking action on malicious email messages</span></span> 

<span data-ttu-id="add0d-204">puede tardar varias horas.</span><span class="sxs-lookup"><span data-stu-id="add0d-204">can take many hours.</span></span> <span data-ttu-id="add0d-205">AIR ahora automatiza este proceso, lo que ahorra tiempo y esfuerzo del equipo de seguridad de su organización.</span><span class="sxs-lookup"><span data-stu-id="add0d-205">AIR now automates this process, saving your organization's security team time and effort.</span></span> 

<span data-ttu-id="add0d-206">Como ejemplo, considere la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="add0d-206">As an example, consider the following image.</span></span> <span data-ttu-id="add0d-207">El primer clúster de tres mensajes de correo electrónico se consideró phish.</span><span class="sxs-lookup"><span data-stu-id="add0d-207">The first cluster of three email messages were deemed to be phish.</span></span> <span data-ttu-id="add0d-208">Se ha encontrado otro clúster de mensajes similares con la misma dirección IP y asunto, y se considera como malintencionado, ya que algunos de ellos se identificaron como phish durante la detección inicial.</span><span class="sxs-lookup"><span data-stu-id="add0d-208">Another cluster of similar messages with the same IP and subject was found and is considered to be malicious, as some of them were identified as phish during initial detection.</span></span> 

![Página de investigación de correo electrónico de AIR](media/air-investigationemailpage.png)

<span data-ttu-id="add0d-210">Puede:</span><span class="sxs-lookup"><span data-stu-id="add0d-210">You can:</span></span>
- <span data-ttu-id="add0d-211">Obtenga información general visual de los resultados y amenazas de clúster actuales encontrados.</span><span class="sxs-lookup"><span data-stu-id="add0d-211">Get a visual overview of the current clustering results and threats found.</span></span>
- <span data-ttu-id="add0d-212">Haga clic en una entidad de clúster o en una lista de amenazas para abrir una página emergente que muestre los detalles de alerta completos.</span><span class="sxs-lookup"><span data-stu-id="add0d-212">Click a cluster entity or a threat list to open a fly-out page that shows the full alert details.</span></span>

![Correo electrónico de investigación de aire con detalles de control flotante](media/air-investigationemailpageflyoutdetails.png)

### <a name="user-investigation"></a><span data-ttu-id="add0d-214">Investigación del usuario</span><span class="sxs-lookup"><span data-stu-id="add0d-214">User investigation</span></span>

<span data-ttu-id="add0d-215">En la pestaña **usuarios** , puede ver todos los usuarios identificados como parte de la investigación.</span><span class="sxs-lookup"><span data-stu-id="add0d-215">On the **Users** tab, you can see all the users identified as part of the investigation.</span></span> 

<span data-ttu-id="add0d-216">Por ejemplo, en la siguiente imagen, AIR ha identificado indicadores de peligro y anomalías en función de una nueva regla de bandeja de entrada creada.</span><span class="sxs-lookup"><span data-stu-id="add0d-216">For example, in the following image, AIR has identified indicators of compromise and anomalies based on a new inbox rule that was created.</span></span> <span data-ttu-id="add0d-217">Hay disponibles detalles adicionales (evidencia) de la investigación en las vistas detalladas de esta pestaña.</span><span class="sxs-lookup"><span data-stu-id="add0d-217">Additional details (evidence) of the investigation are available through detailed views within this tab.</span></span>

![Página de usuarios de investigación de aire](media/air-investigationuserspage.png)

<span data-ttu-id="add0d-219">Puede:</span><span class="sxs-lookup"><span data-stu-id="add0d-219">You can:</span></span>
- <span data-ttu-id="add0d-220">Obtenga una introducción visual de los resultados de usuario identificados y los riesgos encontrados.</span><span class="sxs-lookup"><span data-stu-id="add0d-220">Get a visual overview of identified user results and risks found.</span></span>
- <span data-ttu-id="add0d-221">Seleccione un usuario para abrir una página emergente que muestre todos los detalles de la alerta.</span><span class="sxs-lookup"><span data-stu-id="add0d-221">Select a user to open a fly-out page that shows the full alert details.</span></span>

### <a name="machine-investigation"></a><span data-ttu-id="add0d-222">Investigación de máquina</span><span class="sxs-lookup"><span data-stu-id="add0d-222">Machine investigation</span></span>

<span data-ttu-id="add0d-223">En la pestaña **máquinas** , puede ver todos los equipos identificados como parte de la investigación.</span><span class="sxs-lookup"><span data-stu-id="add0d-223">On the **Machines** tab, you can see all the machines identified as part of the investigation.</span></span> 

![Página de la máquina de investigación de aire](media/air-investigationmachinepage.png)

<span data-ttu-id="add0d-225">Como parte de la investigación, AIR correlaciona las amenazas de correo electrónico en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="add0d-225">As part of the investigation, AIR correlates email threats to devices.</span></span> <span data-ttu-id="add0d-226">Por ejemplo, una investigación pasa un hash de archivo en [ATP de Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) para investigar.</span><span class="sxs-lookup"><span data-stu-id="add0d-226">For example, an investigation passes a file hash across to [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) to investigate.</span></span> <span data-ttu-id="add0d-227">Esto permite la investigación automatizada de las máquinas relevantes para los usuarios y ayuda a garantizar que las amenazas se dirijan en la nube y en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="add0d-227">This allows for automated investigation of relevant machines for your users and helps to ensure that threats are addressed both in the cloud and across your devices.</span></span> 

<span data-ttu-id="add0d-228">Puede:</span><span class="sxs-lookup"><span data-stu-id="add0d-228">You can:</span></span>
- <span data-ttu-id="add0d-229">Obtenga información general visual de las amenazas y los equipos actuales encontrados.</span><span class="sxs-lookup"><span data-stu-id="add0d-229">Get a visual overview of the current machines and threats found.</span></span>
- <span data-ttu-id="add0d-230">Seleccione un equipo para abrir una vista en las investigaciones de [ATP de Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection)relacionadas.</span><span class="sxs-lookup"><span data-stu-id="add0d-230">Select a machine to open a view that into the related [Windows Defender ATP investigations](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection).</span></span>

### <a name="entity-investigation"></a><span data-ttu-id="add0d-231">Investigación de entidades</span><span class="sxs-lookup"><span data-stu-id="add0d-231">Entity investigation</span></span>

<span data-ttu-id="add0d-232">En la pestaña **entidades** , puede ver todos los equipos identificados como parte de la investigación.</span><span class="sxs-lookup"><span data-stu-id="add0d-232">On the **Entities** tab, you can see all the machines identified as part of the investigation.</span></span> 

<span data-ttu-id="add0d-233">Aquí puede ver las entidades investigadas.</span><span class="sxs-lookup"><span data-stu-id="add0d-233">Here, you can see the investigated entities.</span></span> <span data-ttu-id="add0d-234">Puede ver los detalles de los tipos de entidades, como los mensajes de correo electrónico, los clústeres, las direcciones IP, los usuarios, etc.</span><span class="sxs-lookup"><span data-stu-id="add0d-234">You can see details of the types of entities, such as email messages, clusters, IP addresses, users, and more.</span></span> <span data-ttu-id="add0d-235">También puede ver cuántas entidades se han analizado y las amenazas que se han asociado a cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="add0d-235">You can also see how many entities were analyzed, and the threats that were associated with each.</span></span> 

![Página de entidades de investigación de aire](media/air-investigationentitiespage.png)

<span data-ttu-id="add0d-237">Puede:</span><span class="sxs-lookup"><span data-stu-id="add0d-237">You can:</span></span>
- <span data-ttu-id="add0d-238">Obtenga información general visual de las entidades de investigación y las amenazas encontradas.</span><span class="sxs-lookup"><span data-stu-id="add0d-238">Get a visual overview of the investigation entities and threats found.</span></span>
- <span data-ttu-id="add0d-239">Seleccione una entidad para abrir una página emergente que muestre el detalle de la entidad relacionada.</span><span class="sxs-lookup"><span data-stu-id="add0d-239">Select an entity to open a fly-out page that shows the related entity detail.</span></span>

![Detalles de entidades de investigación de aire](media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a><span data-ttu-id="add0d-241">Registro de la guía</span><span class="sxs-lookup"><span data-stu-id="add0d-241">Playbook log</span></span>

<span data-ttu-id="add0d-242">En la pestaña **registro** , puede ver todos los pasos de la guía que se han producido durante la investigación.</span><span class="sxs-lookup"><span data-stu-id="add0d-242">On the **Log** tab, you can see all the playbook steps that have occurred during the investigation.</span></span> <span data-ttu-id="add0d-243">El registro captura un inventario completo de todas las acciones realizadas por las capacidades de inteligencia sobre amenazas de Office 365 como parte del aire.</span><span class="sxs-lookup"><span data-stu-id="add0d-243">The log captures a complete inventory of all actions completed by Office 365 Threat Intelligence capabilities as part of AIR.</span></span> <span data-ttu-id="add0d-244">Proporciona una vista clara de todos los pasos realizados, incluida la propia acción, una descripción y la duración del real desde el principio hasta el final.</span><span class="sxs-lookup"><span data-stu-id="add0d-244">It provides a clear view of all the steps taken, including the Action itself, a description and the duration of the actual from start to finish.</span></span> 

![Página de registro de investigación de aire](media/air-investigationlogpage.png)

<span data-ttu-id="add0d-246">Puede:</span><span class="sxs-lookup"><span data-stu-id="add0d-246">You can:</span></span>
- <span data-ttu-id="add0d-247">Vea una descripción general visual de los pasos de la guía realizados.</span><span class="sxs-lookup"><span data-stu-id="add0d-247">Get see a visual overview of the playbook steps taken.</span></span>
- <span data-ttu-id="add0d-248">ExPorte los resultados a un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="add0d-248">Export the results to a CSV file.</span></span>
- <span data-ttu-id="add0d-249">Filtrar la vista.</span><span class="sxs-lookup"><span data-stu-id="add0d-249">Filter the view.</span></span>

### <a name="recommended-actions"></a><span data-ttu-id="add0d-250">Acciones recomendadas</span><span class="sxs-lookup"><span data-stu-id="add0d-250">Recommended actions</span></span>

<span data-ttu-id="add0d-251">En la ficha **acciones** , puede ver todas las acciones de la guía que se recomiendan para la corrección después de que la investigación haya finalizado.</span><span class="sxs-lookup"><span data-stu-id="add0d-251">On the **Actions** tab, you can see all the playbook actions that are recommended for remediation after the investigation has completed.</span></span> 

<span data-ttu-id="add0d-252">Acciones Capture una lista completa de todos los pasos que Microsoft recomienda realizar al final de una investigación.</span><span class="sxs-lookup"><span data-stu-id="add0d-252">Actions capture a complete list of all the steps Microsoft recommends you take at the end of a investigation.</span></span> <span data-ttu-id="add0d-253">Puede realizar acciones de corrección aquí si selecciona una o varias acciones.</span><span class="sxs-lookup"><span data-stu-id="add0d-253">You can take remediation actions here by selecting one or more actions.</span></span> <span data-ttu-id="add0d-254">Al hacer clic en **aprobar** se permitirá que se inicie la corrección.</span><span class="sxs-lookup"><span data-stu-id="add0d-254">Clicking **Approve** will allow remediation to begin.</span></span> <span data-ttu-id="add0d-255">(Puede que sea necesario disponer de los permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="add0d-255">(Appropriate permissions might be required.</span></span> <span data-ttu-id="add0d-256">Por ejemplo, un lector de seguridad puede ver las acciones pero no aprobarlas.)</span><span class="sxs-lookup"><span data-stu-id="add0d-256">For example, a Security Reader can view actions but not approve them.)</span></span>  

![Página de acción de investigaciones de aire](media/air-investigationactionspage.png)

<span data-ttu-id="add0d-258">Puede:</span><span class="sxs-lookup"><span data-stu-id="add0d-258">You can:</span></span>
- <span data-ttu-id="add0d-259">Obtenga información general visual de las acciones recomendadas de la guía.</span><span class="sxs-lookup"><span data-stu-id="add0d-259">Get a visual overview of the playbook-recommended actions.</span></span>
- <span data-ttu-id="add0d-260">Seleccione una sola acción o varias acciones.</span><span class="sxs-lookup"><span data-stu-id="add0d-260">Select a single action or multiple actions.</span></span>
- <span data-ttu-id="add0d-261">Aprobar acciones recomendadas.</span><span class="sxs-lookup"><span data-stu-id="add0d-261">Approve recommended actions.</span></span> <span data-ttu-id="add0d-262">(Estos se inician inmediatamente con comentarios).</span><span class="sxs-lookup"><span data-stu-id="add0d-262">(These are started immediately with comments.)</span></span>
- <span data-ttu-id="add0d-263">ExPorte los resultados a un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="add0d-263">Export the results to a CSV file.</span></span>
- <span data-ttu-id="add0d-264">Filtrar la vista.</span><span class="sxs-lookup"><span data-stu-id="add0d-264">Filter the view.</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="add0d-265">Cómo obtener aire</span><span class="sxs-lookup"><span data-stu-id="add0d-265">How to get AIR</span></span>

<span data-ttu-id="add0d-266">Actualmente, AIR está en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="add0d-266">Currently, AIR is in preview.</span></span> <span data-ttu-id="add0d-267">Una vez lanzado el aire, se incluirá en las siguientes suscripciones:</span><span class="sxs-lookup"><span data-stu-id="add0d-267">When released, AIR will be included in the following subscriptions:</span></span>

- <span data-ttu-id="add0d-268">Microsoft 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="add0d-268">Microsoft 365 Enterprise E5</span></span>
- <span data-ttu-id="add0d-269">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="add0d-269">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="add0d-270">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="add0d-270">Microsoft Threat Protection</span></span>
- <span data-ttu-id="add0d-271">Plan 2 de protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="add0d-271">Office 365 Advanced Threat Protection Plan 2</span></span>

<span data-ttu-id="add0d-272">Para obtener más información acerca de la disponibilidad de características, visite el [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="add0d-272">To learn more about feature availability, visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

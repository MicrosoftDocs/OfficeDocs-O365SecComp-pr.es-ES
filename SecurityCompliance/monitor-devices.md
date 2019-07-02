---
title: Supervisión y generación de informes de dispositivos en el centro de seguridad 365 de Microsoft
description: Describe cómo puede mantener los dispositivos protegidos, actualizarse y detectar posibles amenazas en la organización.
keywords: seguridad, malware, Microsoft 365, M365, centro de seguridad, monitor, informe, dispositivos
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 44fd28a0ba2ec72d999c89d183d85ccb496903ec
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852874"
---
# <a name="device-monitoring-and-reporting-in-microsoft-365-security-center"></a><span data-ttu-id="c6f99-104">Supervisión y generación de informes de dispositivos en el centro de seguridad 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c6f99-104">Device monitoring and reporting in Microsoft 365 security center</span></span>

<span data-ttu-id="c6f99-105">Mantenga los dispositivos protegidos, actualizados y detecte posibles amenazas en el centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c6f99-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="c6f99-106">Ver alertas de dispositivos</span><span class="sxs-lookup"><span data-stu-id="c6f99-106">View device alerts</span></span>

<span data-ttu-id="c6f99-107">Obtén las alertas actualizadas sobre la actividad de infracciones y otras amenazas en tus dispositivos de ATP de Microsoft defender (disponible con una licencia E5).</span><span class="sxs-lookup"><span data-stu-id="c6f99-107">Get up-to-date alerts about breach activity and other threats on your devices from Microsoft Defender ATP (available with an E5 license).</span></span> <span data-ttu-id="c6f99-108">El centro de seguridad 365 de Microsoft supervisa con eficacia estas alertas en un nivel alto usando el flujo de trabajo preferido.</span><span class="sxs-lookup"><span data-stu-id="c6f99-108">Microsoft 365 security center effectively monitors these alerts at a high level using your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="c6f99-109">Supervisar alertas de alto impacto</span><span class="sxs-lookup"><span data-stu-id="c6f99-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="c6f99-110">Cada alerta de ATP de Microsoft defender tiene una gravedad correspondiente (alta, media, baja o informativa) que indica su posible impacto en la red si se deja desatendida.</span><span class="sxs-lookup"><span data-stu-id="c6f99-110">Each Microsoft Defender ATP alert has a corresponding severity—high, medium, low, or informational—that indicates its potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="c6f99-111">Use la tarjeta de **gravedad de alertas de dispositivos** para centrarse específicamente en las alertas más graves y que puedan requerir respuesta inmediata.</span><span class="sxs-lookup"><span data-stu-id="c6f99-111">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="c6f99-112">Desde esta tarjeta, puede ver más información en el portal del centro de seguridad de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="c6f99-112">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![Tarjeta de gravedad de alertas de dispositivos](./media/security-docs/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="c6f99-114">Comprender los orígenes de las alertas</span><span class="sxs-lookup"><span data-stu-id="c6f99-114">Understand sources of alerts</span></span>

<span data-ttu-id="c6f99-115">ATP de Microsoft defender aprovecha los datos de una amplia gama de sensores de seguridad y orígenes de inteligencia para generar alertas.</span><span class="sxs-lookup"><span data-stu-id="c6f99-115">Microsoft Defender ATP leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="c6f99-116">Por ejemplo, puede usar la información de detección de antivirus de Windows Defender y antimalware de terceros, así como de su propia inteligencia de amenazas personalizada que se proporciona a través de la API del servicio Web.</span><span class="sxs-lookup"><span data-stu-id="c6f99-116">For example, it can use detection information from Windows Defender Antivirus and third-party antimalware, as well as your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="c6f99-117">La tarjeta orígenes de **detección de alertas de dispositivo** muestra la distribución de las alertas por origen.</span><span class="sxs-lookup"><span data-stu-id="c6f99-117">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="c6f99-118">Esta tarjeta puede ayudarle a realizar un seguimiento de las actividades relacionadas con determinados orígenes, especialmente con los orígenes personalizados.</span><span class="sxs-lookup"><span data-stu-id="c6f99-118">This card can help you track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="c6f99-119">También puede usarlo para centrarse en las alertas procedentes de sensores que no están configurados para bloquear automáticamente la actividad o los componentes malintencionados.</span><span class="sxs-lookup"><span data-stu-id="c6f99-119">You can also use this to focus on alerts coming from sensors that are not configured to automatically block malicious activity or components.</span></span>

![Tarjeta de origen de detección de alertas de dispositivo](./media/security-docs/device-alert-detection-sources.png)

<span data-ttu-id="c6f99-121">Desde esta tarjeta, puede ver más información en el portal del centro de seguridad de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="c6f99-121">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="c6f99-122">Descripción de los tipos de amenazas que desencadenan alertas</span><span class="sxs-lookup"><span data-stu-id="c6f99-122">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="c6f99-123">ATP de Microsoft defender ordena cada alerta en una categoría que representa una determinada fase de la cadena de ataques o un tipo de componente de amenaza.</span><span class="sxs-lookup"><span data-stu-id="c6f99-123">Microsoft Defender ATP sorts each alert into a category representing a certain stage in the attack chain or a type of threat component.</span></span> <span data-ttu-id="c6f99-124">Por ejemplo, la actividad de amenazas detectadas se puede clasificar en "movimiento lateral" para indicar que la actividad implicaba un intento de llegar a otros dispositivos de la red y que se produjera después de que los atacantes hayan obtenido una inicialización.</span><span class="sxs-lookup"><span data-stu-id="c6f99-124">For example, detected threat activity might be categorized into “lateral movement” to indicate that the activity involved an attempt to reach other devices on the network and has likely occurred after attackers have gained an initial foothold.</span></span> <span data-ttu-id="c6f99-125">Cuando se detecta, un componente de amenaza puede clasificarse ampliamente como "malware" o más específicamente como "ransomware", "robo de credenciales" u otros tipos de software malintencionado o no deseado.</span><span class="sxs-lookup"><span data-stu-id="c6f99-125">When detected, a threat component might either be classified broadly as “malware” or more specifically as “ransomware”, “credential stealing” or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="c6f99-126">La tarjeta de **categorías de amenaza de dispositivo** muestra la distribución de las alertas a estas categorías.</span><span class="sxs-lookup"><span data-stu-id="c6f99-126">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="c6f99-127">Puede usar esta información para identificar la actividad de amenazas, como los intentos de robo de credenciales, que pueden tener un impacto más significativo en comparación con los intentos de ingeniería social, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c6f99-127">You can use this information to identify threat activity, such as attempts at credential theft, which can have more significant impact compared to attempts at social engineering, for example.</span></span> <span data-ttu-id="c6f99-128">También puede usar esta para supervisar amenazas potencialmente destructivas como ransomware.</span><span class="sxs-lookup"><span data-stu-id="c6f99-128">You can also use this to monitor for potentially destructive threats like ransomware.</span></span>

![Tarjeta de categorías de amenaza de dispositivo](./media/security-docs/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="c6f99-130">Supervisar alertas activas</span><span class="sxs-lookup"><span data-stu-id="c6f99-130">Monitor active alerts</span></span>

<span data-ttu-id="c6f99-131">La tarjeta de **Estado de alerta de dispositivo** indica el número de alertas que no se han resuelto y que pueden requerir atención.</span><span class="sxs-lookup"><span data-stu-id="c6f99-131">The **Device alert status** card indicates the number of alerts that have not been resolved and might require attention.</span></span> <span data-ttu-id="c6f99-132">Desde esta tarjeta, puede ver más información en el portal del centro de seguridad de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="c6f99-132">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![Tarjeta de estado de alerta de dispositivo](./media/security-docs/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="c6f99-134">Supervisión de la clasificación de las alertas resueltas</span><span class="sxs-lookup"><span data-stu-id="c6f99-134">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="c6f99-135">Al resolver una alerta de ATP de Microsoft defender, el personal de seguridad puede especificar si se ha verificado una alerta como:</span><span class="sxs-lookup"><span data-stu-id="c6f99-135">When resolving a Microsoft Defender ATP alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="c6f99-136">Una alerta verdadera que identifica la actividad de infracciones real o los componentes de amenazas</span><span class="sxs-lookup"><span data-stu-id="c6f99-136">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="c6f99-137">Una alerta falsa que ha detectado incorrectamente actividad normal</span><span class="sxs-lookup"><span data-stu-id="c6f99-137">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="c6f99-138">La tarjeta de **clasificación de alertas de dispositivo** muestra si las alertas resueltas se clasificaron como verdaderas o falsas alertas.</span><span class="sxs-lookup"><span data-stu-id="c6f99-138">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="c6f99-139">Desde esta tarjeta, puede ver más información en el portal del centro de seguridad de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="c6f99-139">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="c6f99-140">Nota: en algunos casos, la información de clasificación no está disponible para determinadas alertas.</span><span class="sxs-lookup"><span data-stu-id="c6f99-140">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![Tarjeta de clasificación de alertas de dispositivo](./media/security-docs/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="c6f99-142">Determinación de la determinación de alertas resueltas</span><span class="sxs-lookup"><span data-stu-id="c6f99-142">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="c6f99-143">Además de clasificar si una alerta es verdadera o falsa durante la resolución, el personal de seguridad puede proporcionar una determinación, que indica el tipo de actividad normal o malintencionada que se encontró al validar la alerta.</span><span class="sxs-lookup"><span data-stu-id="c6f99-143">In addition to classifying whether an alert is true or false during resolution, your security staff can provide a determination, indicating the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="c6f99-144">La tarjeta de **determinación de alertas de dispositivos** muestra la determinación que se proporciona para cada alerta, en concreto:</span><span class="sxs-lookup"><span data-stu-id="c6f99-144">The **Device alert determination** card shows the determination provided for each alert, specifically:</span></span>

* <span data-ttu-id="c6f99-145">**Apt** : amenaza persistente avanzada, que indica que el componente de amenaza o actividad detectada forma parte de una infracción compleja diseñada para llegar a la red afectada</span><span class="sxs-lookup"><span data-stu-id="c6f99-145">**APT** – advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="c6f99-146">**Malware** : archivo o código malintencionado</span><span class="sxs-lookup"><span data-stu-id="c6f99-146">**Malware** – malicious file or code</span></span>
* <span data-ttu-id="c6f99-147">**Personal de seguridad** : actividad normal realizada por el personal de seguridad</span><span class="sxs-lookup"><span data-stu-id="c6f99-147">**Security personnel** – normal activity performed by security staff</span></span>
* <span data-ttu-id="c6f99-148">**Pruebas de seguridad** : actividades o componentes diseñados para simular amenazas reales y que se espera que desencadenen sensores de seguridad y generen alertas</span><span class="sxs-lookup"><span data-stu-id="c6f99-148">**Security testing** – activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="c6f99-149">**Software no deseado** : aplicaciones y otro software que no se consideran malintencionados pero que infringen las directivas o los estándares de uso aceptables</span><span class="sxs-lookup"><span data-stu-id="c6f99-149">**Unwanted software** – apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="c6f99-150">**Otros** : cualquier otra determinación que no se incluya en los tipos proporcionados</span><span class="sxs-lookup"><span data-stu-id="c6f99-150">**Others** – any other determination that does not fall under the provided types</span></span>

<span data-ttu-id="c6f99-151">Desde esta tarjeta, puede ver más información en el centro de seguridad de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="c6f99-151">From this card, you can view more information in Microsoft Defender Security Center.</span></span>

![Tarjeta de determinación de alertas de dispositivo](./media/security-docs/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="c6f99-153">Comprender qué dispositivos están expuestos</span><span class="sxs-lookup"><span data-stu-id="c6f99-153">Understand which devices are at risk</span></span>

<span data-ttu-id="c6f99-154">La **protección de dispositivos** muestra el nivel de riesgo para los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c6f99-154">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="c6f99-155">El nivel de riesgo se basa en factores como el tipo y la gravedad de las alertas en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c6f99-155">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![Tarjeta de protección de dispositivos](./media/security-docs/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="c6f99-157">Supervisión e informes del estado de los dispositivos administrados por Intune</span><span class="sxs-lookup"><span data-stu-id="c6f99-157">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="c6f99-158">Los siguientes informes contienen datos de los dispositivos inscritos en Intune.</span><span class="sxs-lookup"><span data-stu-id="c6f99-158">The following reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="c6f99-159">No se incluyen los datos de los dispositivos no inscritos.</span><span class="sxs-lookup"><span data-stu-id="c6f99-159">Data from unenrolled devices is not included.</span></span> <span data-ttu-id="c6f99-160">Solo los administradores globales pueden ver estas tarjetas.</span><span class="sxs-lookup"><span data-stu-id="c6f99-160">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="c6f99-161">Los datos de dispositivos inscritos de Intune incluyen:</span><span class="sxs-lookup"><span data-stu-id="c6f99-161">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="c6f99-162">Cumplimiento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="c6f99-162">Device compliance</span></span>
* <span data-ttu-id="c6f99-163">Dispositivos con malware activo</span><span class="sxs-lookup"><span data-stu-id="c6f99-163">Devices with active malware</span></span>
* <span data-ttu-id="c6f99-164">Tipos de malware en dispositivos</span><span class="sxs-lookup"><span data-stu-id="c6f99-164">Types of malware on devices</span></span>
* <span data-ttu-id="c6f99-165">Malware en dispositivos</span><span class="sxs-lookup"><span data-stu-id="c6f99-165">Malware on devices</span></span>
* <span data-ttu-id="c6f99-166">Dispositivos con detecciones de malware</span><span class="sxs-lookup"><span data-stu-id="c6f99-166">Devices with malware detections</span></span>
* <span data-ttu-id="c6f99-167">Usuarios con detecciones de malware</span><span class="sxs-lookup"><span data-stu-id="c6f99-167">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="c6f99-168">Supervisar el cumplimiento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="c6f99-168">Monitor device compliance</span></span>

<span data-ttu-id="c6f99-169">El **cumplimiento de dispositivos** muestra el número de dispositivos inscritos en Intune compatibles con las directivas de configuración.</span><span class="sxs-lookup"><span data-stu-id="c6f99-169">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![Tarjeta de cumplimiento de dispositivos](./media/security-docs/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="c6f99-171">Detectar dispositivos con detecciones de malware</span><span class="sxs-lookup"><span data-stu-id="c6f99-171">Discover devices with malware detections</span></span>

<span data-ttu-id="c6f99-172">**Detecciones de malware de dispositivos** proporciona el número de dispositivos inscritos de Intune con malware que no se han resuelto completamente debido a acciones pendientes: un reinicio, un análisis completo o acciones manuales del usuario, o si la acción de corrección no se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c6f99-172">**Device malware detections** provides the number of Intune enrolled devices with malware that have not been fully resolved due to pending actions—a restart, a full scan or manual user actions—or if the remediation action did not complete successfully.</span></span>

![Tarjeta de detección de malware de dispositivo](./media/security-docs/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="c6f99-174">Descripción de los tipos de malware detectados</span><span class="sxs-lookup"><span data-stu-id="c6f99-174">Understand the types of malware detected</span></span>

<span data-ttu-id="c6f99-175">**Tipos de malware en dispositivos** muestra distintos tipos de malware que se han detectado en los dispositivos inscritos en Intune.</span><span class="sxs-lookup"><span data-stu-id="c6f99-175">**Types of malware on devices** shows different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="c6f99-176">Puede investigar cada tipo en el centro de seguridad 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c6f99-176">You can investigate each type in Microsoft 365 security center.</span></span>

![Tipos de malware en la tarjeta de dispositivos](./media/security-docs/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="c6f99-178">Comprender el malware específico detectado en los dispositivos</span><span class="sxs-lookup"><span data-stu-id="c6f99-178">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="c6f99-179">**Malware on** Devices proporciona una lista del malware específico detectado en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c6f99-179">**Malware on devices** provides a list of the specific malware detected on your devices.</span></span>

![Malware en tarjeta de dispositivos](./media/security-docs/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="c6f99-181">Conocer los dispositivos que tienen más malware</span><span class="sxs-lookup"><span data-stu-id="c6f99-181">Understand which devices have the most malware</span></span>

<span data-ttu-id="c6f99-182">**Dispositivos con detecciones de malware** muestra los dispositivos que tienen más detecciones de malware.</span><span class="sxs-lookup"><span data-stu-id="c6f99-182">**Devices with malware detections** shows which devices have the most malware detections.</span></span> <span data-ttu-id="c6f99-183">En el centro de seguridad de Microsoft 365, puede investigar si el malware está activo, quién usa el dispositivo y su estado de administración en Intune.</span><span class="sxs-lookup"><span data-stu-id="c6f99-183">In Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![Tarjeta de detección de dispositivos con malware](./media/security-docs/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="c6f99-185">Comprender qué usuarios tienen dispositivos con más malware</span><span class="sxs-lookup"><span data-stu-id="c6f99-185">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="c6f99-186">**Los usuarios con detecciones de malware** muestran a los usuarios con dispositivos que han detectado más malware.</span><span class="sxs-lookup"><span data-stu-id="c6f99-186">**Users with malware detections** shows users with devices that had the most malware detections.</span></span> <span data-ttu-id="c6f99-187">En el centro de seguridad de Microsoft 365, puede ver cuántos dispositivos se asignan a cada usuario y más información acerca de cada dispositivo y el tipo de malware.</span><span class="sxs-lookup"><span data-stu-id="c6f99-187">In Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![Usuarios con tarjeta de detección de malware](./media/security-docs/users-with-malware-detections.png)

## <a name="monitor-and-manage-asr-rule-deployment-and-detections"></a><span data-ttu-id="c6f99-189">Supervisión y administración de la implementación y detección de reglas de ASR</span><span class="sxs-lookup"><span data-stu-id="c6f99-189">Monitor and manage ASR rule deployment and detections</span></span>

<span data-ttu-id="c6f99-190">[Las reglas de reducción de superficie de ataques (ASR)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) ayudan a evitar que las acciones y aplicaciones que suelen usar los ataques de malware que buscan equipos infecten.</span><span class="sxs-lookup"><span data-stu-id="c6f99-190">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) help prevent actions and apps that are typically used by exploit-seeking malware to infect machines.</span></span> <span data-ttu-id="c6f99-191">Estas reglas controlan Cuándo y cómo se pueden ejecutar los ejecutables.</span><span class="sxs-lookup"><span data-stu-id="c6f99-191">These rules control when and how executables can run.</span></span> <span data-ttu-id="c6f99-192">Por ejemplo, puede impedir que JavaScript o VBScript inicien un archivo ejecutable descargado, bloquee las llamadas a la API de Win32 desde macros de Office o bloquee procesos que se ejecuten desde unidades USB.</span><span class="sxs-lookup"><span data-stu-id="c6f99-192">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![Tarjeta de reducción de superficie de ataques](./media/security-docs/attack-surface-reduction-rules.png)

<span data-ttu-id="c6f99-194">La tarjeta de **reglas de reducción de superficie de ataques** proporciona información general sobre la implementación de reglas en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c6f99-194">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="c6f99-195">La barra superior de la tarjeta muestra el número total de dispositivos que se encuentran en los siguientes modos de implementación:</span><span class="sxs-lookup"><span data-stu-id="c6f99-195">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="c6f99-196">**Modo de bloqueo** : dispositivos con al menos una regla configurada para bloquear la actividad detectada</span><span class="sxs-lookup"><span data-stu-id="c6f99-196">**Block mode** – devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="c6f99-197">**Modo auditoría** : dispositivos sin reglas establecidas para bloquear la actividad detectada, pero tiene al menos una regla establecida para auditar la actividad detectada</span><span class="sxs-lookup"><span data-stu-id="c6f99-197">**Audit mode** – devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="c6f99-198">\*\*\*\* Desactivado: dispositivos con todas las reglas de ASR desactivadas</span><span class="sxs-lookup"><span data-stu-id="c6f99-198">**Off** – devices with all ASR rules turned off</span></span>

<span data-ttu-id="c6f99-199">La parte inferior de esta tarjeta muestra la configuración por regla en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c6f99-199">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="c6f99-200">Cada barra indica el número de dispositivos que están configurados para bloquear o auditar o que la regla se ha desactivado completamente.</span><span class="sxs-lookup"><span data-stu-id="c6f99-200">Each bar indicates the number of devices that are set to block or audit detection or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="c6f99-201">Ver detecciones de ASR</span><span class="sxs-lookup"><span data-stu-id="c6f99-201">View ASR detections</span></span>

<span data-ttu-id="c6f99-202">Para ver información detallada sobre las detecciones de reglas de ASR en la red, seleccione **Ver detecciones** en la tarjeta de **reglas de reducción de superficie de ataques** .</span><span class="sxs-lookup"><span data-stu-id="c6f99-202">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="c6f99-203">Se \*\*\*\* abrirá la pestaña detecciones de la página informe detallado.</span><span class="sxs-lookup"><span data-stu-id="c6f99-203">The **Detections** tab in the detailed report page will open.</span></span>

![Pestaña detecciones](./media/security-docs/detections-tab.png)

<span data-ttu-id="c6f99-205">El gráfico de la parte superior de la página muestra las detecciones con detecciones de agrupamiento de tiempo que se bloquearon o auditaron.</span><span class="sxs-lookup"><span data-stu-id="c6f99-205">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="c6f99-206">La tabla de la parte inferior muestra las detecciones más recientes.</span><span class="sxs-lookup"><span data-stu-id="c6f99-206">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="c6f99-207">Use la siguiente información en la tabla para comprender la naturaleza de las detecciones:</span><span class="sxs-lookup"><span data-stu-id="c6f99-207">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="c6f99-208">**Archivo detectado** : el archivo, normalmente un script o un documento, cuyo contenido activó la actividad de ataque sospechoso</span><span class="sxs-lookup"><span data-stu-id="c6f99-208">**Detected file** – the file, typically a script or a document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="c6f99-209">**Regla** : nombre que describe las actividades de ataque para las que se ha diseñado la regla.</span><span class="sxs-lookup"><span data-stu-id="c6f99-209">**Rule** – name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="c6f99-210">Leer acerca de las reglas de ASR existentes</span><span class="sxs-lookup"><span data-stu-id="c6f99-210">Read about existing ASR rules</span></span>
* <span data-ttu-id="c6f99-211">**Aplicación de origen** : la aplicación que ha cargado o ejecutado contenido que desencadena la actividad de ataque sospechoso.</span><span class="sxs-lookup"><span data-stu-id="c6f99-211">**Source app** – the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="c6f99-212">Puede ser una aplicación legítima, como un explorador Web, una aplicación de Office o una herramienta del sistema como PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6f99-212">This could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="c6f99-213">**Editor** : proveedor que liberó la aplicación de origen</span><span class="sxs-lookup"><span data-stu-id="c6f99-213">**Publisher** – the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="c6f99-214">Revisar la configuración de la regla de ASR del dispositivo</span><span class="sxs-lookup"><span data-stu-id="c6f99-214">Review device ASR rule settings</span></span>

<span data-ttu-id="c6f99-215">En la página informe de **reglas de reducción de superficie de ataques** , vaya a la ficha de **configuración** para revisar la configuración de las reglas para dispositivos individuales.</span><span class="sxs-lookup"><span data-stu-id="c6f99-215">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="c6f99-216">Seleccione un dispositivo para obtener información detallada acerca de si cada regla está en modo de bloqueo, modo de auditoría o apagado por completo.</span><span class="sxs-lookup"><span data-stu-id="c6f99-216">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

![Ficha Configuración](./media/security-docs/configuration-tab.png)

<span data-ttu-id="c6f99-218">Microsoft Intune proporciona funciones de administración para las reglas de ASR.</span><span class="sxs-lookup"><span data-stu-id="c6f99-218">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="c6f99-219">Si desea actualizar la configuración, seleccione Introducción a \*\*\*\* **configurar dispositivos** en la ficha para abrir Administración de dispositivos en Intune.</span><span class="sxs-lookup"><span data-stu-id="c6f99-219">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="c6f99-220">Excluir archivos de las reglas de ASR</span><span class="sxs-lookup"><span data-stu-id="c6f99-220">Exclude files from ASR rules</span></span>

<span data-ttu-id="c6f99-221">El centro de seguridad 365 de Microsoft recopila los nombres de los [archivos que](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/troubleshoot-asr#add-exclusions-for-a-false-positive) puede que desee excluir de las detecciones mediante las reglas de reducción de la superficie de ataques.</span><span class="sxs-lookup"><span data-stu-id="c6f99-221">Microsoft 365 security center collects the names of the [files you might want to exclude](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/troubleshoot-asr#add-exclusions-for-a-false-positive) from detections by attack surface reduction rules.</span></span> <span data-ttu-id="c6f99-222">Al excluir archivos, puede reducir las detecciones de falsos positivos y implementar con mayor confianza las reglas de reducción de superficie de ataques en el modo de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c6f99-222">By excluding files, you can reduce false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="c6f99-223">Las exclusiones se administran en Microsoft Intune, pero el centro de seguridad de Microsoft 365 proporciona una herramienta de análisis para ayudarle a comprender los archivos.</span><span class="sxs-lookup"><span data-stu-id="c6f99-223">The exclusions are managed on Microsoft Intune, but Microsoft 365 security center provides an analysis tool to help you understand the files.</span></span> <span data-ttu-id="c6f99-224">Para iniciar la recopilación de archivos para su exclusión, vaya a la pestaña **agregar exclusiones** en la página del informe **reglas de reducción de superficie de ataques** .</span><span class="sxs-lookup"><span data-stu-id="c6f99-224">To start collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

>[!NOTE]  
><span data-ttu-id="c6f99-225">La herramienta analiza las detecciones por todas las reglas de reducción de la superficie de ataque, pero [solo algunas reglas admiten exclusiones](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="c6f99-225">The tool analyzes detections by all attack surface reduction rules, but [only some rules support exclusions](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules).</span></span>

![Ficha agregar exclusiones](./media/security-docs/add-exclusions-tab.png)

<span data-ttu-id="c6f99-227">En la tabla se enumeran todos los nombres de archivo detectados por las reglas de reducción de la superficie de ataques.</span><span class="sxs-lookup"><span data-stu-id="c6f99-227">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="c6f99-228">Puede seleccionar archivos para revisar el impacto de excluirlos:</span><span class="sxs-lookup"><span data-stu-id="c6f99-228">You can select files to review the impact of excluding them:</span></span>

* <span data-ttu-id="c6f99-229">El número de detecciones</span><span class="sxs-lookup"><span data-stu-id="c6f99-229">How many fewer detections</span></span>
* <span data-ttu-id="c6f99-230">El número de dispositivos que informan sobre las detecciones</span><span class="sxs-lookup"><span data-stu-id="c6f99-230">How many fewer devices report the detections</span></span>

<span data-ttu-id="c6f99-231">Para obtener una lista de los archivos seleccionados con todas las rutas de acceso para la exclusión, seleccione **obtener rutas de exclusión**.</span><span class="sxs-lookup"><span data-stu-id="c6f99-231">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="c6f99-232">Registros para la regla de bloqueo de credenciales de ASR **robo desde el subsistema de la autoridad de seguridad local de Windows (LSASS. exe)** Capture la aplicación de origen **LSASS. exe**, un archivo de sistema normal, como el archivo detectado.</span><span class="sxs-lookup"><span data-stu-id="c6f99-232">Logs for the ASR rule **Block credential stealing from the Windows local security authority subsystem (lsass.exe)** capture the source app **lsass.exe**, a normal system file, as the detected file.</span></span> <span data-ttu-id="c6f99-233">Como resultado, la lista generada de rutas de exclusión incluirá este archivo.</span><span class="sxs-lookup"><span data-stu-id="c6f99-233">As a result, the generated list of exclusion paths will include this file.</span></span> <span data-ttu-id="c6f99-234">Para excluir el archivo que desencadenó esta regla en lugar de **LSASS. exe**, use la ruta de acceso a la aplicación de origen en lugar del archivo detectado.</span><span class="sxs-lookup"><span data-stu-id="c6f99-234">To exclude the file that triggered this rule instead of **lsass.exe**, use the path to the source app instead of the detected file.</span></span>

<span data-ttu-id="c6f99-235">Para encontrar la aplicación de origen, ejecute la siguiente [consulta de búsqueda avanzada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) para esta regla específica (identificada por el identificador de regla 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span><span class="sxs-lookup"><span data-stu-id="c6f99-235">To locate the source app, run the following [advanced hunting query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) for this specific rule (identified by rule ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span></span>

```MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a><span data-ttu-id="c6f99-236">Comprobar archivos para su exclusión</span><span class="sxs-lookup"><span data-stu-id="c6f99-236">Check files for exclusion</span></span>
<span data-ttu-id="c6f99-237">Antes de excluir un archivo de ASR, le recomendamos que inspeccione el archivo para determinar si realmente no es malintencionado.</span><span class="sxs-lookup"><span data-stu-id="c6f99-237">Before excluding a file from ASR, we recommend that you inspect the file to determine if it is indeed not malicious.</span></span>

<span data-ttu-id="c6f99-238">Para revisar un archivo, use la [Página de información del archivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) en el centro de seguridad de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="c6f99-238">To review a file, use the [file information page](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) on Microsoft Defender Security Center.</span></span> <span data-ttu-id="c6f99-239">La página proporciona información sobre la prevalencia y la relación de detección de virus VirusTotal.</span><span class="sxs-lookup"><span data-stu-id="c6f99-239">The page provides prevalence information as well as the VirusTotal antivirus detection ratio.</span></span> <span data-ttu-id="c6f99-240">También puede usar la página para enviar el archivo para un análisis detallado.</span><span class="sxs-lookup"><span data-stu-id="c6f99-240">You can also use the page to submit the file for deep analysis.</span></span>

<span data-ttu-id="c6f99-241">Para buscar un archivo detectado en el centro de seguridad de Microsoft defender, busque todas las detecciones de ASR mediante la siguiente consulta de búsqueda avanzada:</span><span class="sxs-lookup"><span data-stu-id="c6f99-241">To locate a detected file in Microsoft Defender Security Center, search for all ASR detections using the following advanced hunting query:</span></span>

```MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

<span data-ttu-id="c6f99-242">Use **SHA1** o **InitiatingProcessSHA1** en los resultados para buscar el archivo mediante la barra de búsqueda universal en el centro de seguridad de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="c6f99-242">Use the **SHA1** or the **InitiatingProcessSHA1** in the results to search for the file using the universal search bar in Microsoft Defender Security Center.</span></span>

---
title: Supervisar los dispositivos de seguridad de Microsoft 365
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
ms.openlocfilehash: 31d89b8bbcad98814ff33764bad24bffbbba4968
ms.sourcegitcommit: 8213c353954b92f5c3979bee4aa049da0fd28a18
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2019
ms.locfileid: "31043261"
---
# <a name="monitor-devices-in-microsoft-365-security"></a>Supervisar los dispositivos de seguridad de Microsoft 365

Mantenga los dispositivos protegidos, actualizados y detecte posibles amenazas en el centro de seguridad de Microsoft 365.

## <a name="view-device-alerts"></a>Ver alertas de dispositivos

Obtén las alertas actualizadas sobre la actividad de infracciones y otras amenazas de los dispositivos desde ATP de Windows Defender (disponible con una licencia E5). El centro de seguridad 365 de Microsoft ofrece varias tarjetas que le permiten supervisar de forma eficaz estas alertas en un nivel alto, en función de su flujo de trabajo preferido.

### <a name="monitor-high-impact-alerts"></a>Supervisar alertas de alto impacto

Cada alerta de ATP de Windows Defender tiene una gravedad correspondiente (alta, media, baja o informativa) que indica su posible impacto en la red si se deja desatendida.  

Use la tarjeta de **gravedad de alertas de dispositivos** para centrarse específicamente en las alertas más graves y que puedan requerir respuesta inmediata. Desde esta tarjeta, puede ver más información en el portal del centro de seguridad de Windows Defender.

![Tarjeta de gravedad de alertas de dispositivos](./media/security-docs/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a>Comprender los orígenes de las alertas

Windows Defender ATP aprovecha los datos de una amplia gama de sensores de seguridad y orígenes de inteligencia para generar alertas. Por ejemplo, puede usar la información de detección de antivirus de Windows Defender y antimalware de terceros, así como de su propia inteligencia de amenazas personalizada que se proporciona a través de la API del servicio Web.

La tarjeta orígenes de **detección de alertas de dispositivo** muestra la distribución de las alertas por origen. Esta tarjeta puede ayudarle a realizar un seguimiento de las actividades relacionadas con determinados orígenes, especialmente con los orígenes personalizados. También puede usarlo para centrarse en las alertas procedentes de sensores que no están configurados para bloquear automáticamente la actividad o los componentes malintencionados.

![Tarjeta de origen de detección de alertas de dispositivo](./media/security-docs/device-alert-detection-sources.png)

Desde esta tarjeta, puede ver más información en el portal del centro de seguridad de Windows Defender.

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a>Descripción de los tipos de amenazas que desencadenan alertas

ATP de Windows Defender ordena cada alerta en una categoría que representa una determinada fase de la cadena de ataques o un tipo de componente de amenaza. Por ejemplo, la actividad de amenazas detectadas se puede clasificar en "movimiento lateral" para indicar que la actividad implicaba un intento de llegar a otros dispositivos de la red y que se produjera después de que los atacantes hayan obtenido una inicialización. Cuando se detecta, un componente de amenaza puede clasificarse ampliamente como "malware" o más específicamente como "ransomware", "robo de credenciales" u otros tipos de software malintencionado o no deseado.

La tarjeta de **categorías de amenaza de dispositivo** muestra la distribución de las alertas a estas categorías. Puede usar esta información para identificar la actividad de amenazas, como los intentos de robo de credenciales, que pueden tener un impacto más significativo en comparación con los intentos de ingeniería social, por ejemplo. También puede usar esta para supervisar amenazas potencialmente destructivas como ransomware.

![Tarjeta de categorías de amenaza de dispositivo](./media/security-docs/device-threat-categories.png)

### <a name="monitor-active-alerts"></a>Supervisar alertas activas

La tarjeta de **Estado de alerta de dispositivo** indica el número de alertas que no se han resuelto y que pueden requerir atención. Desde esta tarjeta, puede ver más información en el portal del centro de seguridad de Windows Defender.

![Tarjeta de estado de alerta de dispositivo](./media/security-docs/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a>Supervisión de la clasificación de las alertas resueltas

Al resolver una alerta de ATP de Windows Defender, el personal de seguridad puede especificar si se ha verificado una alerta como:

* Una alerta verdadera que identifica la actividad de infracciones real o los componentes de amenazas
* Una alerta falsa que ha detectado incorrectamente actividad normal

La tarjeta de **clasificación de alertas de dispositivo** muestra si las alertas resueltas se clasificaron como verdaderas o falsas alertas. Desde esta tarjeta, puede ver más información en el portal del centro de seguridad de Windows Defender.

Nota: en algunos casos, la información de clasificación no está disponible para determinadas alertas.

![Tarjeta de clasificación de alertas de dispositivo](./media/security-docs/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a>Determinación de la determinación de alertas resueltas

Además de clasificar si una alerta es verdadera o falsa durante la resolución, el personal de seguridad puede proporcionar una determinación, que indica el tipo de actividad normal o malintencionada que se encontró al validar la alerta.

La tarjeta de **determinación de alertas de dispositivos** muestra la determinación que se proporciona para cada alerta, en concreto:

* **Apt** : amenaza persistente avanzada, que indica que el componente de amenaza o actividad detectada forma parte de una infracción compleja diseñada para llegar a la red afectada  
* **Malware** : archivo o código malintencionado
* **Personal de seguridad** : actividad normal realizada por el personal de seguridad
* **Pruebas de seguridad** : actividades o componentes diseñados para simular amenazas reales y que se espera que desencadenen sensores de seguridad y generen alertas
* **Software no deseado** : aplicaciones y otro software que no se consideran malintencionados pero que infringen las directivas o los estándares de uso aceptables
* **Otros** : cualquier otra determinación que no se incluya en los tipos proporcionados

Desde esta tarjeta, puede ver más información en el centro de seguridad de Windows Defender.

![Tarjeta de determinación de alertas de dispositivo](./media/security-docs/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a>Comprender qué dispositivos están expuestos

La **protección de dispositivos** muestra el nivel de riesgo para los dispositivos. El nivel de riesgo se basa en factores como el tipo y la gravedad de las alertas en el dispositivo.

![Tarjeta de protección de dispositivos](./media/security-docs/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a>Supervisión e informes del estado de los dispositivos administrados por Intune

Los siguientes informes y supervisión contienen datos de los dispositivos inscritos en Intune. No se incluyen los datos de los dispositivos no inscritos. Solo los administradores globales pueden ver estas tarjetas.

Los datos de dispositivos inscritos de Intune incluyen:

* Cumplimiento de dispositivos
* Dispositivos con malware activo
* Tipos de malware en dispositivos
* Malware en dispositivos
* Dispositivos con detecciones de malware
* Usuarios con detecciones de malware

### <a name="monitor-device-compliance"></a>Supervisar el cumplimiento de dispositivos

El **cumplimiento de dispositivos** muestra el número de dispositivos inscritos en Intune compatibles con las directivas de configuración.

![Tarjeta de cumplimiento de dispositivos](./media/security-docs/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a>Detectar dispositivos con detecciones de malware

**Detecciones de malware de dispositivos** proporciona el número de dispositivos inscritos de Intune con malware que no se han resuelto completamente debido a acciones pendientes: un reinicio, un análisis completo o acciones manuales del usuario, o si la acción de corrección no se completó correctamente.

![Tarjeta de detección de malware de dispositivo](./media/security-docs/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a>Descripción de los tipos de malware detectados

**Tipos de malware en dispositivos** muestra distintos tipos de malware que se han detectado en los dispositivos inscritos en Intune. Puede investigar cada tipo en el centro de seguridad 365 de Microsoft.

![Tipos de malware en la tarjeta de dispositivos](./media/security-docs/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a>Comprender el malware específico detectado en los dispositivos

**Malware on** Devices proporciona una lista del malware específico detectado en los dispositivos.

![Malware en tarjeta de dispositivos](./media/security-docs/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a>Conocer los dispositivos que tienen más malware

**Dispositivos con detecciones de malware** muestra los dispositivos que tienen más detecciones de malware. En el centro de seguridad de Microsoft 365, puede investigar si el malware está activo, quién usa el dispositivo y su estado de administración en Intune.

![Tarjeta de detección de dispositivos con malware](./media/security-docs/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a>Comprender qué usuarios tienen dispositivos con más malware

**Los usuarios con detecciones de malware** muestran a los usuarios con dispositivos que han detectado más malware. En el centro de seguridad de Microsoft 365, puede ver cuántos dispositivos se asignan a cada usuario y más información acerca de cada dispositivo y el tipo de malware.

![Usuarios con tarjeta de detección de malware](./media/security-docs/users-with-malware-detections.png)

## <a name="monitor-and-manage-asr-rule-deployment-and-detections"></a>Supervisión y administración de la implementación y detección de reglas de ASR

[Las reglas de reducción de superficie de ataques (ASR)](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) ayudan a evitar que las acciones y aplicaciones que suelen usar los ataques de malware que buscan equipos infecten. Estas reglas controlan Cuándo y cómo se pueden ejecutar los ejecutables. Por ejemplo, puede impedir que JavaScript o VBScript inicien un archivo ejecutable descargado, bloquee las llamadas a la API de Win32 desde macros de Office o bloquee procesos que se ejecuten desde unidades USB.

![Tarjeta de reducción de superficie de ataques](./media/security-docs/attack-surface-reduction-rules.png)

La tarjeta de **reglas de reducción de superficie de ataques** proporciona información general sobre la implementación de reglas en los dispositivos.

La barra superior de la tarjeta muestra el número total de dispositivos que se encuentran en los siguientes modos de implementación:

* **Modo de bloqueo** : dispositivos con al menos una regla configurada para bloquear la actividad detectada
* **Modo auditoría** : dispositivos sin reglas establecidas para bloquear la actividad detectada, pero tiene al menos una regla establecida para auditar la actividad detectada  
* **** Desactivado: dispositivos con todas las reglas de ASR desactivadas

La parte inferior de esta tarjeta muestra la configuración por regla en los dispositivos. Cada barra indica el número de dispositivos que están configurados para bloquear o auditar o que la regla se ha desactivado completamente.

### <a name="view-asr-detections"></a>Ver detecciones de ASR

Para ver información detallada sobre las detecciones de reglas de ASR en la red, seleccione **Ver detecciones** en la tarjeta de **reglas de reducción de superficie de ataques** . Se **** abrirá la pestaña detecciones de la página informe detallado.

![Pestaña detecciones](./media/security-docs/detections-tab.png)

El gráfico de la parte superior de la página muestra las detecciones con detecciones de agrupamiento de tiempo que se bloquearon o auditaron. La tabla de la parte inferior muestra las detecciones más recientes. Use la siguiente información en la tabla para comprender la naturaleza de las detecciones:

* **Archivo detectado** : el archivo, normalmente un script o un documento, cuyo contenido activó la actividad de ataque sospechoso
* **Regla** : nombre que describe las actividades de ataque para las que se ha diseñado la regla. Leer acerca de las reglas de ASR existentes
* **Aplicación de origen** : la aplicación que ha cargado o ejecutado contenido que desencadena la actividad de ataque sospechoso. Puede ser una aplicación legítima, como un explorador Web, una aplicación de Office o una herramienta del sistema como PowerShell.
* **Editor** : proveedor que liberó la aplicación de origen

### <a name="review-device-asr-rule-settings"></a>Revisar la configuración de la regla de ASR del dispositivo

En la página informe de **reglas de reducción de superficie de ataques** , vaya a la ficha de **configuración** para revisar la configuración de las reglas para dispositivos individuales. Seleccione un dispositivo para obtener información detallada acerca de si cada regla está en modo de bloqueo, modo de auditoría o apagado por completo.

![Ficha Configuración](./media/security-docs/configuration-tab.png)

Microsoft Intune proporciona funciones de administración para las reglas de ASR. Si desea actualizar la configuración, seleccione Introducción a **** **configurar dispositivos** en la ficha para abrir Administración de dispositivos en Intune.

### <a name="exclude-files-from-asr-rules"></a>Excluir archivos de las reglas de ASR

Al excluir archivos de las detecciones, puede evitar detecciones falsas positivas no deseadas y implementar con mayor confianza las reglas de reducción de superficie de ataques en el modo de bloqueo.

Mientras que las exclusiones de archivos para las reglas de reducción de superficie de ataques se administran en Microsoft Intune, el centro de seguridad 365 de Microsoft proporciona una herramienta de análisis para ayudarle a comprender los archivos que activan las detecciones. También ayuda a recopilar los nombres de los archivos que puede que desee excluir.

Para empezar a analizar las detecciones y recopilar los archivos para su exclusión, vaya a la pestaña **agregar exclusiones** en la página del informe de **reglas de reducción de superficie de ataques** .

![Ficha agregar exclusiones](./media/security-docs/add-exclusions-tab.png)

En la tabla se enumeran todos los nombres de archivo detectados por las reglas de reducción de la superficie de ataques. Una vez que haya seleccionado un archivo o varios archivos, puede revisar el impacto de agregar dichos archivos a sus excepciones:

* La reducción del número total de detecciones
* La reducción en el número total de dispositivos afectados por las detecciones

Para obtener una lista de los archivos seleccionados con todas las rutas de acceso para la exclusión, seleccione **obtener rutas de exclusión**.

Para obtener más información acerca de las exclusiones e instrucciones detalladas sobre cómo agregarlas, vea [solucionar problemas de las reglas de reducción](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-exploit-guard/troubleshoot-asr)de la superficie de ataque.

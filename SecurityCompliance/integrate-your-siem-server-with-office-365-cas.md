---
title: Integrar el servidor SIEM con Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: dd6d2417-49c4-4de6-9294-67fdabbf8532
description: También puede integrar su servidor SIEM con seguridad de la aplicación de nube de Office 365. Lea este artículo para obtener información general sobre cómo funciona y cómo configurarla.
ms.openlocfilehash: 3cdae0389065b18da090139528eceefb007363fa
ms.sourcegitcommit: b0b0b716718c22779c7c04775b8010d65cd6656b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2019
ms.locfileid: "28723267"
---
# <a name="integrate-your-siem-server-with-office-365-cloud-app-security"></a><span data-ttu-id="6219c-104">Integrar el servidor SIEM con Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6219c-104">Integrate your SIEM server with Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="6219c-105">Evaluación **\>**</span><span class="sxs-lookup"><span data-stu-id="6219c-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="6219c-106">Planeación de **\>**</span><span class="sxs-lookup"><span data-stu-id="6219c-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="6219c-107">Implementación **\>**</span><span class="sxs-lookup"><span data-stu-id="6219c-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="6219c-108">Utilización de \*\*\*</span><span class="sxs-lookup"><span data-stu-id="6219c-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="6219c-109">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="6219c-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="6219c-110">Comenzar a planear</span><span class="sxs-lookup"><span data-stu-id="6219c-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="6219c-111">¡Están aquí!</span><span class="sxs-lookup"><span data-stu-id="6219c-111">You are here!</span></span>  <br/> [<span data-ttu-id="6219c-112">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="6219c-112">Next step</span></span>](utilization-activities-for-ocas.md) <br/> |[<span data-ttu-id="6219c-113">Iniciar utilizando</span><span class="sxs-lookup"><span data-stu-id="6219c-113">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
## <a name="overview-and-prerequisites"></a><span data-ttu-id="6219c-114">Información general y los requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6219c-114">Overview and prerequisites</span></span>

<span data-ttu-id="6219c-p102">También puede integrar la [Seguridad de la aplicación de Office 365 en la nube](get-ready-for-office-365-cas.md) con el servidor de administración (SIEM) de eventos e información de seguridad para habilitar la supervisión centralizada de alertas. Esto es especialmente beneficioso para las organizaciones que usan servicios de nube locales y en aplicaciones de servidor. Integración con un servidor SIEM permite a su equipo de seguridad proteger mejor las aplicaciones de Office 365 que se mantiene el flujo de trabajo de seguridad habituales, al automatizar determinados procedimientos de seguridad y correlacionar entre basados en la nube y locales eventos.</span><span class="sxs-lookup"><span data-stu-id="6219c-p102">You can integrate [Office 365 Cloud App Security](get-ready-for-office-365-cas.md) with your security information and event management (SIEM) server to enable centralized monitoring of alerts. This is especially beneficial for organizations who are using cloud services and on-premises server applications. Integrating with a SIEM server allows your security team to better protect your Office 365 applications while maintaining your usual security workflow, by automating certain security procedures and correlating between cloud-based and on-premises events.</span></span>  
  
<span data-ttu-id="6219c-p103">Al integrar en primer lugar el servidor SIEM con seguridad de la aplicación de nube de Office 365, las alertas de los últimos dos días se transfieren en el servidor SIEM, así como todas las alertas desde, a continuación, en (basado en los filtros que seleccione). Además, si se deshabilita esta característica durante un período prolongado, cuando se vuelve a habilitar, reenviará los últimos dos días de alertas y, a continuación, todas las alertas de, a continuación, en.</span><span class="sxs-lookup"><span data-stu-id="6219c-p103">When you first integrate your SIEM server with Office 365 Cloud App Security, alerts from the last two days are forwarded to the SIEM server, as well as all alerts from then on (based on any filters you select). Additionally, if you disable this feature for an extended period, when you enable it again, it will forward the past two days of alerts and then all alerts from then on.</span></span>

### <a name="siem-integration-architecture"></a><span data-ttu-id="6219c-120">Arquitectura de integración de SIEM</span><span class="sxs-lookup"><span data-stu-id="6219c-120">SIEM integration architecture</span></span>

<span data-ttu-id="6219c-p104">Un agente SIEM está configurado en la red de su organización. Cuando se ha implementado y configurado, el agente de SIEM extrae los tipos de datos que se configuraron (alertas) mediante la API de REST de la seguridad de aplicaciones de Office 365 en la nube. A continuación, se envía el tráfico a través de un canal HTTPS cifrado en el puerto 443.</span><span class="sxs-lookup"><span data-stu-id="6219c-p104">A SIEM agent is set up in your organization's network. When deployed and configured, the SIEM agent pulls the data types that were configured (alerts) using Office 365 Cloud App Security RESTful APIs. The traffic is then sent over an encrypted HTTPS channel on port 443.</span></span>
  
<span data-ttu-id="6219c-124">Cuando un agente de SIEM recupera datos de seguridad de la aplicación de nube de Office 365, envía los mensajes de registro del sistema en el servidor local de SIEM con las configuraciones de red que se proporcionan durante la instalación (TCP o UDP con un puerto personalizado).</span><span class="sxs-lookup"><span data-stu-id="6219c-124">When a SIEM agent retrieves data from Office 365 Cloud App Security, it sends the Syslog messages to your local SIEM server using the network configurations that are provided during setup (TCP or UDP with a custom port).</span></span>

![Arquitectura de SIEM y seguridad de la aplicación en la nube](media/siem-architecture.png)

### <a name="supported-siem-servers"></a><span data-ttu-id="6219c-126">Servidores SIEM compatibles</span><span class="sxs-lookup"><span data-stu-id="6219c-126">Supported SIEM servers</span></span>

<span data-ttu-id="6219c-127">Seguridad de la aplicación de Office 365 en la nube actualmente es compatible con los servidores SIEM siguientes:</span><span class="sxs-lookup"><span data-stu-id="6219c-127">Office 365 Cloud App Security currently supports the following SIEM servers:</span></span>
- <span data-ttu-id="6219c-128">ArcSight Micro Focus</span><span class="sxs-lookup"><span data-stu-id="6219c-128">Micro Focus ArcSight</span></span>
- <span data-ttu-id="6219c-129">CEF genérica</span><span class="sxs-lookup"><span data-stu-id="6219c-129">Generic CEF</span></span>

### <a name="prerequisites"></a><span data-ttu-id="6219c-130">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6219c-130">Prerequisites</span></span>

- <span data-ttu-id="6219c-p105">Debe ser un administrador global o administrador de seguridad para llevar a cabo las tareas descritas en este artículo. Vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="6219c-p105">You must be a global administrator or security administrator to perform the tasks described in this article. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)</span></span>

- <span data-ttu-id="6219c-133">Debe tener [habilitada la seguridad de la aplicación de Office 365 en la nube](turn-on-office-365-cas.md) para su organización.</span><span class="sxs-lookup"><span data-stu-id="6219c-133">You must have [Office 365 Cloud App Security enabled](turn-on-office-365-cas.md) for your organization.</span></span>

- <span data-ttu-id="6219c-134">[Registro de auditoría](turn-audit-log-search-on-or-off.md) debe estar activada para Office 365</span><span class="sxs-lookup"><span data-stu-id="6219c-134">[Audit logging](turn-audit-log-search-on-or-off.md) must be turned on for Office 365</span></span>

- <span data-ttu-id="6219c-135">Debe tener un servidor estándar que cumple los siguientes requisitos para poder configurar la integración del servidor SIEM:</span><span class="sxs-lookup"><span data-stu-id="6219c-135">You must have a standard server that meets the following requirements in order to configure SIEM server integration:</span></span>
    - <span data-ttu-id="6219c-136">SO: Windows o Linux (puede ser una máquina virtual)</span><span class="sxs-lookup"><span data-stu-id="6219c-136">OS: Windows or Linux (this can be a virtual machine)</span></span>
    - <span data-ttu-id="6219c-137">CPU: 2</span><span class="sxs-lookup"><span data-stu-id="6219c-137">CPU: 2</span></span>
    - <span data-ttu-id="6219c-138">Espacio en disco: 20 GB</span><span class="sxs-lookup"><span data-stu-id="6219c-138">Disk space: 20 GB</span></span>
    - <span data-ttu-id="6219c-139">RAM: 2 GB</span><span class="sxs-lookup"><span data-stu-id="6219c-139">RAM: 2 GB</span></span>
    - <span data-ttu-id="6219c-140">[Oracle Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html) instalado</span><span class="sxs-lookup"><span data-stu-id="6219c-140">[Oracle Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html) installed</span></span>
    - <span data-ttu-id="6219c-141">Firewall configurado como se describe en [los requisitos de red](https://docs.microsoft.com/cloud-app-security/network-requirements)</span><span class="sxs-lookup"><span data-stu-id="6219c-141">Firewall configured as described in [Network requirements](https://docs.microsoft.com/cloud-app-security/network-requirements)</span></span>

- <span data-ttu-id="6219c-p106">Debe disponer de obtener información detallada sobre el **host remoto de registro del sistema** y el **número de puerto de Syslot**. Un administrador de red o un administrador de seguridad debe ser capaz de ayudarle a encontrar esa información.</span><span class="sxs-lookup"><span data-stu-id="6219c-p106">You must have details about your **Remote syslog host** and **Syslot port number**. A network administrator or security administrator should be able to help you locate that information.</span></span> 

- <span data-ttu-id="6219c-144">Debe aceptar [los términos de licencia de software](https://go.microsoft.com/fwlink/?linkid=862491) descargar el [fichero JAR](https://go.microsoft.com/fwlink/?linkid=838596) que necesitará para integrar su servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="6219c-144">You must agree to [software license terms](https://go.microsoft.com/fwlink/?linkid=862491) to download the [JAR file](https://go.microsoft.com/fwlink/?linkid=838596) you'll need to integrate your SIEM server.</span></span>
 
## <a name="step-1-set-it-up-a-siem-agent-in-office-365-cloud-app-security"></a><span data-ttu-id="6219c-145">Paso 1: Lo configurar un agente de SIEM en seguridad de la aplicación de nube de Office 365</span><span class="sxs-lookup"><span data-stu-id="6219c-145">Step 1: Set it up a SIEM agent in Office 365 Cloud App Security</span></span>

1. <span data-ttu-id="6219c-p107">Vaya a [https://protection.office.com](https://protection.office.com) e iniciar sesión con su cuenta de trabajo o escuela para Office 365. (Esto le llevará a la seguridad &amp; centro de cumplimiento.)</span><span class="sxs-lookup"><span data-stu-id="6219c-p107">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="6219c-148">Vaya a **las alertas de** \> **avanzada de administrar las alertas**.</span><span class="sxs-lookup"><span data-stu-id="6219c-148">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="6219c-p108">Elija **Ir a la seguridad de la aplicación de Office 365 en la nube**.</span><span class="sxs-lookup"><span data-stu-id="6219c-p108">Choose **Go to Office 365 Cloud App Security**. </span></span><br/>
    <span data-ttu-id="6219c-150">![En la seguridad &amp; centro de cumplimiento, elija Administrar alertas avanzadas para ir a la seguridad de la aplicación de nube de Office 365](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="6219c-150">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span>
  
4. <span data-ttu-id="6219c-151">Haga clic en **configuración de** \> de **extensiones de seguridad**y, a continuación, elija los agentes SIEM.</span><span class="sxs-lookup"><span data-stu-id="6219c-151">Click **Settings** \> **Security extensions**, and then choose SIEM agents.</span></span><br/>
<span data-ttu-id="6219c-152">![Elija Configuración > extensiones de seguridad](media/Settings-SecurityExtensions.png)</span><span class="sxs-lookup"><span data-stu-id="6219c-152">![Choose Settings > Security extensions](media/Settings-SecurityExtensions.png)</span></span>

5. <span data-ttu-id="6219c-153">Elija **Agregar SIEM agente**.</span><span class="sxs-lookup"><span data-stu-id="6219c-153">Choose **Add SIEM agent**.</span></span><br/><span data-ttu-id="6219c-154">![Elija a agente SIEM agregar.](media/SIEMAgents.png)</span><span class="sxs-lookup"><span data-stu-id="6219c-154">![Choose Add SIEM agent.](media/SIEMAgents.png)</span></span>
    
6. <span data-ttu-id="6219c-155">Elija **iniciar el Asistente**.</span><span class="sxs-lookup"><span data-stu-id="6219c-155">Choose **Start wizard**.</span></span><br/><span data-ttu-id="6219c-156">![Obtener ayuda o iniciar el Asistente para](media/HelpOrWizard.png)</span><span class="sxs-lookup"><span data-stu-id="6219c-156">![Get help or start the wizard](media/HelpOrWizard.png)</span></span> 
    
7. <span data-ttu-id="6219c-p109">En el paso **General** , especifique un nombre y **Seleccione el formato SIEM** y establecer cualquier **Configuración avanzada** que son relevantes para ese formato. A continuación, elija **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6219c-p109">In the **General** step, specify a name, and **Select your SIEM format** and set any **Advanced settings** that are relevant to that format. Then choose **Next**.</span></span><br/><span data-ttu-id="6219c-159">![Especifique un nombre y tipo](media/ChooseAgentTypeAndName.png)</span><span class="sxs-lookup"><span data-stu-id="6219c-159">![Specify a name and type](media/ChooseAgentTypeAndName.png)</span></span>
    
8. <span data-ttu-id="6219c-p110">En el paso **Remoto de registro del sistema** , especifique la dirección IP o el nombre de host del **host remoto de registro del sistema** y el **número de puerto del registro del sistema**. Seleccione TCP o UDP como protocolo remoto registro del sistema. (Puede trabajar con el Administrador de seguridad o administrador de red para obtener estos detalles si no dispone de ellos). A continuación, elija **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6219c-p110">In the **Remote Syslog** step, specify the IP address or hostname of the **Remote syslog host** and the **Syslog port number**. Select TCP or UDP as the Remote Syslog protocol. (You can work with your network administrator or security administrator to get these details if you don't have them.) Then choose **Next**.</span></span><br/><span data-ttu-id="6219c-163">![Especificar detalles del registro del sistema remoto remoto](media/ArcSightS1Syslog.png)</span><span class="sxs-lookup"><span data-stu-id="6219c-163">![Specify Remote Syslog details](media/ArcSightS1Syslog.png)</span></span>
  
9. <span data-ttu-id="6219c-164">En el paso de **Tipos de datos** , siga uno de los siguientes procedimientos y, a continuación, haga clic en **siguiente**:</span><span class="sxs-lookup"><span data-stu-id="6219c-164">In the **Data Types** step, do one of the following, and then click **Next**:</span></span>
    - <span data-ttu-id="6219c-165">Conserve la configuración predeterminada de **Todas las alertas**</span><span class="sxs-lookup"><span data-stu-id="6219c-165">Keep the default setting of **All Alerts**</span></span><br/><span data-ttu-id="6219c-166">O BIEN</span><span class="sxs-lookup"><span data-stu-id="6219c-166">OR</span></span>
    - <span data-ttu-id="6219c-p111">Haga clic en **todas las alertas**y, a continuación, elija **filtros específicos**. Definir filtros para seleccionar los tipos de alertas que desea enviar a su servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="6219c-p111">Click **All alerts**, and then choose **Specific filters**. Define filters to select the kinds of alerts you want to send to your SIEM server. </span></span><br/><span data-ttu-id="6219c-169">![Paso de tipos de datos del Asistente](media/ArcSightS1ExportOptions.png)</span><span class="sxs-lookup"><span data-stu-id="6219c-169">![Data Types step of the wizard](media/ArcSightS1ExportOptions.png)</span></span>
  
10. <span data-ttu-id="6219c-170">En la pantalla Enhorabuena, copie el token y guardar para usarlo más adelante.</span><span class="sxs-lookup"><span data-stu-id="6219c-170">On the Congratulations screen, copy the token and save it for later.</span></span><br/>![Pantalla de agente creado SIEM](media/SIEMAgentFinished.png) 

> [!IMPORTANT]
> <span data-ttu-id="6219c-p112">En este punto, ha configurado un agente de SIEM en seguridad de la aplicación de Office 365 en la nube, pero aún no se han finalizado la integración del servidor de SIEM. Continúe con el paso siguiente para continuar la integración del servidor de SIEM.</span><span class="sxs-lookup"><span data-stu-id="6219c-p112">At this point, you have set up a SIEM agent in Office 365 Cloud App Security, but your SIEM server integration is not yet finished. Proceed to the next step to continue your SIEM server integration.</span></span>

<span data-ttu-id="6219c-p113">Una vez que haga clic en Cerrar y salir del asistente, en la pantalla de extensiones de seguridad, puede ver al agente de SIEM que agregó en la tabla. Se mostrará un estado **creado** hasta que se conecta más adelante.</span><span class="sxs-lookup"><span data-stu-id="6219c-p113">After you click Close and leave the wizard, on the Security extensions screen, you can see the SIEM agent you added in the table. It will show a status of **Created** until it's connected later.</span></span>

![Agente SIEM creado](media/SIEMAgentCreated.png)
    
## <a name="step-2-download-a-jar-file-and-run-it-on-your-siem-server"></a><span data-ttu-id="6219c-177">Paso 2: Descargar un archivo JAR y ejecutar en el servidor de SIEM</span><span class="sxs-lookup"><span data-stu-id="6219c-177">Step 2: Download a JAR file and run it on your SIEM server</span></span>

1. <span data-ttu-id="6219c-p114">Descargue el [Agente de SIEM de seguridad de aplicación de Microsoft en la nube](https://go.microsoft.com/fwlink/?linkid=838596) y descomprima la carpeta. (Debe aceptar los términos de [licencia](https://go.microsoft.com/fwlink/?linkid=862491) de software para poder continuar).</span><span class="sxs-lookup"><span data-stu-id="6219c-p114">Download the [Microsoft Cloud App Security SIEM Agent](https://go.microsoft.com/fwlink/?linkid=838596) and unzip the folder. (You must agree to [software license terms](https://go.microsoft.com/fwlink/?linkid=862491) in order to proceed.)</span></span> 
    
2. <span data-ttu-id="6219c-180">Extraiga el archivo .jar desde la carpeta zip y ejecutar en el servidor de SIEM.</span><span class="sxs-lookup"><span data-stu-id="6219c-180">Extract the .jar file from the zipped folder and run it on your SIEM server.</span></span>
    
3. <span data-ttu-id="6219c-181">Después de ejecutar el archivo, ejecute lo siguiente: comando:</span><span class="sxs-lookup"><span data-stu-id="6219c-181">After running the file, run the following: command:</span></span><br/>
  ```
  java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN
  ```
### <a name="important-notes"></a><span data-ttu-id="6219c-182">Notas importantes</span><span class="sxs-lookup"><span data-stu-id="6219c-182">Important notes</span></span>

- <span data-ttu-id="6219c-183">El nombre de archivo puede diferir dependiendo de la versión del agente SIEM.</span><span class="sxs-lookup"><span data-stu-id="6219c-183">The file name may differ depending on the version of the SIEM agent.</span></span> 

- <span data-ttu-id="6219c-184">Le recomendamos que ejecute el archivo JAR en el servidor de SIEM durante la instalación del servidor.</span><span class="sxs-lookup"><span data-stu-id="6219c-184">We recommend that you run the JAR file on your SIEM server during server setup.</span></span>

    - <span data-ttu-id="6219c-185">**Windows**: ejecute como una tarea programada, asegurándose de que se configure la tarea para **ejecutar si el usuario inició sesión como si no** y desactive la opción **Detener la tarea si se ejecuta más de** .</span><span class="sxs-lookup"><span data-stu-id="6219c-185">**Windows**: Run as a scheduled task, making sure to configure the task to **Run whether the user is logged on or not** and clear the **Stop the task if it runs longer than** option.</span></span>

    - <span data-ttu-id="6219c-186">**Linux**: agregar el comando ejecutar con un **&** a la `rc.local` archivo.</span><span class="sxs-lookup"><span data-stu-id="6219c-186">**Linux**: Add the run command with an **&** to the `rc.local` file.</span></span> <br/><span data-ttu-id="6219c-187">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6219c-187">Example:</span></span><br/> 
    ```
    java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN &
    ```

- <span data-ttu-id="6219c-p115">Parámetros entre corchetes [] son opcionales y deben usarse sólo si es relevante. Use las siguientes variables:</span><span class="sxs-lookup"><span data-stu-id="6219c-p115">Parameters in brackets [] are optional, and should be used only if relevant. Use the following variables:</span></span>

    - <span data-ttu-id="6219c-190">**DIRNAME** es la ruta de acceso al directorio que desea usar para los registros de depuración de agente local.</span><span class="sxs-lookup"><span data-stu-id="6219c-190">**DIRNAME** is the path to the directory you want to use for local agent debug logs.</span></span>

    - <span data-ttu-id="6219c-191">**Dirección [: puerto]** es la dirección del servidor proxy y el puerto que utiliza el servidor para conectarse a Internet.</span><span class="sxs-lookup"><span data-stu-id="6219c-191">**ADDRESS[:PORT]** is the proxy server address and port that the server uses to connect to the Internet.</span></span>

    - <span data-ttu-id="6219c-192">**Símbolo (token)** es el símbolo (token) de agente SIEM que se copió en el primer procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6219c-192">**TOKEN** is the SIEM agent token you copied in the first procedure.</span></span>

    - <span data-ttu-id="6219c-193">Para obtener ayuda, escriba `-h`.</span><span class="sxs-lookup"><span data-stu-id="6219c-193">To get help, type `-h`.</span></span> 
  
## <a name="step-3-validate-that-the-siem-agent-is-working"></a><span data-ttu-id="6219c-194">Paso 3: Validar que el agente de SIEM está funcionando</span><span class="sxs-lookup"><span data-stu-id="6219c-194">Step 3: Validate that the SIEM agent is working</span></span>

1. <span data-ttu-id="6219c-195">Asegúrese de que el estado del agente SIEM en el portal de seguridad de la aplicación de nube de Office 365 no se muestra como **error de conexión** o **desconectado** y que no hay ninguna notificación de agente.</span><span class="sxs-lookup"><span data-stu-id="6219c-195">Make sure the status of the SIEM agent in the Office 365 Cloud App Security portal is not displayed as **Connection error** or **Disconnected** and that there are no agent notifications.</span></span><br/><span data-ttu-id="6219c-196">Por ejemplo, aquí podemos ver que está conectado el servidor SIEM:</span><span class="sxs-lookup"><span data-stu-id="6219c-196">For example, here we can see the SIEM server is connected:</span></span><br/><span data-ttu-id="6219c-197">![Servidor SIEM conectado](media/siem-connected.png)</span><span class="sxs-lookup"><span data-stu-id="6219c-197">![SIEM server connected](media/siem-connected.png)</span></span><br/><span data-ttu-id="6219c-198">Y, a continuación, podemos ver que el servidor SIEM está desconectado:</span><span class="sxs-lookup"><span data-stu-id="6219c-198">And here, we can see the SIEM server is disconnected:</span></span><br/><span data-ttu-id="6219c-199">![Servidor SIEM no conectado](media/siem-not-connected.png)</span><span class="sxs-lookup"><span data-stu-id="6219c-199">![SIEM server not connected](media/siem-not-connected.png)</span></span> 
  
2. <span data-ttu-id="6219c-200">En el servidor de registro del sistema/SIEM, asegúrese de que vea que han llegado las alertas de seguridad de la aplicación de nube de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6219c-200">In your Syslog/SIEM server, make sure you see that alerts have arrived from Office 365 Cloud App Security.</span></span>
  
## <a name="what-the-logfiles-look-like"></a><span data-ttu-id="6219c-201">El aspecto de los archivos de registro</span><span class="sxs-lookup"><span data-stu-id="6219c-201">What the logfiles look like</span></span>

<span data-ttu-id="6219c-202">Este es un ejemplo de archivo de registro de alertas que es posible que se envíen a un servidor SIEM:</span><span class="sxs-lookup"><span data-stu-id="6219c-202">Here's an alerts logfile example that might be sent to a SIEM server:</span></span>

```
2017-07-15T20:42:30.531Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|myPolicy|3|externalId=596a7e360c204203a335a3fb start=1500151350531 end=1500151350531 msg=Activity policy ''myPolicy'' was triggered by ''admin@box-contoso.com'' suser=admin@box-contoso.com destinationServiceName=Box cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596a7e360c204203a335a3fb cs2Label=uniqueServiceAppIds cs2=APPID_BOX cs3Label=relatedAudits cs3=1500151288183_acc891bf-33e1-424b-a021-0d4370789660 cs4Label=policyIDs cs4=59f0ab82f797fa0681e9b1c7

2017-07-16T09:36:26.550Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b339b0c204203a33a51ae start=1500197786550 end=1500197786550 msg=Activity policy ''test-activity-policy'' was triggered by ''user@contoso.com'' suser=user@contoso.com destinationServiceName=Salesforce cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b339b0c204203a33a51ae cs2Label=uniqueServiceAppIds cs2=APPID_SALESFORCE cs3Label=relatedAudits cs3=1500197720691_b7f6317c-b8de-476a-bc8f-dfa570e00349 cs4Label=policyIDs cs4=

2017-07-16T09:17:03.361Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy3|3|externalId=596b2fd70c204203a33a3eeb start=1500196623361 end=1500196623361 msg=Activity policy ''test-activity-policy3'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Office 365 cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eeb cs2Label=uniqueServiceAppIds cs2=APPID_O365 cs3Label=relatedAudits cs3=1500196549157_a0e01f8a-e29a-43ae-8599-783c1c11597d cs4Label=policyIDs cs4=

2017-07-16T09:17:15.426Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b2fd70c204203a33a3eec start=1500196635426 end=1500196635426 msg=Activity policy ''test-activity-policy'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Office 365 admin center cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eec cs2Label=uniqueServiceAppIds cs2=APPID_O365_PORTAL cs3Label=relatedAudits cs3=1500196557398_3e102b20-d9fa-4f66-b550-8c7a403bb4d8 cs4Label=policyIDs cs4=59f0ab35f797fa9811e9b1c7

2017-07-16T09:17:46.290Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy4|3|externalId=596b30200c204203a33a4765 start=1500196666290 end=1500196666290 msg=Activity policy ''test-activity-policy4'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Exchange Online cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b30200c204203a33a4765 cs2Label=uniqueServiceAppIds cs2=APPID_OUTLOOK cs3Label=relatedAudits cs3=1500196587034_a8673602-7e95-46d6-a1fe-c156c4709c5d cs4Label=policyIDs cs4=

2017-07-16T09:41:04.369Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy2|3|externalId=596b34b10c204203a33a5240 start=1500198064369 end=1500198064369 msg=Activity policy ''test-activity-policy2'' was triggered by ''user2@test15-adallom.com'' suser=user2@test15-adallom.com destinationServiceName=Google cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b34b10c204203a33a5240 cs2Label=uniqueServiceAppIds cs2=APPID_33626 cs3Label=relatedAudits cs3=1500197996117_fd71f265-1e46-4f04-b372-2e32ec874cd3 cs4Label=policyIDs cs4=
```

<span data-ttu-id="6219c-203">Y aquí es otro ejemplo, esta vez en formato CEF:</span><span class="sxs-lookup"><span data-stu-id="6219c-203">And here's another sample, this time in CEF format:</span></span>


|<span data-ttu-id="6219c-204">Nombre del campo CEF</span><span class="sxs-lookup"><span data-stu-id="6219c-204">CEF field name</span></span>  | <span data-ttu-id="6219c-205">Descripción</span><span class="sxs-lookup"><span data-stu-id="6219c-205">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="6219c-206">Inicio</span><span class="sxs-lookup"><span data-stu-id="6219c-206">start</span></span>     | <span data-ttu-id="6219c-207">marca de tiempo de alerta</span><span class="sxs-lookup"><span data-stu-id="6219c-207">alert timestamp</span></span>        |
|<span data-ttu-id="6219c-208">end</span><span class="sxs-lookup"><span data-stu-id="6219c-208">end</span></span>     | <span data-ttu-id="6219c-209">marca de tiempo de alerta</span><span class="sxs-lookup"><span data-stu-id="6219c-209">alert timestamp</span></span>        |
|<span data-ttu-id="6219c-210">RT</span><span class="sxs-lookup"><span data-stu-id="6219c-210">rt</span></span>     | <span data-ttu-id="6219c-211">marca de tiempo de alerta</span><span class="sxs-lookup"><span data-stu-id="6219c-211">alert timestamp</span></span>        |
|<span data-ttu-id="6219c-212">msg</span><span class="sxs-lookup"><span data-stu-id="6219c-212">msg</span></span>     | <span data-ttu-id="6219c-213">Descripción de la alerta tal como se muestra en el portal de seguridad de la aplicación de nube de Office 365</span><span class="sxs-lookup"><span data-stu-id="6219c-213">alert description as shown in the Office 365 Cloud App Security portal</span></span>        |
|<span data-ttu-id="6219c-214">suser se</span><span class="sxs-lookup"><span data-stu-id="6219c-214">suser</span></span>     | <span data-ttu-id="6219c-215">usuario de asunto de alerta</span><span class="sxs-lookup"><span data-stu-id="6219c-215">alert subject user</span></span>        |
|<span data-ttu-id="6219c-216">destinationServiceName</span><span class="sxs-lookup"><span data-stu-id="6219c-216">destinationServiceName</span></span>     | <span data-ttu-id="6219c-217">alerta de que se originan aplicación, como Office 365, SharePoint o OneDrive</span><span class="sxs-lookup"><span data-stu-id="6219c-217">alert originating app, such as Office 365, SharePoint, or OneDrive</span></span>        |
|<span data-ttu-id="6219c-218">csLabel</span><span class="sxs-lookup"><span data-stu-id="6219c-218">csLabel</span></span>     | <span data-ttu-id="6219c-p116">Varía (etiquetas tengan diferentes significados). Normalmente, las etiquetas son explican por sí solos, al igual que targetObjects.</span><span class="sxs-lookup"><span data-stu-id="6219c-p116">Varies (labels have different meanings). Typically, labels are self-explanatory, like targetObjects.</span></span>        |
|<span data-ttu-id="6219c-221">cs</span><span class="sxs-lookup"><span data-stu-id="6219c-221">cs</span></span>     | <span data-ttu-id="6219c-222">Información correspondiente a una etiqueta (por ejemplo, el usuario de destino de una alerta de acuerdo con el ejemplo de etiqueta)</span><span class="sxs-lookup"><span data-stu-id="6219c-222">Information corresponding to a label (such as the target user of an alert as per the label example)</span></span>        |

## <a name="additional-tasks-as-needed"></a><span data-ttu-id="6219c-223">Tareas adicionales (según sea necesario)</span><span class="sxs-lookup"><span data-stu-id="6219c-223">Additional tasks (as needed)</span></span>

<span data-ttu-id="6219c-p117">Una vez que se ha configurado el servidor SIEM y se la integrado con la seguridad de la aplicación de nube de Office 365, es posible que necesite regenerar un token, editar a un agente de SIEM o eliminación de un agente de SIEM. Las secciones siguientes describen cómo realizar estas tareas.</span><span class="sxs-lookup"><span data-stu-id="6219c-p117">After you have configured your SIEM server and have integrated it with Office 365 Cloud App Security, you might need to regenerate a token, edit a SIEM agent, or delete a SIEM agent. The following sections describe how to perform these tasks.</span></span>

### <a name="regenerate-a-token"></a><span data-ttu-id="6219c-226">Vuelva a generar un símbolo (token)</span><span class="sxs-lookup"><span data-stu-id="6219c-226">Regenerate a token</span></span>

<span data-ttu-id="6219c-227">Si se pierde su token, puede volver a generar uno.</span><span class="sxs-lookup"><span data-stu-id="6219c-227">If you lose your token, you can regenerate one.</span></span> 

1. <span data-ttu-id="6219c-228">En el portal de seguridad de la aplicación de nube de Office 365, elija **configuración** > **extensiones de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="6219c-228">In the Office 365 Cloud App Security portal, choose **Settings** > **Security extensions**.</span></span>

2. <span data-ttu-id="6219c-229">En la tabla, busque la fila para el agente de SIEM.</span><span class="sxs-lookup"><span data-stu-id="6219c-229">In the table, locate the row for the SIEM agent.</span></span> 

3. <span data-ttu-id="6219c-230">Haga clic en los puntos suspensivos y elija, a continuación, **vuelva a generar el símbolo (token)**.</span><span class="sxs-lookup"><span data-stu-id="6219c-230">Click the ellipses, and then choose **Regenerate token**.</span></span><br/><span data-ttu-id="6219c-231">![Vuelva a generar un token al hacer clic en el botón de puntos suspensivos para el agente de SIEM](media/04de368a-b88e-4a9c-a830-58025cb98db6.png)</span><span class="sxs-lookup"><span data-stu-id="6219c-231">![Regenerate a token by clicking the ellipsis for your SIEM agent](media/04de368a-b88e-4a9c-a830-58025cb98db6.png)</span></span>
  
### <a name="edit-a-siem-agent"></a><span data-ttu-id="6219c-232">Editar a un agente de SIEM</span><span class="sxs-lookup"><span data-stu-id="6219c-232">Edit a SIEM agent</span></span>

1. <span data-ttu-id="6219c-233">En el portal de seguridad de la aplicación de nube de Office 365, elija **configuración** > **extensiones de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="6219c-233">In the Office 365 Cloud App Security portal, choose **Settings** > **Security extensions**.</span></span>

2. <span data-ttu-id="6219c-234">Busque la fila para el agente de SIEM.</span><span class="sxs-lookup"><span data-stu-id="6219c-234">Locate the row for the SIEM agent.</span></span> 

3. <span data-ttu-id="6219c-p118">Haga clic en los puntos suspensivos y, a continuación, elija **Editar**. (Si se edita al agente de SIEM, no es necesario volver a ejecutar el archivo .jar; actualiza automáticamente.)</span><span class="sxs-lookup"><span data-stu-id="6219c-p118">Click the ellipses, and then choose **Edit**. (If you edit the SIEM agent, you do not need to re-run the .jar file; it updates automatically.) </span></span><br/><span data-ttu-id="6219c-237">![Para editar a su agente SIEM, elija los puntos suspensivos y, a continuación, elija Editar.](media/96d0b362-3e0c-4dff-b2b4-d7af5b1bfb91.png)</span><span class="sxs-lookup"><span data-stu-id="6219c-237">![To edit your SIEM agent, choose the ellipses, and then choose Edit.](media/96d0b362-3e0c-4dff-b2b4-d7af5b1bfb91.png)</span></span>
  
### <a name="delete-a-siem-agent"></a><span data-ttu-id="6219c-238">Eliminar a un agente de SIEM</span><span class="sxs-lookup"><span data-stu-id="6219c-238">Delete a SIEM agent</span></span>

1. <span data-ttu-id="6219c-239">En el portal de seguridad de la aplicación de nube de Office 365, elija **configuración** > **extensiones de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="6219c-239">In the Office 365 Cloud App Security portal, choose **Settings** > **Security extensions**.</span></span>

2. <span data-ttu-id="6219c-240">Busque la fila para el agente de SIEM.</span><span class="sxs-lookup"><span data-stu-id="6219c-240">Locate the row for the SIEM agent.</span></span> 

3. <span data-ttu-id="6219c-241">Haga clic en los puntos suspensivos y, a continuación, elija **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="6219c-241">Click the ellipses, and then choose **Delete**.</span></span><br/><span data-ttu-id="6219c-242">![Para eliminar a un agente de SIEM, elija los puntos suspensivos y, a continuación, elija Eliminar.](media/540b5bdf-5574-4ecc-a7b0-92a499a387d7.png)</span><span class="sxs-lookup"><span data-stu-id="6219c-242">![To delete a SIEM agent, choose the ellipses, and then choose Delete.](media/540b5bdf-5574-4ecc-a7b0-92a499a387d7.png)</span></span>

  
## <a name="next-steps"></a><span data-ttu-id="6219c-243">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6219c-243">Next steps</span></span>

- [<span data-ttu-id="6219c-244">Actividades de uso después de implementar Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6219c-244">Utilization activities after rolling out Office 365 Cloud App Security</span></span>](utilization-activities-for-ocas.md)
    
- [<span data-ttu-id="6219c-245">Revisar y realizar acciones en las alertas</span><span class="sxs-lookup"><span data-stu-id="6219c-245">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="6219c-246">Las direcciones IP para simplificar la administración de grupo</span><span class="sxs-lookup"><span data-stu-id="6219c-246">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    


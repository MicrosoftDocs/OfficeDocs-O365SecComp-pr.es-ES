---
title: Integrar el servidor SIEM con Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: dd6d2417-49c4-4de6-9294-67fdabbf8532
description: Puede integrar su servidor de SIEM con Office 365 Cloud App Security. Lea este artículo para obtener información general sobre cómo funciona y cómo configurarlo.
ms.openlocfilehash: 82b5e0e6467bd42acba3c40d67e4e0363a7e0f72
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254818"
---
# <a name="integrate-your-siem-server-with-office-365-cloud-app-security"></a><span data-ttu-id="c0a81-104">Integrar el servidor SIEM con Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c0a81-104">Integrate your SIEM server with Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="c0a81-105">Evaluación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="c0a81-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="c0a81-106">Planeación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="c0a81-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="c0a81-107">Implementación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="c0a81-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="c0a81-108">Uso \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="c0a81-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="c0a81-109">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="c0a81-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="c0a81-110">Empezar a planear</span><span class="sxs-lookup"><span data-stu-id="c0a81-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="c0a81-111">Ya está aquí.</span><span class="sxs-lookup"><span data-stu-id="c0a81-111">You are here!</span></span>  <br/> [<span data-ttu-id="c0a81-112">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="c0a81-112">Next step</span></span>](utilization-activities-for-ocas.md) <br/> |[<span data-ttu-id="c0a81-113">Empezar a usar</span><span class="sxs-lookup"><span data-stu-id="c0a81-113">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
## <a name="overview-and-prerequisites"></a><span data-ttu-id="c0a81-114">Información general y requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c0a81-114">Overview and prerequisites</span></span>

<span data-ttu-id="c0a81-115">Puede integrar [Office 365 Cloud App Security](get-ready-for-office-365-cas.md) con su servidor de administración de eventos e información de seguridad (Siem) para habilitar el control centralizado de las alertas.</span><span class="sxs-lookup"><span data-stu-id="c0a81-115">You can integrate [Office 365 Cloud App Security](get-ready-for-office-365-cas.md) with your security information and event management (SIEM) server to enable centralized monitoring of alerts.</span></span> <span data-ttu-id="c0a81-116">Esto es especialmente ventajoso para las organizaciones que usan servicios en la nube y aplicaciones de servidor local.</span><span class="sxs-lookup"><span data-stu-id="c0a81-116">This is especially beneficial for organizations who are using cloud services and on-premises server applications.</span></span> <span data-ttu-id="c0a81-117">Puede integrar el servidor de SIEM para extraer alertas y actividades de la seguridad de aplicaciones en la nube de Office 365 en el servidor de SIEM.</span><span class="sxs-lookup"><span data-stu-id="c0a81-117">You can integrate your SIEM server to pull alerts and activities from Office 365 Cloud App Security into your SIEM server.</span></span> <span data-ttu-id="c0a81-118">La integración con un servidor de SIEM permite que su equipo de seguridad Proteja mejor sus aplicaciones de Office 365 a la vez que mantiene un flujo de trabajo de seguridad usual mediante la automatización de determinados procedimientos de seguridad y la correlación entre eventos locales y basados en la nube.</span><span class="sxs-lookup"><span data-stu-id="c0a81-118">Integrating with a SIEM server allows your security team to better protect your Office 365 applications while maintaining your usual security workflow, by automating certain security procedures and correlating between cloud-based and on-premises events.</span></span>  
  
<span data-ttu-id="c0a81-119">Cuando integre por primera vez su servidor de SIEM con Office 365 Cloud App Security, las alertas de los dos últimos días se reenvían al servidor de SIEM, así como todas las alertas desde entonces, según los filtros que seleccione.</span><span class="sxs-lookup"><span data-stu-id="c0a81-119">When you first integrate your SIEM server with Office 365 Cloud App Security, alerts from the last two days are forwarded to the SIEM server, as well as all alerts from then on (based on any filters you select).</span></span> <span data-ttu-id="c0a81-120">Además, si deshabilita esta característica durante un período prolongado, cuando vuelva a habilitarla, reenviará los últimos dos días de alertas y, a continuación, todas las alertas desde entonces.</span><span class="sxs-lookup"><span data-stu-id="c0a81-120">Additionally, if you disable this feature for an extended period, when you enable it again, it will forward the past two days of alerts and then all alerts from then on.</span></span>

### <a name="siem-integration-architecture"></a><span data-ttu-id="c0a81-121">Arquitectura de integración de SIEM</span><span class="sxs-lookup"><span data-stu-id="c0a81-121">SIEM integration architecture</span></span>

<span data-ttu-id="c0a81-122">Un agente de SIEM se configura en la red de la organización.</span><span class="sxs-lookup"><span data-stu-id="c0a81-122">A SIEM agent is set up in your organization's network.</span></span> <span data-ttu-id="c0a81-123">Cuando se implementa y configura, el agente de SIEM extrae los tipos de datos que se configuraron (alertas) con las API RESTful de seguridad de aplicación de nube de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c0a81-123">When deployed and configured, the SIEM agent pulls the data types that were configured (alerts) using Office 365 Cloud App Security RESTful APIs.</span></span> <span data-ttu-id="c0a81-124">A continuación, el tráfico se envía a través de un canal HTTPS cifrado en el puerto 443.</span><span class="sxs-lookup"><span data-stu-id="c0a81-124">The traffic is then sent over an encrypted HTTPS channel on port 443.</span></span>
  
<span data-ttu-id="c0a81-125">Cuando un agente de SIEM recupera datos de la seguridad de aplicación de nube de Office 365, envía los mensajes de syslog a su servidor de SIEM local mediante las configuraciones de red que se proporcionan durante la instalación (TCP o UDP con un puerto personalizado).</span><span class="sxs-lookup"><span data-stu-id="c0a81-125">When a SIEM agent retrieves data from Office 365 Cloud App Security, it sends the Syslog messages to your local SIEM server using the network configurations that are provided during setup (TCP or UDP with a custom port).</span></span>

![Arquitectura de seguridad de aplicaciones de SIEM y nube](media/siem-architecture.png)

### <a name="supported-siem-servers"></a><span data-ttu-id="c0a81-127">Servidores SIEM admitidos</span><span class="sxs-lookup"><span data-stu-id="c0a81-127">Supported SIEM servers</span></span>

<span data-ttu-id="c0a81-128">Office 365 Cloud App Security es compatible actualmente con los siguientes servidores SIEM:</span><span class="sxs-lookup"><span data-stu-id="c0a81-128">Office 365 Cloud App Security currently supports the following SIEM servers:</span></span>
- <span data-ttu-id="c0a81-129">ArcSight de micro Focus</span><span class="sxs-lookup"><span data-stu-id="c0a81-129">Micro Focus ArcSight</span></span>
- <span data-ttu-id="c0a81-130">CEF genérico</span><span class="sxs-lookup"><span data-stu-id="c0a81-130">Generic CEF</span></span>

### <a name="prerequisites"></a><span data-ttu-id="c0a81-131">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c0a81-131">Prerequisites</span></span>

- <span data-ttu-id="c0a81-132">Debe ser administrador global o administrador de seguridad para realizar las tareas descritas en este artículo.</span><span class="sxs-lookup"><span data-stu-id="c0a81-132">You must be a global administrator or security administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="c0a81-133">Consulte [permisos en el centro de seguridad &amp; y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="c0a81-133">See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)</span></span>

- <span data-ttu-id="c0a81-134">Debe tener habilitada la [seguridad de aplicación de nube de Office 365](turn-on-office-365-cas.md) para su organización.</span><span class="sxs-lookup"><span data-stu-id="c0a81-134">You must have [Office 365 Cloud App Security enabled](turn-on-office-365-cas.md) for your organization.</span></span>

- <span data-ttu-id="c0a81-135">El [registro de auditoría](turn-audit-log-search-on-or-off.md) debe estar activado para Office 365</span><span class="sxs-lookup"><span data-stu-id="c0a81-135">[Audit logging](turn-audit-log-search-on-or-off.md) must be turned on for Office 365</span></span>

- <span data-ttu-id="c0a81-136">Debe tener un servidor estándar que cumpla los siguientes requisitos para configurar la integración del servidor SIEM:</span><span class="sxs-lookup"><span data-stu-id="c0a81-136">You must have a standard server that meets the following requirements in order to configure SIEM server integration:</span></span>
    - <span data-ttu-id="c0a81-137">SO: Windows o Linux (puede ser una máquina virtual)</span><span class="sxs-lookup"><span data-stu-id="c0a81-137">OS: Windows or Linux (this can be a virtual machine)</span></span>
    - <span data-ttu-id="c0a81-138">CPU: 2</span><span class="sxs-lookup"><span data-stu-id="c0a81-138">CPU: 2</span></span>
    - <span data-ttu-id="c0a81-139">Espacio en disco: 20 GB</span><span class="sxs-lookup"><span data-stu-id="c0a81-139">Disk space: 20 GB</span></span>
    - <span data-ttu-id="c0a81-140">RAM: 2 GB</span><span class="sxs-lookup"><span data-stu-id="c0a81-140">RAM: 2 GB</span></span>
    - <span data-ttu-id="c0a81-141">[Java 8 de Oracle](http://www.oracle.com/technetwork/java/javase/downloads/index.html) instalado</span><span class="sxs-lookup"><span data-stu-id="c0a81-141">[Oracle Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html) installed</span></span>
    - <span data-ttu-id="c0a81-142">Firewall configurado como se describe en [requisitos de red](https://docs.microsoft.com/cloud-app-security/network-requirements)</span><span class="sxs-lookup"><span data-stu-id="c0a81-142">Firewall configured as described in [Network requirements](https://docs.microsoft.com/cloud-app-security/network-requirements)</span></span>

- <span data-ttu-id="c0a81-143">Debe tener detalles sobre el **host syslog remoto** y el **número de Puerto Syslot**.</span><span class="sxs-lookup"><span data-stu-id="c0a81-143">You must have details about your **Remote syslog host** and **Syslot port number**.</span></span> <span data-ttu-id="c0a81-144">Un administrador de red o un administrador de seguridad debe poder ayudarle a encontrar esa información.</span><span class="sxs-lookup"><span data-stu-id="c0a81-144">A network administrator or security administrator should be able to help you locate that information.</span></span> 

- <span data-ttu-id="c0a81-145">Debe aceptar los términos de la [licencia de software](https://go.microsoft.com/fwlink/?linkid=862491) para descargar el [archivo jar](https://go.microsoft.com/fwlink/?linkid=838596) que necesitará para integrar su servidor de Siem.</span><span class="sxs-lookup"><span data-stu-id="c0a81-145">You must agree to [software license terms](https://go.microsoft.com/fwlink/?linkid=862491) to download the [JAR file](https://go.microsoft.com/fwlink/?linkid=838596) you'll need to integrate your SIEM server.</span></span>
 
## <a name="step-1-set-it-up-a-siem-agent-in-office-365-cloud-app-security"></a><span data-ttu-id="c0a81-146">Paso 1: configurar un agente de SIEM en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c0a81-146">Step 1: Set it up a SIEM agent in Office 365 Cloud App Security</span></span>

1. <span data-ttu-id="c0a81-147">Vaya al portal de Cloud App Security ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="c0a81-147">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="c0a81-148">Haga clic en **configuración** \> de **extensiones de seguridad**y elija agentes de Siem.</span><span class="sxs-lookup"><span data-stu-id="c0a81-148">Click **Settings** \> **Security extensions**, and then choose SIEM agents.</span></span><br/>
<span data-ttu-id="c0a81-149">![Elija Configuración > extensiones de seguridad](media/Settings-SecurityExtensions.png)</span><span class="sxs-lookup"><span data-stu-id="c0a81-149">![Choose Settings > Security extensions](media/Settings-SecurityExtensions.png)</span></span>

3. <span data-ttu-id="c0a81-150">Elija **Agregar agente Siem**.</span><span class="sxs-lookup"><span data-stu-id="c0a81-150">Choose **Add SIEM agent**.</span></span><br/><span data-ttu-id="c0a81-151">![Elija Agregar agente SIEM.](media/SIEMAgents.png)</span><span class="sxs-lookup"><span data-stu-id="c0a81-151">![Choose Add SIEM agent.](media/SIEMAgents.png)</span></span>
    
4. <span data-ttu-id="c0a81-152">Elija **iniciar asistente**.</span><span class="sxs-lookup"><span data-stu-id="c0a81-152">Choose **Start wizard**.</span></span><br/><span data-ttu-id="c0a81-153">![Obtener ayuda o iniciar el asistente](media/HelpOrWizard.png)</span><span class="sxs-lookup"><span data-stu-id="c0a81-153">![Get help or start the wizard](media/HelpOrWizard.png)</span></span> 
    
5. <span data-ttu-id="c0a81-154">En el paso **General** , especifique un nombre y **Seleccione el formato Siem** y establezca la **Configuración avanzada** que sea relevante para ese formato.</span><span class="sxs-lookup"><span data-stu-id="c0a81-154">In the **General** step, specify a name, and **Select your SIEM format** and set any **Advanced settings** that are relevant to that format.</span></span> <span data-ttu-id="c0a81-155">A continuación, elija **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c0a81-155">Then choose **Next**.</span></span><br/><span data-ttu-id="c0a81-156">![Especificar un nombre y un tipo](media/ChooseAgentTypeAndName.png)</span><span class="sxs-lookup"><span data-stu-id="c0a81-156">![Specify a name and type](media/ChooseAgentTypeAndName.png)</span></span>
    
6. <span data-ttu-id="c0a81-157">En el paso **remoto de syslog** , especifique la dirección IP o el nombre de host del host de **syslog remoto** y el **número de Puerto syslog**.</span><span class="sxs-lookup"><span data-stu-id="c0a81-157">In the **Remote Syslog** step, specify the IP address or hostname of the **Remote syslog host** and the **Syslog port number**.</span></span> <span data-ttu-id="c0a81-158">Seleccione TCP o UDP como protocolo syslog remoto.</span><span class="sxs-lookup"><span data-stu-id="c0a81-158">Select TCP or UDP as the Remote Syslog protocol.</span></span> <span data-ttu-id="c0a81-159">(Puede trabajar con el administrador de la red o con el administrador de seguridad para obtener estos detalles si no los tiene). A continuación, elija **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c0a81-159">(You can work with your network administrator or security administrator to get these details if you don't have them.) Then choose **Next**.</span></span><br/><span data-ttu-id="c0a81-160">![Especificar detalles de registro de registro remoto](media/ArcSightS1Syslog.png)</span><span class="sxs-lookup"><span data-stu-id="c0a81-160">![Specify Remote Syslog details](media/ArcSightS1Syslog.png)</span></span>
  
7. <span data-ttu-id="c0a81-161">En el paso **tipos de datos** , realice una de las acciones siguientes y, a continuación, haga clic en **siguiente**:</span><span class="sxs-lookup"><span data-stu-id="c0a81-161">In the **Data Types** step, do one of the following, and then click **Next**:</span></span>
    - <span data-ttu-id="c0a81-162">Mantener la configuración predeterminada de **todas las alertas**</span><span class="sxs-lookup"><span data-stu-id="c0a81-162">Keep the default setting of **All Alerts**</span></span><br/><span data-ttu-id="c0a81-163">O</span><span class="sxs-lookup"><span data-stu-id="c0a81-163">OR</span></span>
    - <span data-ttu-id="c0a81-164">Haga clic en **todas las alertas**y, a continuación, elija **filtros específicos**.</span><span class="sxs-lookup"><span data-stu-id="c0a81-164">Click **All alerts**, and then choose **Specific filters**.</span></span> <span data-ttu-id="c0a81-165">Defina filtros para seleccionar los tipos de alertas que desea enviar a su servidor de SIEM.</span><span class="sxs-lookup"><span data-stu-id="c0a81-165">Define filters to select the kinds of alerts you want to send to your SIEM server.</span></span>
<br/><span data-ttu-id="c0a81-166">![Tipo de datos paso del asistente](media/ArcSightS1ExportOptions.png)</span><span class="sxs-lookup"><span data-stu-id="c0a81-166">![Data Types step of the wizard](media/ArcSightS1ExportOptions.png)</span></span>
  
8. <span data-ttu-id="c0a81-167">En la pantalla Enhorabuena, copie el token y guárdelo para más tarde.</span><span class="sxs-lookup"><span data-stu-id="c0a81-167">On the Congratulations screen, copy the token and save it for later.</span></span><br/>![Pantalla del agente de SIEM creada](media/SIEMAgentFinished.png) 

> [!IMPORTANT]
> <span data-ttu-id="c0a81-169">En este punto, ha configurado un agente de SIEM en Office 365 Cloud App Security, pero la integración del servidor SIEM todavía no ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="c0a81-169">At this point, you have set up a SIEM agent in Office 365 Cloud App Security, but your SIEM server integration is not yet finished.</span></span> <span data-ttu-id="c0a81-170">Continúe con el paso siguiente para continuar con la integración del servidor de SIEM.</span><span class="sxs-lookup"><span data-stu-id="c0a81-170">Proceed to the next step to continue your SIEM server integration.</span></span>

<span data-ttu-id="c0a81-171">Después de hacer clic en cerrar y salir del asistente, en la pantalla extensiones de seguridad, puede ver el agente de SIEM que agregó en la tabla.</span><span class="sxs-lookup"><span data-stu-id="c0a81-171">After you click Close and leave the wizard, on the Security extensions screen, you can see the SIEM agent you added in the table.</span></span> <span data-ttu-id="c0a81-172">Mostrará el estado **creado** hasta que se conecte más adelante.</span><span class="sxs-lookup"><span data-stu-id="c0a81-172">It will show a status of **Created** until it's connected later.</span></span>

![Agente de SIEM creado](media/SIEMAgentCreated.png)
    
## <a name="step-2-download-a-jar-file-and-run-it-on-your-siem-server"></a><span data-ttu-id="c0a81-174">Paso 2: descargar un archivo JAR y ejecutarlo en el servidor de SIEM</span><span class="sxs-lookup"><span data-stu-id="c0a81-174">Step 2: Download a JAR file and run it on your SIEM server</span></span>

1. <span data-ttu-id="c0a81-175">Descargue el [agente de Siem de Microsoft Cloud App Security](https://go.microsoft.com/fwlink/?linkid=838596) y descomprima la carpeta.</span><span class="sxs-lookup"><span data-stu-id="c0a81-175">Download the [Microsoft Cloud App Security SIEM Agent](https://go.microsoft.com/fwlink/?linkid=838596) and unzip the folder.</span></span> <span data-ttu-id="c0a81-176">(Debe aceptar los [términos de licencia del software](https://go.microsoft.com/fwlink/?linkid=862491) para poder continuar).</span><span class="sxs-lookup"><span data-stu-id="c0a81-176">(You must agree to [software license terms](https://go.microsoft.com/fwlink/?linkid=862491) in order to proceed.)</span></span> 
    
2. <span data-ttu-id="c0a81-177">Extraiga el archivo. jar de la carpeta ZIP y ejecútelo en el servidor de SIEM.</span><span class="sxs-lookup"><span data-stu-id="c0a81-177">Extract the .jar file from the zipped folder and run it on your SIEM server.</span></span>
    
3. <span data-ttu-id="c0a81-178">Después de ejecutar el archivo, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="c0a81-178">After running the file, run the following: command:</span></span><br/>
  ```
  java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN
  ```
### <a name="important-notes"></a><span data-ttu-id="c0a81-179">Notas importantes</span><span class="sxs-lookup"><span data-stu-id="c0a81-179">Important notes</span></span>

- <span data-ttu-id="c0a81-180">El nombre de archivo puede variar en función de la versión del agente de SIEM.</span><span class="sxs-lookup"><span data-stu-id="c0a81-180">The file name may differ depending on the version of the SIEM agent.</span></span> 

- <span data-ttu-id="c0a81-181">Le recomendamos que ejecute el archivo JAR en el servidor de SIEM durante la configuración del servidor.</span><span class="sxs-lookup"><span data-stu-id="c0a81-181">We recommend that you run the JAR file on your SIEM server during server setup.</span></span>

    - <span data-ttu-id="c0a81-182">**Windows**: ejecutar como tarea programada, asegurándose de configurar la tarea para que **se ejecute tanto si el usuario inició sesión como si no** y borre la opción **detener la tarea si se ejecuta durante más de** .</span><span class="sxs-lookup"><span data-stu-id="c0a81-182">**Windows**: Run as a scheduled task, making sure to configure the task to **Run whether the user is logged on or not** and clear the **Stop the task if it runs longer than** option.</span></span>

    - <span data-ttu-id="c0a81-183">**Linux**: agregue el comando ejecutar con un **&** al `rc.local` archivo.</span><span class="sxs-lookup"><span data-stu-id="c0a81-183">**Linux**: Add the run command with an **&** to the `rc.local` file.</span></span> <br/><span data-ttu-id="c0a81-184">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c0a81-184">Example:</span></span><br/> 
    ```
    java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN &
    ```

- <span data-ttu-id="c0a81-185">Los parámetros entre corchetes [] son opcionales y solo deben usarse si proceden.</span><span class="sxs-lookup"><span data-stu-id="c0a81-185">Parameters in brackets [] are optional, and should be used only if relevant.</span></span> <span data-ttu-id="c0a81-186">Use las siguientes variables:</span><span class="sxs-lookup"><span data-stu-id="c0a81-186">Use the following variables:</span></span>

    - <span data-ttu-id="c0a81-187">**DIRNAME** es la ruta de acceso al directorio que desea usar para los registros de depuración del agente local.</span><span class="sxs-lookup"><span data-stu-id="c0a81-187">**DIRNAME** is the path to the directory you want to use for local agent debug logs.</span></span>

    - <span data-ttu-id="c0a81-188">**Address [:P ORT]** es la dirección del servidor proxy y el puerto que usa el servidor para conectarse a Internet.</span><span class="sxs-lookup"><span data-stu-id="c0a81-188">**ADDRESS[:PORT]** is the proxy server address and port that the server uses to connect to the Internet.</span></span>

    - <span data-ttu-id="c0a81-189">**Token** es el token del agente Siem que copió en el primer procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c0a81-189">**TOKEN** is the SIEM agent token you copied in the first procedure.</span></span>

    - <span data-ttu-id="c0a81-190">Para obtener ayuda, escriba `-h`.</span><span class="sxs-lookup"><span data-stu-id="c0a81-190">To get help, type `-h`.</span></span> 
  
## <a name="step-3-validate-that-the-siem-agent-is-working"></a><span data-ttu-id="c0a81-191">Paso 3: validar que el agente de SIEM funcione</span><span class="sxs-lookup"><span data-stu-id="c0a81-191">Step 3: Validate that the SIEM agent is working</span></span>

1. <span data-ttu-id="c0a81-192">Asegúrese de que el estado del agente de SIEM del portal de seguridad de aplicaciones de nube de Office 365 no se muestra como **error de conexión** o desconectado y de que no hay notificaciones de agente. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c0a81-192">Make sure the status of the SIEM agent in the Office 365 Cloud App Security portal is not displayed as **Connection error** or **Disconnected** and that there are no agent notifications.</span></span><br/><span data-ttu-id="c0a81-193">Por ejemplo, aquí podemos ver que el servidor de SIEM está conectado:</span><span class="sxs-lookup"><span data-stu-id="c0a81-193">For example, here we can see the SIEM server is connected:</span></span><br/><span data-ttu-id="c0a81-194">![Servidor de SIEM conectado](media/siem-connected.png)</span><span class="sxs-lookup"><span data-stu-id="c0a81-194">![SIEM server connected](media/siem-connected.png)</span></span><br/><span data-ttu-id="c0a81-195">Y aquí podemos ver que el servidor de SIEM está desconectado:</span><span class="sxs-lookup"><span data-stu-id="c0a81-195">And here, we can see the SIEM server is disconnected:</span></span><br/><span data-ttu-id="c0a81-196">![Servidor de SIEM no conectado](media/siem-not-connected.png)</span><span class="sxs-lookup"><span data-stu-id="c0a81-196">![SIEM server not connected](media/siem-not-connected.png)</span></span> 
  
2. <span data-ttu-id="c0a81-197">En el servidor syslog/SIEM, asegúrese de que se ve que las alertas han llegado desde Office 365 Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="c0a81-197">In your Syslog/SIEM server, make sure you see that alerts have arrived from Office 365 Cloud App Security.</span></span>
  
## <a name="what-the-logfiles-look-like"></a><span data-ttu-id="c0a81-198">Aspecto de los archivos de registro</span><span class="sxs-lookup"><span data-stu-id="c0a81-198">What the logfiles look like</span></span>

<span data-ttu-id="c0a81-199">Este es un ejemplo de archivo de registro de alertas que podría enviarse a un servidor de SIEM:</span><span class="sxs-lookup"><span data-stu-id="c0a81-199">Here's an alerts logfile example that might be sent to a SIEM server:</span></span>

```
2017-07-15T20:42:30.531Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|myPolicy|3|externalId=596a7e360c204203a335a3fb start=1500151350531 end=1500151350531 msg=Activity policy ''myPolicy'' was triggered by ''admin@box-contoso.com'' suser=admin@box-contoso.com destinationServiceName=Box cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596a7e360c204203a335a3fb cs2Label=uniqueServiceAppIds cs2=APPID_BOX cs3Label=relatedAudits cs3=1500151288183_acc891bf-33e1-424b-a021-0d4370789660 cs4Label=policyIDs cs4=59f0ab82f797fa0681e9b1c7

2017-07-16T09:36:26.550Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b339b0c204203a33a51ae start=1500197786550 end=1500197786550 msg=Activity policy ''test-activity-policy'' was triggered by ''user@contoso.com'' suser=user@contoso.com destinationServiceName=Salesforce cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b339b0c204203a33a51ae cs2Label=uniqueServiceAppIds cs2=APPID_SALESFORCE cs3Label=relatedAudits cs3=1500197720691_b7f6317c-b8de-476a-bc8f-dfa570e00349 cs4Label=policyIDs cs4=

2017-07-16T09:17:03.361Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy3|3|externalId=596b2fd70c204203a33a3eeb start=1500196623361 end=1500196623361 msg=Activity policy ''test-activity-policy3'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Office 365 cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eeb cs2Label=uniqueServiceAppIds cs2=APPID_O365 cs3Label=relatedAudits cs3=1500196549157_a0e01f8a-e29a-43ae-8599-783c1c11597d cs4Label=policyIDs cs4=

2017-07-16T09:17:15.426Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b2fd70c204203a33a3eec start=1500196635426 end=1500196635426 msg=Activity policy ''test-activity-policy'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Office 365 admin center cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eec cs2Label=uniqueServiceAppIds cs2=APPID_O365_PORTAL cs3Label=relatedAudits cs3=1500196557398_3e102b20-d9fa-4f66-b550-8c7a403bb4d8 cs4Label=policyIDs cs4=59f0ab35f797fa9811e9b1c7

2017-07-16T09:17:46.290Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy4|3|externalId=596b30200c204203a33a4765 start=1500196666290 end=1500196666290 msg=Activity policy ''test-activity-policy4'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Exchange Online cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b30200c204203a33a4765 cs2Label=uniqueServiceAppIds cs2=APPID_OUTLOOK cs3Label=relatedAudits cs3=1500196587034_a8673602-7e95-46d6-a1fe-c156c4709c5d cs4Label=policyIDs cs4=

2017-07-16T09:41:04.369Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy2|3|externalId=596b34b10c204203a33a5240 start=1500198064369 end=1500198064369 msg=Activity policy ''test-activity-policy2'' was triggered by ''user2@test15-adallom.com'' suser=user2@test15-adallom.com destinationServiceName=Google cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b34b10c204203a33a5240 cs2Label=uniqueServiceAppIds cs2=APPID_33626 cs3Label=relatedAudits cs3=1500197996117_fd71f265-1e46-4f04-b372-2e32ec874cd3 cs4Label=policyIDs cs4=
```

<span data-ttu-id="c0a81-200">Y este es otro ejemplo, esta vez en formato CEF:</span><span class="sxs-lookup"><span data-stu-id="c0a81-200">And here's another sample, this time in CEF format:</span></span>


|<span data-ttu-id="c0a81-201">Nombre del campo CEF</span><span class="sxs-lookup"><span data-stu-id="c0a81-201">CEF field name</span></span>  | <span data-ttu-id="c0a81-202">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0a81-202">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="c0a81-203">start</span><span class="sxs-lookup"><span data-stu-id="c0a81-203">start</span></span>     | <span data-ttu-id="c0a81-204">marca de hora de alerta</span><span class="sxs-lookup"><span data-stu-id="c0a81-204">alert timestamp</span></span>        |
|<span data-ttu-id="c0a81-205">end</span><span class="sxs-lookup"><span data-stu-id="c0a81-205">end</span></span>     | <span data-ttu-id="c0a81-206">marca de hora de alerta</span><span class="sxs-lookup"><span data-stu-id="c0a81-206">alert timestamp</span></span>        |
|<span data-ttu-id="c0a81-207">RT</span><span class="sxs-lookup"><span data-stu-id="c0a81-207">rt</span></span>     | <span data-ttu-id="c0a81-208">marca de hora de alerta</span><span class="sxs-lookup"><span data-stu-id="c0a81-208">alert timestamp</span></span>        |
|<span data-ttu-id="c0a81-209">Enviado</span><span class="sxs-lookup"><span data-stu-id="c0a81-209">msg</span></span>     | <span data-ttu-id="c0a81-210">Descripción de la alerta como se muestra en el portal de seguridad de aplicación de nube de Office 365</span><span class="sxs-lookup"><span data-stu-id="c0a81-210">alert description as shown in the Office 365 Cloud App Security portal</span></span>        |
|<span data-ttu-id="c0a81-211">suser</span><span class="sxs-lookup"><span data-stu-id="c0a81-211">suser</span></span>     | <span data-ttu-id="c0a81-212">usuario de asunto de alerta</span><span class="sxs-lookup"><span data-stu-id="c0a81-212">alert subject user</span></span>        |
|<span data-ttu-id="c0a81-213">destinationServiceName</span><span class="sxs-lookup"><span data-stu-id="c0a81-213">destinationServiceName</span></span>     | <span data-ttu-id="c0a81-214">la aplicación de origen de la alerta, como Office 365, SharePoint o OneDrive</span><span class="sxs-lookup"><span data-stu-id="c0a81-214">alert originating app, such as Office 365, SharePoint, or OneDrive</span></span>        |
|<span data-ttu-id="c0a81-215">csLabel</span><span class="sxs-lookup"><span data-stu-id="c0a81-215">csLabel</span></span>     | <span data-ttu-id="c0a81-216">Varía (las etiquetas tienen distintos significados).</span><span class="sxs-lookup"><span data-stu-id="c0a81-216">Varies (labels have different meanings).</span></span> <span data-ttu-id="c0a81-217">Normalmente, las etiquetas se explican por sí mismas, como targetObjects.</span><span class="sxs-lookup"><span data-stu-id="c0a81-217">Typically, labels are self-explanatory, like targetObjects.</span></span>        |
|<span data-ttu-id="c0a81-218">cs</span><span class="sxs-lookup"><span data-stu-id="c0a81-218">cs</span></span>     | <span data-ttu-id="c0a81-219">Información correspondiente a una etiqueta (como, por ejemplo, el usuario de destino de una alerta según el ejemplo de la etiqueta)</span><span class="sxs-lookup"><span data-stu-id="c0a81-219">Information corresponding to a label (such as the target user of an alert as per the label example)</span></span>        |

## <a name="additional-tasks-as-needed"></a><span data-ttu-id="c0a81-220">Tareas adicionales (según sea necesario)</span><span class="sxs-lookup"><span data-stu-id="c0a81-220">Additional tasks (as needed)</span></span>

<span data-ttu-id="c0a81-221">Una vez que haya configurado el servidor de SIEM y lo haya integrado con Office 365 Cloud App Security, es posible que deba regenerar un token, editar un agente de SIEM o eliminar un agente de SIEM.</span><span class="sxs-lookup"><span data-stu-id="c0a81-221">After you have configured your SIEM server and have integrated it with Office 365 Cloud App Security, you might need to regenerate a token, edit a SIEM agent, or delete a SIEM agent.</span></span> <span data-ttu-id="c0a81-222">En las secciones siguientes se describe cómo realizar estas tareas.</span><span class="sxs-lookup"><span data-stu-id="c0a81-222">The following sections describe how to perform these tasks.</span></span>

### <a name="regenerate-a-token"></a><span data-ttu-id="c0a81-223">Volver a generar un token</span><span class="sxs-lookup"><span data-stu-id="c0a81-223">Regenerate a token</span></span>

<span data-ttu-id="c0a81-224">Si pierde el token, puede volver a generar uno.</span><span class="sxs-lookup"><span data-stu-id="c0a81-224">If you lose your token, you can regenerate one.</span></span> 

1. <span data-ttu-id="c0a81-225">en Office 365 Cloud App Security[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)portal (), elija **settings** > **security extensions**.</span><span class="sxs-lookup"><span data-stu-id="c0a81-225">In the Office 365 Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)), choose **Settings** > **Security extensions**.</span></span>

2. <span data-ttu-id="c0a81-226">En la tabla, busque la fila del agente SIEM.</span><span class="sxs-lookup"><span data-stu-id="c0a81-226">In the table, locate the row for the SIEM agent.</span></span> 

3. <span data-ttu-id="c0a81-227">Haga clic en los puntos suspensivos y, a continuación, elija **regenerar token**.</span><span class="sxs-lookup"><span data-stu-id="c0a81-227">Click the ellipses, and then choose **Regenerate token**.</span></span><br/><span data-ttu-id="c0a81-228">![Regenere un token haciendo clic en los puntos suspensivos del agente de SIEM](media/04de368a-b88e-4a9c-a830-58025cb98db6.png)</span><span class="sxs-lookup"><span data-stu-id="c0a81-228">![Regenerate a token by clicking the ellipsis for your SIEM agent](media/04de368a-b88e-4a9c-a830-58025cb98db6.png)</span></span>
  
### <a name="edit-a-siem-agent"></a><span data-ttu-id="c0a81-229">Edición de un agente de SIEM</span><span class="sxs-lookup"><span data-stu-id="c0a81-229">Edit a SIEM agent</span></span>

1. <span data-ttu-id="c0a81-230">en Office 365 Cloud App Security[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)portal (), elija **settings** > **security extensions**.</span><span class="sxs-lookup"><span data-stu-id="c0a81-230">In the Office 365 Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)), choose **Settings** > **Security extensions**.</span></span>

2. <span data-ttu-id="c0a81-231">Busque la fila del agente SIEM.</span><span class="sxs-lookup"><span data-stu-id="c0a81-231">Locate the row for the SIEM agent.</span></span> 

3. <span data-ttu-id="c0a81-232">Haga clic en los puntos suspensivos y, a continuación, elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c0a81-232">Click the ellipses, and then choose **Edit**.</span></span> <span data-ttu-id="c0a81-233">(Si edita el agente SIEM, no es necesario volver a ejecutar el archivo. jar; se actualiza automáticamente).</span><span class="sxs-lookup"><span data-stu-id="c0a81-233">(If you edit the SIEM agent, you do not need to re-run the .jar file; it updates automatically.)</span></span> <br/><span data-ttu-id="c0a81-234">![Para editar el agente de SIEM, elija los puntos suspensivos y, a continuación, elija Editar.](media/96d0b362-3e0c-4dff-b2b4-d7af5b1bfb91.png)</span><span class="sxs-lookup"><span data-stu-id="c0a81-234">![To edit your SIEM agent, choose the ellipses, and then choose Edit.](media/96d0b362-3e0c-4dff-b2b4-d7af5b1bfb91.png)</span></span>
  
### <a name="delete-a-siem-agent"></a><span data-ttu-id="c0a81-235">Eliminar un agente de SIEM</span><span class="sxs-lookup"><span data-stu-id="c0a81-235">Delete a SIEM agent</span></span>

1. <span data-ttu-id="c0a81-236">en Office 365 Cloud App Security[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)portal (), elija **settings** > **security extensions**.</span><span class="sxs-lookup"><span data-stu-id="c0a81-236">In the Office 365 Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)), choose **Settings** > **Security extensions**.</span></span>

2. <span data-ttu-id="c0a81-237">Busque la fila del agente SIEM.</span><span class="sxs-lookup"><span data-stu-id="c0a81-237">Locate the row for the SIEM agent.</span></span> 

3. <span data-ttu-id="c0a81-238">Haga clic en los puntos suspensivos y, a continuación, elija **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="c0a81-238">Click the ellipses, and then choose **Delete**.</span></span><br/><span data-ttu-id="c0a81-239">![Para eliminar un agente de SIEM, elija los puntos suspensivos y, a continuación, elija Eliminar.](media/540b5bdf-5574-4ecc-a7b0-92a499a387d7.png)</span><span class="sxs-lookup"><span data-stu-id="c0a81-239">![To delete a SIEM agent, choose the ellipses, and then choose Delete.](media/540b5bdf-5574-4ecc-a7b0-92a499a387d7.png)</span></span>

  
## <a name="next-steps"></a><span data-ttu-id="c0a81-240">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c0a81-240">Next steps</span></span>

- [<span data-ttu-id="c0a81-241">Actividades de uso después de implementar Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c0a81-241">Utilization activities after rolling out Office 365 Cloud App Security</span></span>](utilization-activities-for-ocas.md)
    
- [<span data-ttu-id="c0a81-242">Revisar y realizar acciones en las alertas</span><span class="sxs-lookup"><span data-stu-id="c0a81-242">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="c0a81-243">Agrupar las direcciones IP para simplificar la administración</span><span class="sxs-lookup"><span data-stu-id="c0a81-243">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    


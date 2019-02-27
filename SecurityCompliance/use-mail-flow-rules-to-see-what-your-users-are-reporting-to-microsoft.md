---
title: Use reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Puede crear una regla de transporte de Exchange para evitar que los usuarios envíen mensajes de correo electrónico a Microsoft para su análisis y usarlos en sus propios procesos de seguridad.
ms.openlocfilehash: 5838b05327858cbad3c530674153989c173f4048
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275990"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Use reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft

Hay varias formas de enviar mensajes falsos positivos y falsos negativos a Microsoft para su análisis. Como administrador, puede usar reglas de flujo de correo para ver lo que los usuarios notifican a Microsoft como correo no deseado, fraudes de suplantación de identidad (phishing). Para obtener más información, vea enviar correo electrónico no deseado, mensajes de correo [no deseado y mensajes de estafa de suplantación de identidad a Microsoft para su análisis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). Por el contrario, puede crear una regla de transporte de Exchange para evitar que los usuarios envíen mensajes de correo electrónico a Microsoft para su análisis y usarlos en sus propios procesos de seguridad.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

Tiempo estimado para finalizar: 5 minutos
  
Debe tener permisos asignados para poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "reglas de transporte" en el tema [permisos de directivas de mensajería y conformidad](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) y la entrada "directivas de buzón de Outlook en la web" en el tema [clients and Mobile](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) Devices Permissions. 
  
Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Métodos abreviados de teclado en el Centro de administración de Exchange**.
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a>Usar el EAC para crear una regla de flujo de correo para ver los informes de correo no deseado manuales de los usuarios, suplantación de identidad (phishing) y no

1. En el EAC, vaya a **Flujo de correo** \> **Reglas**.
    
2. Click ![Agregar icono](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.
    
3. Give the rule a name and then click **More options**.
    
4. Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.
    
5. In the **specify words or phrases** box, do the following: 
    - Escriba `abuse@messaging.microsoft.com` y haga clic ![en agregar](media/ITPro-EAC-AddIcon.gif)icono y, a `junk@office365.microsoft.com` continuación, escriba ![y,](media/ITPro-EAC-AddIcon.gif)a continuación, haga clic en agregar icono. Estas direcciones de correo electrónico se usan para enviar mensajes falsos negativos a Microsoft.
    - Escriba `phish@office365.microsoft.com` y, a ![continuación,](media/ITPro-EAC-AddIcon.gif)haga clic en agregar icono. Esta dirección de correo electrónico se usa para enviar mensajes de suplantación de identidad perdidos a Microsoft.
    - Escriba `false_positive@messaging.microsoft.com` y haga clic ![en agregar](media/ITPro-EAC-AddIcon.gif)icono y, a `not_junk@office365.microsoft.com` continuación, escriba ![y,](media/ITPro-EAC-AddIcon.gif)a continuación, haga clic en agregar icono. Estas direcciones de correo electrónico se usan para enviar mensajes de falso positivo a Microsoft.
    - Click **ok**.
    
6. En **hacer lo siguiente**, seleccione **CCO el mensaje a...** y, a continuación, seleccione los buzones donde quiera recibir los mensajes. 
    
7. Si lo desea, puede realizar selecciones para auditar la regla, probarla, activar la regla durante un período de tiempo específico y otras selecciones. Se recomienda probar la regla durante un período antes de aplicarla. Consulte [procedimientos para reglas de flujo de correo](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures). 
    
8. Haga clic en el botón **Guardar** para guardar la regla. Aparecerá en la lista de reglas. 
    
Después de crear y aplicar la regla, todos los mensajes que se envíen desde la organización a las direcciones de correo electrónico especificadas se copiarán en el buzón especificado.
  


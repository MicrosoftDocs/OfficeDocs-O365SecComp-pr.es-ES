---
title: Use reglas de flujo de correo para ver lo que los usuarios son informes a Microsoft
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
description: Puede crear una regla de transporte de Exchange para impedir que los usuarios enviar mensajes de correo electrónico a Microsoft para su análisis y usarlas en sus propios procesos de seguridad
ms.openlocfilehash: 6c6af23e6a5f345e26c7dc09c898f2978ea51a5f
ms.sourcegitcommit: df1e9590a9fa152fa776f16d9b25c180ba7198f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2018
ms.locfileid: "22122590"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Use reglas de flujo de correo para ver lo que los usuarios son informes a Microsoft

Hay varias maneras que puede enviar mensajes negativos falsos positivos y false a Microsoft para su análisis. Como administrador, puede usar las reglas de flujo de correo para ver lo que los usuarios son informes a Microsoft como correo no deseado, que no sean de correo no deseado y las estafas de suplantación de identidad. Para obtener más información, vea [enviar spam, no spam y los mensajes de estafas de suplantación de identidad a Microsoft para su análisis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). Por el contrario, puede crear una regla de transporte de Exchange para impedir que los usuarios enviar mensajes de correo electrónico a Microsoft para su análisis y usarlas en sus propios procesos de seguridad.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

Tiempo estimado para finalizar: 5 minutos
  
Debe tener asignados los permisos puede llevar a cabo estos procedimientos. Para ver qué permisos necesita, vea la entrada "Reglas de transporte" en el tema [permisos de directivas y cumplimiento de normas de mensajería](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) y la entrada "Directivas de buzón de correo de Outlook Web App" en el tema de [los clientes y los permisos de los dispositivos móviles](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) . 
  
Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Métodos abreviados de teclado en el Centro de administración de Exchange**.
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a>Usar el EAC para crear una regla de flujo de correo para ver los usuarios manual correo no deseado, suplantación de identidad y los informes no no deseados

1. En el EAC, vaya a **Flujo de correo** \> **Reglas**.
    
2. Click ![Agregar icono](media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.
    
3. Give the rule a name and then click **More options**.
    
4. Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.
    
5. In the **specify words or phrases** box, do the following: 
    - Tipo de `abuse@messaging.microsoft.com` y, a continuación, haga clic en ![icono Agregar](media/ITPro-EAC-AddIcon.png)y, a continuación, escriba `junk@office365.microsoft.com` y, a continuación, haga clic en ![icono Agregar](media/ITPro-EAC-AddIcon.png). Estas direcciones de correo electrónico se utilizan para enviar mensajes falsos negativos a Microsoft.
    - Tipo de `phish@office365.microsoft.com` y, a continuación, haga clic en ![icono Agregar](media/ITPro-EAC-AddIcon.png). Esta dirección de correo electrónico se usa para enviar mensajes de suplantación de identidad perdidas a Microsoft.
    - Tipo de `false_positive@messaging.microsoft.com` y, a continuación, haga clic en ![icono Agregar](media/ITPro-EAC-AddIcon.png)y, a continuación, escriba `not_junk@office365.microsoft.com` y, a continuación, haga clic en ![icono Agregar](media/ITPro-EAC-AddIcon.png). Estas direcciones de correo electrónico se utilizan para enviar mensajes falsos positivos a Microsoft.
    - Click **ok**.
    
6. Bajo, **siga este procedimiento**, seleccione **CCO del mensaje a...** y, a continuación y, a continuación, seleccione los buzones de correo que desea reciben los mensajes. 
    
7. Si lo desea, puede realizar las selecciones para la regla de auditoría, probar la regla, active la regla durante un período de tiempo específico y otras selecciones. Se recomienda probar la regla para un período antes de aplicarlo. Consulte [los procedimientos para las reglas de flujo de correo](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures). 
    
8. Haga clic en el botón **Guardar** para guardar la regla. Aparecerá en la lista de reglas. 
    
Después de crear y aplicar la regla, se copiarán todos los mensajes que se envían desde la organización a las direcciones de correo electrónico especificada en el buzón especificado.
  


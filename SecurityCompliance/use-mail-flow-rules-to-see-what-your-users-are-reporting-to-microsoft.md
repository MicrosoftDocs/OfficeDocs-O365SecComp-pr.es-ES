---
title: Usar reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Puede crear una regla de flujo de correo de Exchange para evitar que los usuarios envíen mensajes de correo electrónico a Microsoft para su análisis y usarlos en sus propios procesos de seguridad.
ms.openlocfilehash: 0086cf048dcffa912085f23b328ab1d51780f0df
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156142"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Usar reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft

There are multiple ways you can send false positive and false negative messages to Microsoft for analysis. Como administrador, puede usar reglas de flujo de correo para ver lo que los usuarios notifican a Microsoft como correo no deseado, fraudes de suplantación de identidad (phishing). Para obtener más información, vea enviar correo electrónico no deseado, mensajes de correo [no deseado y mensajes de estafa de suplantación de identidad a Microsoft para su análisis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). Por el contrario, puede crear una regla de flujo de correo de Exchange (también denominada regla de transporte) para evitar que los usuarios envíen mensajes de correo electrónico a Microsoft para su análisis y usarlos en sus propios procesos de seguridad.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

Tiempo estimado para finalizar: 5 minutos
  
Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "reglas de flujo de correo" en el tema [permisos de directivas de mensajería y conformidad](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) y la entrada "directivas de buzón de Outlook en la web" en el tema [clients and Mobile](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) Devices Permissions. 
  
Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Métodos abreviados de teclado en el Centro de administración de Exchange**.
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a>Usar el EAC para crear una regla de flujo de correo para ver los informes de correo no deseado manuales de los usuarios, suplantación de identidad (phishing) y no

1. En el EAC, vaya a **Flujo de correo** \> **Reglas**.
    
2. Click ![Agregar icono](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.
    
3. Give the rule a name and then click **More options**.
    
4. Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.
    
5. In the **specify words or phrases** box, do the following: 
    - Escriba `abuse@messaging.microsoft.com` y haga clic ![en agregar](media/ITPro-EAC-AddIcon.gif)icono y, a `junk@office365.microsoft.com` continuación, escriba ![y,](media/ITPro-EAC-AddIcon.gif)a continuación, haga clic en agregar icono. These email addresses are used to submit false negative messages to Microsoft.
    - Escriba `phish@office365.microsoft.com` y, a ![continuación,](media/ITPro-EAC-AddIcon.gif)haga clic en agregar icono. Esta dirección de correo electrónico se usa para enviar mensajes de suplantación de identidad perdidos a Microsoft.
    - Escriba `false_positive@messaging.microsoft.com` y haga clic ![en agregar](media/ITPro-EAC-AddIcon.gif)icono y, a `not_junk@office365.microsoft.com` continuación, escriba ![y,](media/ITPro-EAC-AddIcon.gif)a continuación, haga clic en agregar icono. These email addresses are used to submit false positive messages to Microsoft.
    - Click **ok**.
    
6. En **hacer lo siguiente**, seleccione **CCO el mensaje a...** y, a continuación, seleccione los buzones donde quiera recibir los mensajes. 
    
7. Si lo desea, puede realizar selecciones para auditar la regla, probarla, activarla durante un período de tiempo específico y otras selecciones. Recomendamos probar la regla durante un tiempo antes de aplicarla. Consulte [procedimientos para reglas de flujo de correo](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures). 
    
8. Haga clic en el botón **Guardar** para guardar la regla. Aparecerá en la lista de reglas. 
    
Después de crear y aplicar la regla, todos los mensajes que se envíen desde la organización a las direcciones de correo electrónico especificadas se copiarán en el buzón especificado.
  


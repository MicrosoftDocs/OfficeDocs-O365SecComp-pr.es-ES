---
title: Solución de problemas e información de soporte técnico
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5d9f75f5-bb7f-458c-ad30-5c8eae0b0e4e
ms.collection:
- M365-security-compliance
description: En este tema se describen pasos de solución de problemas para usuarios finales y administradores, y se proporciona información acerca de cómo ponerse en contacto con el soporte técnico para obtener ayuda.
ms.openlocfilehash: bea2ad502f24d63874bfa954e6d67c73dc44d98d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32259848"
---
# <a name="troubleshooting-and-support-information"></a>Solución de problemas e información de soporte técnico

En este tema se describen pasos de solución de problemas para usuarios finales y administradores, y se proporciona información acerca de cómo ponerse en contacto con el soporte técnico para obtener ayuda.
  
## <a name="troubleshooting-for-users"></a>Solución de problemas para usuarios

De manera ocasional, puede experimentar problemas con Microsoft Office Outlook después de agregar el complemento de notificación de correo no deseado. A continuación, se enumeran los problemas que puede experimentar, junto con las sugerencias correspondientes para resolverlos. 
  
- Al hacer clic en **Informar de correo electrónico no deseado**, no ocurre ninguna acción.
    
- Outlook deja de responder después de seleccionar un mensaje de correo electrónico.
    
- El correo no deseado notificado no se puede entregar debido a una respuesta de "no se puede entregar".
    
### <a name="troubleshooting-tip"></a>Consejos para solucionar el problema

1. Cierre y reinicie Microsoft Office Outlook.
    
2. Compruebe que puede crear y enviar un mensaje de prueba. Para ello, puede enviar un mensaje de prueba a otra cuenta de correo electrónico y, a continuación, comprobar si se recibe el mensaje.
    
Si el problema continúa, póngase en contacto con el administrador de TI.
  
> [!TIP]
> También puede enviar mensajes de correo no deseado directamente a Microsoft a la dirección de correo electrónico [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com), y mensajes falsos positivos a la dirección de correo electrónico [not_junk@office365.microsoft.com](mailto: not_junk@office365.microsoft.com). Para obtener más información, vea enviar correo electrónico no deseado, mensajes de correo [no deseado y mensajes de estafa de suplantación de identidad a Microsoft para su análisis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). 
  
## <a name="troubleshooting-for-administrators"></a>Solución de problemas para administradores

Como administrador, puede tener problemas con usuarios que usen el complemento de notificación de correo no deseado para Microsoft Office Outlook. A continuación hay algunos pasos para resolver problemas que pueda encontrar. 
  
 **Problema:** Aparece un mensaje de error que solicita continuamente a los usuarios que se pongan en contacto con el administrador del sistema. 
  
### <a name="troubleshooting-tip"></a>Consejos para solucionar el problema

1. Establezca el valor de la clave del Registro siguiente en "Verbose":
    
  - **Outlook de 32 bits instalado en un sistema operativo de 32 bits:**
    
    HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel
    
  - **Outlook de 32 bits instalado en un sistema operativo de 64 bits:**
    
    HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Junk Email Reporting\Addins\LoggingLevel
    
  - **Outlook de 64 bits (siempre instalado en un sistema operativo de 64 bits):**
    
    HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel
    
2. Reinicie Microsoft Office Outlook y solicite a los usuarios que le vuelvan a informar cuando aparezca el mensaje de error.
    
3. Recopile la información de registro de la siguiente ubicación: 
    
    %LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt
    
4. Póngase en contacto con el soporte técnico de Protección en línea de Exchange y proporcione la información de registro. 
    
 **Problema:** Los usuarios optan por no recibir una confirmación cuando envían un correo electrónico como correo no deseado y ahora desean activar esta opción. 
  
### <a name="troubleshooting-tip"></a>Consejos para solucionar el problema

1. Establezca el valor de la clave del Registro siguiente en "True": HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences\ConfirmReportJunk
    
2. Reinicie Microsoft Office Outlook.
    
## <a name="support-information"></a>Información de soporte

Si necesita ayuda para instalar, configurar o desinstalar el complemento, póngase en contacto con el soporte técnico mediante el vínculo nueva solicitud de servicio de la página soporte del centro de administración de Microsoft 365. Para obtener opciones adicionales, como el envío de una solicitud de servicio a través de las opciones de teléfono y de autosoporte, consulte [ayuda y soporte técnico para EOP](eop/help-and-support-for-eop.md).
  
## <a name="for-more-information"></a>Más información

[Habilitar el complemento de mensajes de informe](https://support.office.com/article/4250c4bc-6102-420b-9e0a-a95064837676)
  
[Informar a Microsoft sobre mensajes de correo electrónico no deseado](report-junk-email-messages-to-microsoft.md)
  


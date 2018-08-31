---
title: Information Rights Management en Exchange Online
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2c956776-0016-4be6-b4cd-133a237f4a9e
description: Las personas suelen usar el correo para intercambiar información confidencial, como datos financieros, contratos legales, información confidencial de productos, informes y proyecciones de ventas, información de historial médico o información sobre clientes y empleados. Por ello, los buzones de correo pueden convertirse en repositorios para cantidades grandes de información posiblemente confidencial y la filtración de información puede convertirse en una seria amenaza para las organizaciones.
ms.openlocfilehash: 5036fe359215de1c2674d7efabbb283c78418a19
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002581"
---
# <a name="information-rights-management-in-exchange-online"></a>Information Rights Management en Exchange Online

Las personas suelen usar el correo para intercambiar información confidencial, como datos financieros, contratos legales, información confidencial de productos, informes y proyecciones de ventas, información de historial médico o información sobre clientes y empleados. Por ello, los buzones de correo pueden convertirse en repositorios para cantidades grandes de información posiblemente confidencial y la filtración de información puede convertirse en una seria amenaza para las organizaciones.
  
Para ayudar a evitar la fuga de información, Exchange Online incluye la funcionalidad Information Rights Management (IRM) que proporciona protección en línea y sin conexión de mensajes de correo electrónico y archivos adjuntos. Se puede aplicar la protección de IRM por los usuarios de Microsoft Outlook o Outlook en la web, y se pueden aplicar los administradores mediante reglas de protección de transporte o las reglas de protección de Outlook. IRM ayuda a usted y su control de usuarios que puede obtener acceso, reenviar, imprimir o copiar datos confidenciales dentro de un correo electrónico.
  
## <a name="changes-to-how-irm-works-with-office-365-message-encryption-ome-and-azure-active-directory"></a>Cambios realizados en funcionamiento de IRM con Office 365 Message Encryption (OME) y Azure Active Directory

A partir de septiembre de 2017, al configurar las nuevas capacidades de cifrado de mensajes de Office 365 para su organización, también configurar IRM para su uso con Azure Rights Management (RMS Azure). Ya no configurar IRM con Azure RMS por separado. En su lugar, OME administración de derechos y trabajar juntos sin ningún problema. Para obtener más información acerca de las nuevas capacidades, consulte [Preguntas más frecuentes sobre el cifrado de mensajes de Office 365](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e). Si está listo para empezar a usar las nuevas capacidades OME dentro de la organización, consulte [Configurar nuevas capacidades de Office 365 Message Encryption fundamentan en protección de la información de Azure](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e).
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a>Cómo funciona IRM con Exchange Online y Active Directory Rights Management Services

Exchange Online IRM utiliza local Active Directory Rights Management Services (AD RMS), una tecnología de protección de información en Windows Server 2008 y versiones posteriores. Protección de IRM se aplica a correo electrónico mediante la aplicación de una plantilla de directiva de derechos de AD RMS a un mensaje de correo electrónico. Derechos están asociados al propio mensaje para que se produzca una protección en línea y sin conexión y dentro y fuera del firewall de la organización.
  
Los usuarios pueden aplicar una plantilla a un mensaje de correo electrónico para controlar los permisos que tienen los destinatarios en un mensaje. Acciones, como desvío, extraer información de un mensaje, guardar un mensaje o impresión de un mensaje se pueden controlar mediante la aplicación de una directiva de derechos de AD RMS para el mensaje.
  
Puede configurar IRM para usar un servidor de AD RMS que ejecuta Windows Server 2008 o posterior. Puede usar este servidor de AD RMS para administrar las plantillas de directiva de derechos de AD RMS para su organización basada en la nube. Outlook también se basa en el servidor de AD RMS para permitir a los usuarios aplicar la protección de IRM a los mensajes que envían. Para obtener información detallada, vea [configurar IRM para usar un local de servidor de AD RMS](configure-irm-to-use-an-on-premises-ad-rms-server.md). 
  
Después de habilitarla, la protección IRM se aplica a los mensajes del modo siguiente:
  
- **Los usuarios pueden aplicar manualmente una plantilla mediante Outlook y Outlook en el web.** Los usuarios pueden aplicar una plantilla de directiva de derechos de AD RMS a un mensaje de correo electrónico mediante la selección de la plantilla de la lista **conjunto de permisos** . Cuando los usuarios enviar un mensaje protegido mediante IRM, los archivos adjuntos que usan un formato compatible también reciben la misma protección de IRM que el mensaje. Protección de IRM se aplica a los archivos asociados con Word, Excel y PowerPoint, así como archivos .xps y mensajes de correo electrónico adjunto. 
    
- **Los administradores pueden usar las reglas de protección de transporte para aplicar la protección de IRM automáticamente a Outlook y Outlook en el web.** Puede crear reglas de protección de transporte para los mensajes de protección de IRM. Configurar la acción de regla de protección de transporte para aplicar una plantilla de directiva de derechos de AD RMS a mensajes que cumplan la condición de regla. Después de habilitar IRM, están disponibles para usar con la acción de regla de protección de transporte denominada **Aplicar protección de derechos al mensaje con**plantillas de directiva de derechos de AD RMS de la organización.
    
- **Los administradores pueden crear reglas de protección de Outlook.** Las reglas de protección de Outlook aplican automáticamente la protección de IRM a los mensajes en Outlook 2010 (no en Outlook en el web) según las condiciones de mensaje que incluyen el departamento del remitente, que el mensaje se envió a, y si los destinatarios están dentro o fuera su organización. Para obtener información detallada, vea [crear una regla de protección de Outlook](http://technet.microsoft.com/library/da64750d-faaf-44de-ad8c-888eba7fbdbf.aspx).
    


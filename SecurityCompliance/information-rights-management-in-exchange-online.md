---
title: Information Rights Management en Exchange Online
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2c956776-0016-4be6-b4cd-133a237f4a9e
description: Las personas suelen usar el correo para intercambiar información confidencial, como datos financieros, contratos legales, información confidencial de productos, informes y proyecciones de ventas, información de historial médico o información sobre clientes y empleados. Por ello, los buzones de correo pueden convertirse en repositorios para cantidades grandes de información posiblemente confidencial y la filtración de información puede convertirse en una seria amenaza para las organizaciones.
ms.openlocfilehash: aef3acaba6b0efe4550958ce1d98add371069648
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32253988"
---
# <a name="information-rights-management-in-exchange-online"></a>Information Rights Management en Exchange Online

Las personas suelen usar el correo para intercambiar información confidencial, como datos financieros, contratos legales, información confidencial de productos, informes y proyecciones de ventas, información de historial médico o información sobre clientes y empleados. Por ello, los buzones de correo pueden convertirse en repositorios para cantidades grandes de información posiblemente confidencial y la filtración de información puede convertirse en una seria amenaza para las organizaciones.
  
Para ayudar a evitar la filtración de información, Exchange Online incluye la función Information Rights Management (IRM), que ofrece protección en línea y sin conexión para los mensajes de correo y los datos adjuntos. La protección de IRM pueden aplicarla los usuarios en Microsoft Outlook o Outlook en la web, y los administradores pueden aplicarla mediante reglas de protección de transporte o reglas de protección de Outlook. IRM le ayuda tanto a usted como a los usuarios a controlar quién puede consultar, reenviar, imprimir o copiar información confidencial del correo.
  
## <a name="changes-to-how-irm-works-with-office-365-message-encryption-ome-and-azure-active-directory"></a>Cambios en el funcionamiento de IRM con Office 365 cifrado de mensajes (OME) y Azure Active Directory

A partir del 2017 de septiembre, cuando configure las nuevas capacidades de cifrado de mensajes de Office 365 para su organización, también debe configurar IRM para usarla con Azure Rights Management (Azure RMS). Ya no configura IRM con Azure RMS por separado. En su lugar, OME y la administración de derechos trabajan de forma transparente en todo el conjunto. Para obtener más información sobre las nuevas funciones, consulte [preguntas más frecuentes](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e)sobre el cifrado de mensajes de Office 365. Si está listo para empezar a usar las nuevas funciones de OME dentro de su organización, vea [configurar las nuevas funciones de cifrado de mensajes de Office 365 integradas en Azure Information Protection](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e).
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a>Cómo funciona IRM con Exchange Online y Active Directory Rights Management Services

IRM de Exchange online usa Active Directory Rights Management Services local (AD RMS), una tecnología de protección de la información en Windows Server 2008 y versiones posteriores. La protección de IRM se implanta en el correo electrónico mediante la aplicación de una plantilla de directiva de permisos de AD RMS a un mensaje de correo electrónico. Los derechos se adjuntan al propio mensaje para que la protección se produzca en línea o sin conexión, y dentro y fuera del firewall de la organización.
  
Los usuarios pueden aplicar una plantilla a un mensaje de correo electrónico para controlar los permisos que los destinatarios tienen en un mensaje. Algunas acciones, como reenviar o extraer información de un mensaje, guardar un mensaje o imprimirlo, se pueden controlar aplicando una directiva de permisos AD RMS al mensaje.
  
Puede configurar IRM para usar un servidor de AD RMS que ejecute Windows Server 2008 o posterior. Puede usar este servidor de AD RMS local para administrar las plantillas de directiva de permisos AD RMS en la organización basada en nube. Outlook también depende del servidor de AD RMS para permitir a los usuarios aplicar la protección IRM a los mensajes que envían. Para obtener más información, vea [configure IRM to Use an on-premises AD RMS Server](configure-irm-to-use-an-on-premises-ad-rms-server.md). 
  
Después de habilitarla, la protección IRM se aplica a los mensajes del modo siguiente:
  
- **Los usuarios pueden aplicar manualmente una plantilla mediante Outlook y Outlook en la Web.** Los usuarios pueden aplicar una plantilla de directiva de permisos AD RMS a un mensaje de correo electrónico seleccionando la plantilla en la lista **establecer permisos** . Cuando los usuarios envían un mensaje protegido con IRM, los datos adjuntos que tengan un formato compatible reciben la misma protección de IRM que el mensaje. La protección de IRM se aplica a los archivos asociados con Word, Excel y PowerPoint, así como a los archivos .xps y a los mensajes de correo adjuntos. 
    
- **Los administradores pueden usar reglas de protección de transporte para aplicar la protección de IRM automáticamente a Outlook y Outlook en la Web.** Puede crear reglas de protección de transporte para proteger los mensajes de IRM. Configure la acción de la regla de protección de transporte para aplicar una plantilla de permisos de AD RMS a los mensajes que cumplan la condición de la regla. Después de habilitar IRM, las plantillas de directivas de permisos de AD RMS de la organización ya se pueden usar con la acción de la regla de protección de transporte denominada **Aplicar protección de derechos al mensaje con**.
    
- **Los administradores pueden crear reglas de protección de Outlook.** Las reglas de protección de Outlook aplican automáticamente la protección de IRM a los mensajes en Outlook 2010 (no en la Web de Outlook) basándose en las condiciones del mensaje que incluyen el Departamento del remitente, a quién se envía el mensaje y si los destinatarios están dentro o fuera del Organization. Para información detallada, vea [Create an Outlook Protection Rule](http://technet.microsoft.com/library/da64750d-faaf-44de-ad8c-888eba7fbdbf.aspx).
    


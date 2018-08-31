---
title: Evitar que el correo electrónico se marquen como correo no deseado en Office 365 y Exchange Online Protection
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 74aaade0-efc0-46ac-b949-f2d1d59256fa
description: Sugerencias para administradores de Office 365 evitar que el correo electrónico buena marcado como correo no deseado desde la que se envían a cuarentena como un falso positivo. Personalizar un listas seguras y otras opciones para evitar que el correo electrónico buena marcado como correo no deseado.
ms.openlocfilehash: 42b27d237592e95e6d175ab335959bc82269c0f7
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535682"
---
# <a name="prevent-email-from-being-marked-as-spam-in-office-365-and-exchange-online-protection"></a>Evitar que el correo electrónico se marquen como correo no deseado en Office 365 y Exchange Online Protection

Los administradores de Exchange Online o Exchange Online Protection (EOP) con las credenciales de acceso apropiado pueden usar estos pasos para ayudar a garantizar que un mensaje de correo electrónico que viajan a través del servicio no está marcado como correo no deseado.
  
Puede resultar frustrante correo electrónico legítima y de buena en cuarentena o bloqueado como correo no deseado y de destino en una carpeta de cuarentena. Puede usar una lista de remitentes seguros o de una regla de flujo de correo para el desvío de filtrado de spam y evitar que los mensajes de correo electrónico buena introducción marcados como correo electrónico no deseado. Cuando un mensaje está marcado incorrectamente como correo no deseado mediante el filtro de spam, se denomina un falso positivo. El filtro de spam Office 365 proporciona también algunas de las opciones que los usuarios finales pueden personalizar con el fin de ayudar a evitar los falsos positivos.
  
Si está buscando ayuda con correo negativo es false, es decir, un mensaje de spam que obtiene a través de cuando no debería, desproteger de las sugerencias de [correo electrónico de bloqueo de correo no deseado con el filtro de spam de Office 365 para evitar problemas de negativos es false](block-email-spam-to-prevent-false-negatives.md).
  
## <a name="eop-only-customers-use-directory-synchronization"></a>Los clientes sólo elevación de privilegios: usar la sincronización de Active directory

Elevación de privilegios es un correo electrónico basada en la nube de filtrado de servicio que ayuda a proteger su organización contra correo no deseado y malware. Si tiene buzones de correo en Office 365, automáticamente están protegidos por elevación de privilegios ya que es parte del servicio. 
  
Si usted es un cliente solo EOP, es decir, suscribirse al servicio de EOP para su uso con el servidor de Exchange local, debe sincronizar con el servicio de configuración del usuario mediante la sincronización de Active directory. De esta forma asegura de que la lista de remitentes seguro respetan las listas de elevación de privilegios. Para obtener más información, vea "Usar la sincronización de Active directory para administrar usuarios de correo" en [Manage Mail Users in EOP](https://go.microsoft.com/fwlink/?LinkId=534098).
  
## <a name="prevent-false-positive-email-by-using-the-connection-filters-ip-allow-list"></a>Evitar que el correo electrónico positivo false mediante el uso de la conexión IP del filtro lista de permitidos

Si observa que siempre se mueve el correo electrónico de un remitente a las carpetas no deseado en su organización, puede agregar la dirección IP del remitente de correo electrónico como dirección IP del filtro de la conexión lista de permitidos. Normalmente, esto evita que las respuestas positivas false para este remitente para todos los destinatarios dentro de la organización. La excepción se produce cuando un usuario habilita la opción "listas seguras sólo: sólo el correo de personas o dominios de la lista de remitentes seguros o la lista de destinatarios seguros se entregarán en la Bandeja de entrada" en Outlook y no se agrega ese remitente a la lista de remitentes seguros. Para obtener información sobre cómo reemplazar esta opción, consulte [solución de problemas: un mensaje termina en la carpeta de correo no deseado, aunque EOP marca el mensaje como correo no deseado que no sean](prevent-email-from-being-marked-as-spam-0.md#TroubleshootingJunkEOPNonSpam).
  
 **Para agregar una dirección IP a la conexión IP del filtro lista de permitidos**
  
1. Obtener el encabezado de un mensaje enviado por el remitente que desea permitir. Puede hacerlo desde su cliente de correo como Outlook o Outlook en la Web, tal como se describe en el [Analizador de encabezado de mensaje](https://go.microsoft.com/fwlink/p/?LinkId=306583).
    
2. Buscar manualmente la dirección IP después de la etiqueta CIP en el encabezado X-Forefront-Antispam-Report o mediante el uso de la ficha **Mensaje analizador** del [Analizador de conectividad remota](https://testconnectivity.microsoft.com/?tabid=mha).
    
3. Agregar la dirección IP dirección como la dirección IP lista de permitidos siguiendo los pasos descritos en "Utilizar el EAC para editar la directiva de filtro de conexión predeterminada" en [Configurar la directiva de filtro de conexión](https://go.microsoft.com/fwlink/?LinkId=534132).
    
## <a name="prevent-false-positive-email-by-configuring-spam-filter-policies"></a>Evitar que el correo electrónico positivo false mediante la configuración de directivas de filtro de correo no deseado

Puede agregar dominios o direcciones de correo electrónico individuales a una lista Permitir siguiendo los pasos de [configuración de sus directivas de filtro de correo no deseado](https://go.microsoft.com/fwlink/?LinkID=534136).
  
## <a name="review-your-advanced-spam-filter-policies"></a>Revise las directivas de filtro avanzadas correo no deseado

Si tiene restricciones especiales configuradas en una directiva de filtro de spam, por ejemplo, si se ha bloqueado un dominio completo, debe revisarlos para comprobar si podría estar causando falsos positivos. Vea la [configuración de sus directivas de filtro de correo no deseado](https://go.microsoft.com/fwlink/?LinkId=534136)y desactivar la opción adicional de [Opciones de filtrado avanzadas correo no deseado](https://go.microsoft.com/fwlink/?LinkId=534137) que pueden impedir que los mensajes que se marcará como correo no deseado. 
  
## <a name="help-your-end-users-create-a-safe-sender-list-to-prevent-good-email-from-being-marked-as-spam"></a>Ayudar a los usuarios finales a crear una lista de remitentes seguros para evitar que el correo electrónico buena se marquen como correo no deseado
<a name="BKMK_email-user-help-safelist"> </a>

Indique a los usuarios para agregar las direcciones de los remitentes que confían a su lista de remitentes seguros en [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) o [Outlook en el Web](https://go.microsoft.com/fwlink/p/?LinkId=294862). Para empezar a en Outlook en el Web, elija **configuración**![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \> **Opciones de** \> **Bloquear o permitir**. El siguiente diagrama muestra un ejemplo de cómo agregar algo a una lista de remitentes seguros.
  
![Adición de un remitente seguro en Outlook Web App](media/8de6b24e-429e-4e8f-8ce8-53ba659cbfcb.png)
  
Los usuarios remitentes seguros y destinatarios, pero no los dominios seguros respeta la elevación de privilegios. Esto es true, independientemente de si el dominio se agrega a través de Outlook en la Web o agregado en Outlook y sincroniza mediante la sincronización de Active Directory.
  
## <a name="troubleshooting-a-message-ends-up-in-the-junk-folder-even-though-eop-marked-the-message-as-non-spam"></a>Solución de problemas: Un mensaje termina en la carpeta de correo no deseado, aunque EOP marca el mensaje como no correo no deseado
<a name="TroubleshootingJunkEOPNonSpam"> </a>

Si los usuarios tienen la opción en Outlook habilitado para "listas seguras sólo: sólo correo de personas o dominios de la lista de remitentes seguros o la lista de destinatarios seguros se entregarán en la Bandeja de entrada", a continuación, todos los correos electrónicos se vaya a la carpeta no deseada para un remitente a menos que el remitente está en la reci lista de remitentes seguros del pient. Esto ocurrirá independientemente de si EOP marca un mensaje como no correo no deseado, o si ha configurado una regla en EOP para marcar un mensaje como no correo no deseado.
  
Puede deshabilitar la opción sólo listas seguras para los usuarios de Outlook siguiendo las instrucciones que aparecen en [Outlook: configuración de directiva para deshabilitar la interfaz de usuario de correo electrónico no deseado y el mecanismo de filtrado](https://support.microsoft.com/en-us/kb/2180568).
  
Si ve el mensaje en Outlook en el Web, habrá una sugerencia de seguridad amarillo que indica que el mensaje se encuentra en la carpeta de correo no deseado debido a que el remitente no está en la lista de remitentes seguros del destinatario.
  
Si examina el encabezado de un mensaje, puede incluir la marca sfv: skn (direcciones IP permitidas o permitir ETR) o SFV:NSPM (que no sean el correo no deseado), pero aún se sitúa el mensaje en la carpeta del usuario no deseado. No hay nada en el encabezado del mensaje que indica que el usuario tiene "Sólo listas seguras" habilitado. Esto sucede debido a que la opción "Sólo listas seguras" establecer por los usuarios de Outlook reemplaza la configuración de elevación de privilegios. 
  
 **Para comprobar por qué un mensaje de un remitente seguro se marca como no deseado en el encabezado del mensaje, pero que todavía extremos en la carpeta de correo no deseado del usuario**
  
1. Para obtener información sobre cómo conectarse a Exchange Online PowerShell, vea [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). 
    
2. Ejecute el siguiente comando para ver las opciones de configuración de correo electrónico no deseado del usuario:
    
  ```
  Get-MailboxJunkEmailConfiguration example@contoso.com | fl TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
  ```

    Si TrustedListsOnly está establecida en True, significa que esta opción está habilitada. Si ContactsTrusted está establecida en True, significa que el usuario confía en los contactos y remitentes seguros. El TrustedSendersAndDomains enumera el contenido de la lista de remitentes seguros del usuario.
    
## <a name="still-need-help"></a>¿Aún necesita ayuda?
<a name="TroubleshootingJunkEOPNonSpam"> </a>

[![Obtener ayuda en los foros de la comunidad de Office 365](media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![Administradores: Iniciar sesión y crear una solicitud de servicio](media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![Administradores: Llamar al soporte técnico](media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  
## <a name="see-also"></a>Vea también
<a name="TroubleshootingJunkEOPNonSpam"> </a>

[Información general del filtro de correo no deseado](https://support.office.com/article/5AE3EA8E-CF41-4FA0-B02A-3B96E21DE089)
  
[Bloquear o permitir (configuración de correo electrónico no deseado)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46)
  
[Bloquear el correo no deseado con el filtro de correo no deseado de Office 365 para evitar problemas de negativos falsos](block-email-spam-to-prevent-false-negatives.md)


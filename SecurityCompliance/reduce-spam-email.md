---
title: Reducir el correo no deseado en Office 365
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 07824c51-2c45-4005-8596-03c0d7c4ff2a
description: Obtenga información sobre las formas más comunes de reducir el correo masivo y el correo no deseado en Office 365.
ms.openlocfilehash: e462bbb11862d795650b6378cd5de2681f0edf74
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536275"
---
# <a name="how-to-reduce-spam-email-in-office-365"></a>Reducir el correo no deseado en Office 365

 **¿Recibe demasiado correo no deseado en Office 365? Siga este procedimiento.**
  
Muchos de los problemas relacionados con el correo no deseado en Office 365 pueden solucionarse si se [analizan los encabezados de mensaje de correo electrónico](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c) y se determina cuál fue el problema. Si ve un encabezado de mensaje llamado X-Forefront-Antispam-Report que contiene la cadena SFV:NSPM, quiere decir que Exchange Online Protection (EOP) analizó el mensaje y determinó que no era correo no deseado. En ese caso, es muy recomendable que [use el complemento Denunciar mensaje](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) para ayudarnos a mejorar nuestros filtros. Si no ve este valor en los encabezados, puede que no se realizara un análisis de correo no deseado del mensaje, o bien se produjo un problema de configuración que causó que el mensaje omitiera. En este caso, vea la información siguiente. 
  
Obtenga más información sobre los [encabezados de mensaje contra correo no deseado](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx).
  
## <a name="solutions-to-common-causes-of-getting-too-much-spam"></a>Soluciones para causas comunes de recibir demasiado correo no deseado

Para impedir que se reciba demasiado correo no deseado, Exchange Online Protection (EOP) necesita que los administradores completen algunas tareas. Si no es el administrador de su espacio empresarial de Office 365 y recibe demasiado correo no deseado, le recomendamos que trabaje con su administrador en relación con estas tareas. De lo contrario, puede ir directamente a la sección para usuarios.
  
### <a name="for-admins"></a>Para administradores

- **Apuntar los registros DNS a Office 365** Para que EOP proporcione protección, los registros DNS del agente de intercambio de correo (MX) de todos los dominios tienen que apuntar a Office 365 (y únicamente a Office 365). Si los [registros MX no apuntan a Office 365](https://blogs.msdn.microsoft.com/tzink/2017/12/28/if-you-use-office-365-but-your-mx-record-doesnt-point-to-office-you-may-want-to-close-down-your-security-settings/), EOP no proporcionará el filtrado de correo no deseado para los usuarios. Vea [Crear registros DNS para Office 365 al administrar los registros DNS](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).
    
- **Habilitar la regla de correo no deseado en todos los buzones** De forma predeterminada, la acción de filtrado de correo no deseado se establece en **Mover el mensaje a la carpeta de correo no deseado**. Si esta es la acción de directiva contra correo no deseado preferida y actual, cada buzón también [necesita tener habilitada la regla de correo masivo](https://blogs.msdn.microsoft.com/tzink/2017/12/14/making-sure-your-junk-email-filtering-is-enabled-in-office-365/). Para comprobarlo, ejecute el cmdlet Get-MailboxJunkEmailConfiguration en uno o más buzones. Por ejemplo, para comprobar esto en todos los buzones, ejecute lo siguiente: Get-MailboxJunkEmailConfiguration -Identity \* | Where {$_.Enabled -eq $false}
    
    Al ver el resultado, el valor de la propiedad Enable tiene que ser True. Si está establecida en False, ejecute Set-MailboxJunkEmailConfiguration para cambiarla a True.
    
- **Comprobar las reglas de flujo del correo y las listas seguras** Examine el encabezado de un mensaje que tendría que haberse marcado como correo no deseado. Busque la propiedad SCL en el encabezado X-Forefront-Antispam-Report. Si el valor de SCL es -1, esto indica que el mensaje se agregó a la lista segura y omitió el filtrado de correo no deseado de EOP. Investigue las reglas de flujo del correo, las listas de permitidos y la lista de remitentes permitidos de los destinatarios. [Buscar y corregir problemas de entrega de correo electrónico como administrador de Office 365](https://support.office.com/article/e7758b99-1896-41db-bf39-51e2dba21de6) para empresas también resultará útil para proporcionar detalles sobre los motivos por los que un mensaje recibió un SCL de -1. 
    
- **Crear reglas de flujo del correo en un servidor Exchange local** Si usa Exchange Online Protection, pero los buzones se encuentran en un servidor Exchange local, tendrá que crear un par de reglas de flujo del correo en el servidor Exchange local. Vea las [instrucciones para EOP solo](https://technet.microsoft.com/library/ms.exch.eac.EditAntispamPolicy_SpamAction%28EXCHG.150%29.aspx?v=15.20.548.14&amp;l=1&amp;s=BPOS_S_E15_0).
    
- **Marcar correo masivo como correo no deseado** El correo masivo es el correo electrónico al que puede que los usuarios se suscribieran, pero se sigue considerando correo no deseado. En el encabezado de mensaje, busque la propiedad BCL (nivel de confianza en masa) en el encabezado X-Microsoft-Antispam. Si el valor de BCL es inferior al umbral establecido en el filtro de correo no deseado, puede ajustar el umbral para que, en su lugar, marque estos tipos de mensajes masivos como correo no deseado. Diferentes usuarios tienen distintas tolerancias y preferencias para la [administración del correo masivo](https://blogs.msdn.microsoft.com/tzink/2014/08/25/different-levels-of-bulk-mail-filtering-in-office-365/). Puede crear distintas directivas o reglas para diferentes preferencias de usuario. 
    
- **Bloquear inmediatamente un remitente** Si necesita bloquear de forma inmediata un remitente, puede bloquearlo por dirección de correo electrónico, dominio o dirección IP. Vea [Bloquear el correo no deseado con el filtro contra correo no deseado de Office 365 para evitar problemas de falsos negativos](block-email-spam-to-prevent-false-negatives.md). Una entrada en una lista de permitidos del usuario final puede invalidar un bloqueo establecido por el administrador.
    
- **Activar el complemento Denunciar mensaje para los usuarios** Es muy recomendable que [habilite el complemento Denunciar mensaje para los usuarios](enable-the-report-message-add-in.md). Como administrador, es posible que también pueda ver los comentarios que los usuarios envían y usar cualquier patrón para ajustar la configuración que pueda estar causando problemas.
    
### <a name="for-users"></a>Para usuarios

- **Habilitar la regla de correo no deseado y comprobar la lista de permitidos** Compruebe que la regla de acción de correo no deseado esté habilitada y que el remitente o el dominio del remitente no se estableciera para omitirlo en la lista de permitidos personal. La mejor forma de obtener acceso a estas opciones de configuración es desde [Bloquear o permitir (configuración de correo electrónico no deseado)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46). Desde allí, también puede bloquear el dominio o la dirección de correo electrónico del remitente.
    
- **Denunciar correo no deseado a Microsoft** Informe de los mensajes de correo no deseado a Microsoft con el [complemento Denunciar mensaje](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Además, también puede enviar un mensaje a junk@office365.microsoft.com y adjuntar uno o más mensajes al informe.
    
    **Importante** Si no reenvía los mensajes como datos adjuntos, [no se incluirán los encabezados y no podremos mejorar](https://blogs.msdn.microsoft.com/tzink/2017/11/30/when-creating-support-tickets-about-spam-be-sure-to-include-message-headers/) el filtrado de correo no deseado en Office 365. 
    
- **Cancelar la suscripción de correo masivo** Si el mensaje era algo para lo que se registró (boletines, anuncios de productos, etc.) y contiene un vínculo para cancelar la suscripción de un origen confiable, simplemente puede cancelar la suscripción. Office 365 no suele considerar estos mensajes como correo no deseado. También puede bloquear el remitente o pedirle al administrador que realice un cambio que cause que todo el correo masivo se considere correo no deseado. 
    


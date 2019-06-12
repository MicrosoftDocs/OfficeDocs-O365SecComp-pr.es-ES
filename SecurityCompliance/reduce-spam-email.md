---
title: Reducir el correo no deseado en Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: 07824c51-2c45-4005-8596-03c0d7c4ff2a
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_IP
description: Obtenga información sobre las formas más comunes de reducir el correo masivo y el correo no deseado en Office 365.
ms.openlocfilehash: 6603b5a3efdfb6ffde0743d3b674ca69ca39eaa0
ms.sourcegitcommit: 5a93c2f3df35d06a59a7fbaff5c91f7afde11781
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857600"
---
# <a name="how-to-reduce-spam-email-in-office-365"></a>Reducir el correo no deseado en Office 365

 **¿Recibe demasiado correo no deseado en Office 365? Siga este procedimiento.**
  
Se recomienda informar de los mensajes que constituyan falsos negativos [usando el complemento Denunciar mensaje](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) para ayudarnos a mejorar nuestros filtros. Además, puede reenviar el mensaje *como elemento adjunto* a junk@office365.microsoft.com o a phish@office365.microsoft.com (si se trataba de suplantación de identidad).

> [!TIP]
> Si cree que el mensaje es correo no deseado y está en la carpeta Correo no deseado, esto no debería suponer un problema. Si no desea que aparezca en ninguna parte del buzón, debe cambiar la directiva contra correo no deseado para poner el mensaje en cuarentena. Encontrará más información acerca de poner un mensaje en cuarentena en [Quarantine email messages in Office 365](quarantine-email-messages.md) (Poner mensajes de correo electrónico en cuarentena en Office 365).

## <a name="fixing-allowed-spam"></a>Se ha solucionado el correo no deseado permitido

A menudo vemos que los clientes reciben correo no deseado en su bandeja de entrada debido a configuraciones incorrectas. La más común es configurar los dominios en una regla de flujo de correo (también conocida como regla de transporte) que permite omitir los filtros o incluir su dominio o dominios en la lista de remitentes permitidos o seguros. Esto no es conveniente porque estos mensajes omiten el filtrado contra correo no deseado cuando se podrían haber filtrado.  

## <a name="solutions-to-other-common-causes-of-getting-too-much-spam"></a>Soluciones para otras causas comunes de la recepción de demasiado correo no deseado

Para impedir que se reciba demasiado correo no deseado, Exchange Online Protection (EOP) necesita que los administradores completen algunas tareas. Si no es el administrador de su espacio empresarial de Office 365 y recibe demasiado correo no deseado, le recomendamos que trabaje con su administrador en relación con estas tareas. De lo contrario, puede ir directamente a la sección para usuarios.
  
### <a name="for-admins"></a>Para administradores

- **Apuntar los registros DNS a Office 365** Para que EOP proporcione protección, los registros DNS del agente de intercambio de correo (MX) de todos los dominios tienen que apuntar a Office 365 (y únicamente a Office 365). Vea [Crear registros DNS para Office 365 al administrar los registros DNS](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).
    
- 
  **Habilitar la regla de correo no deseado en todos los buzones** De forma predeterminada, la acción de filtrado de correo no deseado se establece en **Mover el mensaje a la carpeta de correo no deseado**. Si esta es la acción de directiva contra correo no deseado preferida y actual, cada buzón también [necesita tener habilitada la regla de correo masivo](https://support.office.com/es-ES/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). Para comprobarlo, ejecute el cmdlet Get-MailboxJunkEmailConfiguration en uno o más buzones. Por ejemplo, para comprobar esto en todos los buzones, ejecute lo siguiente: Get-MailboxJunkEmailConfiguration -Identity \* | Where {$_.Enabled -eq $false}
    
    Cuando se visualiza el resultado, la propiedad Enable debe ser True. Si es False, puede ejecutar Set-MailboxJunkEmailConfiguration para cambiarla a True de la siguiente manera: Set-MailboxJunkEmailConfiguration -Identity $values.UserPrincipalName -Enabled $true.
    
- **Crear reglas de flujo del correo en un servidor Exchange local** Si usa Exchange Online Protection, pero los buzones se encuentran en un servidor Exchange local, tendrá que crear un par de reglas de flujo del correo en el servidor Exchange local. Vea las [instrucciones para EOP solo](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj900470(v=exchg.150)).
    
- 
  **Marcar correo masivo como correo no deseado** El correo masivo es el correo electrónico al que puede que los usuarios se suscribieran, pero se sigue considerando correo no deseado. En el encabezado de mensaje, busque la propiedad BCL (nivel de confianza en masa) en el encabezado X-Microsoft-Antispam. Si el valor de BCL es inferior al umbral establecido en el filtro de correo no deseado, puede ajustar el umbral para que, en su lugar, marque estos tipos de mensajes masivos como correo no deseado. Diferentes usuarios tienen distintas tolerancias y preferencias para la [administración del correo masivo](https://docs.microsoft.com/es-ES/office365/SecurityCompliance/bulk-complaint-level-values). Puede crear distintas directivas o reglas para diferentes preferencias de usuario. 
    
- **Bloquear inmediatamente un remitente** Si necesita bloquear de forma inmediata un remitente, puede hacerlo por dirección de correo electrónico, dominio o dirección IP. Vea [Crear listas de remitentes bloqueados en Office 365](create-block-sender-lists-in-office-365.md). Una entrada en una lista de permitidos del usuario final puede invalidar un bloqueo establecido por el administrador.
    
- **Activar el complemento Denunciar mensaje para los usuarios** Es muy recomendable que [habilite el complemento Denunciar mensaje para los usuarios](enable-the-report-message-add-in.md). Como administrador, es posible que también pueda ver los comentarios que los usuarios envían y usar cualquier patrón para ajustar la configuración que pueda estar causando problemas.
- **Habilitar [DKIM](use-dkim-to-validate-outbound-email.md)** para firmar todos los mensajes salientes e incrementar la seguridad de su dominio y espacio empresarial.
 > [!TIP]
> Después de habilitar DKIM, debe habilitar [DMARC](use-dkim-to-validate-outbound-email.md) ya que este registro validará si DKIM y SPF funcionan correctamente y, por lo general, los correos electrónicos falsificados no tienen la firma, dado que O365 administra su clave simétrica pública y privada.
    
### <a name="for-users"></a>Para usuarios

- **Habilitar la regla de correo no deseado y comprobar la lista de permitidos** Compruebe que la regla de acción de correo no deseado esté habilitada y que el remitente o el dominio del remitente no se estableciera para omitirlo en la lista de permitidos personal. La mejor forma de obtener acceso a estas opciones de configuración es desde [Bloquear o permitir (configuración de correo electrónico no deseado)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46). Desde allí, también puede bloquear el dominio o la dirección de correo electrónico del remitente.
    
- **Denunciar correo no deseado a Microsoft** Informe de los mensajes de correo no deseado a Microsoft con el [complemento Denunciar mensaje](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Además, también puede enviar un mensaje a junk@office365.microsoft.com y adjuntar uno o más mensajes al informe.
    
    **Importante** Si no reenvía los mensajes como datos adjuntos, no se incluirán los encabezados y no podremos mejorar el filtrado de correo no deseado en Office 365. 
    
- **Cancelar la suscripción de correo masivo** Si el mensaje era algo para lo que se registró (boletines, anuncios de productos, etc.) y contiene un vínculo para cancelar la suscripción de un origen confiable, simplemente puede cancelar la suscripción. Office 365 no suele considerar estos mensajes como correo no deseado. También puede bloquear el remitente o pedirle al administrador que realice un cambio que cause que todo el correo masivo se considere correo no deseado.

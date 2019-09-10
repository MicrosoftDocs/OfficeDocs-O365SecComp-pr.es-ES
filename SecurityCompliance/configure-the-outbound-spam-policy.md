---
title: Configurar notificaciones de directivas de correo no deseado salientes en Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/10/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a modificar la configuración de notificaciones para detecciones de correo no deseado de salida en Office 365.
ms.openlocfilehash: c48b6cd634417a00040fb5479313782b44f6aa8d
ms.sourcegitcommit: 81b3bff27bc60235a38004c5b0297ac454331b25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "36822520"
---
# <a name="configure-outbound-spam-policy-notifications-in-office-365"></a>Configurar notificaciones de directivas de correo no deseado salientes en Office 365

El filtrado de correo no deseado saliente siempre está habilitado si utiliza el servicio para enviar correo electrónico saliente, lo que protege a las organizaciones que utilizan el servicio y sus destinatarios. De manera similar al filtrado entrante, el filtrado de correo no deseado saliente está compuesto por el filtro de conexión y el filtro de contenido; no obstante, no es posible configurar el filtrado saliente. Si se determina que un mensaje saliente es correo no deseado, este se enruta mediante el grupo de entrega de mayor riesgo, que reduce la probabilidad de que el grupo de IP saliente normal se agregue a una lista de bloqueo. Si un cliente continúa enviando correo no deseado saliente mediante el servicio, su envío de mensajes se bloqueará.

Aunque no puede deshabilitar ni cambiar el filtrado de correo no deseado saliente, puede configurar las siguientes opciones de notificación de correo no deseado saliente:

- **Enviar copias de mensajes sospechosos**: estos mensajes se marcan como correo no deseado (independientemente de la clasificación de SCL) y el filtro no los rechaza, pero se redirigen a través del grupo de entrega de mayor riesgo. Puede usar el centro de administración de Exchange (EAC) o ** \*** los cmdlets-HostedOutboundSpamFilterPolicy en Exchange Online PowerShell o Exchange Online Protection PowerShell para especificar destinatarios adicionales para estos mensajes detectados. Tenga en cuenta que los destinatarios se agregan como destinatarios **CCO** (los campos **desde** y **para** son el remitente y el destinatario originales).

- **Enviar notificaciones cuando se bloquea un remitente**: cuando hay una cantidad significativa de correo no deseado procedente de un usuario en particular, el usuario está deshabilitado para enviar mensajes de correo electrónico. Los administradores reciben una notificación de forma predeterminada, pero puede usar el **usuario restringido del envío de** la [Directiva de alerta](alert-policies.md) de correo electrónico en el centro de cumplimiento de & de seguridad de Office 365 para configurar destinatarios de notificaciones adicionales.

  Para ver el aspecto que tiene esta notificación, véase [Notificación de muestra cuando se bloquea a un remitente para enviar correo no deseado de salida](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md). Para obtener información sobre cómo volver a habilitar a un usuario, consulte [Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Tiempo estimado para finalizar: 5 minutos

- Para abrir el Centro de seguridad y cumplimiento, vea [Ir al Centro de seguridad y cumplimiento de Office 365](go-to-the-securitycompliance-center.md).

- Para abrir el EAC, consulte [centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) o [Exchange admin Center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).

- Para abrir PowerShell de Exchange Online, vea [conectarse a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Para abrir PowerShell de Exchange Online Protection, vea [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell).

- La cuenta debe tener permisos asignados para poder realizar este procedimiento. Para ver qué permisos necesita, consulte la entrada de la función "Administrar alertas" en [permisos en el centro de seguridad & cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md).

## <a name="use-the-eac-to-configure-additional-recipients-for-outbound-spam-messages"></a>Usar el EAC para configurar destinatarios adicionales para los mensajes de correo no deseado saliente

1. En el EAC, vaya a **protección** \> **contra correo no deseado**de protección.

2. Seleccione la Directiva denominada **predeterminada**y, a continuación, haga clic](media/ITPro-EAC-EditIcon.png)en **Editar** ![icono de edición.

3. En la página de propiedades que se abre, compruebe que la pestaña **preferencias de correo no deseado saliente** está seleccionada y, a continuación, configure las siguientes opciones:

   **Envíe una copia de todos los mensajes de correo electrónico saliente sospechosos a las siguientes direcciones o**direcciones de correo electrónico: Active la casilla y escriba las direcciones de correo electrónico de uno o más administradores que se deben agregar al campo **CCO** de los mensajes detectados. Separe varias direcciones de correo electrónico con un punto y coma (;).

   Cuando haya terminado, haga clic en **Guardar**.

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-additional-recipients-for-outbound-spam-messages"></a>Usar Exchange Online PowerShell o Exchange Online Protection PowerShell para configurar destinatarios adicionales para los mensajes de correo no deseado salientes

Para habilitar y configurar destinatarios adicionales para los mensajes de correo no deseado salientes, use la siguiente sintaxis:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundMail $true -BccSuspiciousOutboundAdditionalRecipients <recipients>
```

- Para especificar los destinatarios que sobrescriben todos los valores existentes, use `emailaddress1,emailaddress2,...emailaddressN`la sintaxis.

- Para agregar o quitar selectivamente los destinatarios sin que ello afecte a las demás entradas `@{Add="\<emailaddress1\>","\<emailaddress2\>"...; Remove="\<emailaddress1\>","\<emailaddress2\>"...}`, use la sintaxis.

En este ejemplo se habilitan y configuran chris@contoso.com, laura@contoso.com y julia@contoso.com como destinatarios CCO para los mensajes de correo no deseado saliente.

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundMail $true -BccSuspiciousOutboundAdditionalRecipients chris@contoso.com,laura@contoso.com,julia@contoso.com
```

En este ejemplo se agrega michelle@contoso.com como un destinatario de CCO adicional.

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundAdditionalRecipients @{Add=michelle@contoso.com}
```

En este ejemplo se quitan chris@contoso.com y julia@contoso.com de la lista de destinatarios CCO.

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundAdditionalRecipients @{Remove='chris@contoso.com','julia@contoso.com'}
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).

**Nota**: Ejecute el comando `Get-HostedOutboundSpamFilterPolicy | Format-List` para ver los valores actuales de las propiedades *BccSuspiciousOutboundMail* y *BccSuspiciousOutboundAdditionalRecipients* .

## <a name="use-the-security--compliance-center-to-configure-notifications-when-a-sender-is-blocked"></a>Usar el centro de seguridad & cumplimiento para configurar las notificaciones cuando se bloquea un remitente

1. En el centro de seguridad & cumplimiento, vaya a **directivas de alerta**de **alertas** \> .

2. Busque y seleccione la Directiva denominada **usuario con restricción de envío de correo electrónico**.

3. En la volando que se abre, haga clic en **Editar Directiva**.

4. En la página **Editar destinatarios** que aparece, configure las siguientes opciones:

   - **Enviar notificaciones por correo electrónico**: **Compruebe que está** seleccionada.

   - **Destinatarios de correo electrónico**: de forma predeterminada **TenantAdmins** es el único valor aquí. Para agregar más destinatarios, haga clic en un punto vacío en este cuadro, empiece a escribir el destinatario y seleccione el destinatario cuando se resuelva el nombre. Para quitar destinatarios, haga clic en la **X** junto a sus nombres.

   - **Límite de notificación diario**: el valor predeterminado es **sin límite**, pero puede configurar varios límites entre 1 y 200.

   Cuando haya terminado, haga clic en **Guardar**.

## <a name="for-more-information"></a>Más información

[Grupo de entrega de alto riesgo para mensajes salientes](high-risk-delivery-pool-for-outbound-messages.md)

[Preguntas más frecuentes sobre protección contra correo no deseado](anti-spam-protection-faq.md)

---
title: 'Purga automática cero horas: protección contra correo no deseado y malware'
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: La depuración automática de cero horas (ZAP) es una característica de protección de correo electrónico que detecta los mensajes con correo no deseado o malware que ya se han entregado a los buzones de los usuarios y, a continuación, inofensivos en el contenido malintencionado. Cómo hace ZAP esto depende del tipo de contenido malintencionado detectado.
ms.openlocfilehash: b49f7e3b5effec7b67daf6ab8acbf049705a4841
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670585"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>Purga automática cero horas: protección contra correo no deseado y malware

## <a name="overview"></a>Información general

La purga automática de cero horas (ZAP) es una característica de protección de correo electrónico que detecta los mensajes con phish, correo no deseado o malware que ya se han entregado a los buzones de los usuarios y, a continuación, inofensivos en el contenido malintencionado. Cómo hace ZAP esto depende del tipo de contenido malintencionado detectado; el correo se puede zapped debido al contenido de correo, las direcciones URL o los datos adjuntos.
  
ZAP está disponible con la protección de Exchange Online predeterminada que se incluye con cualquier suscripción a Office 365 que contenga buzones de correo de Exchange Online.

ZAP está activado de forma predeterminada, pero deben cumplirse las siguientes condiciones:
  
- La **acción de correo no deseado** está configurada para **mover el mensaje a la carpeta correo no deseado**. <br/>También puede crear una nueva Directiva de filtro de correo no deseado que se aplique sólo a un grupo de usuarios si no desea que ZAP pueda filtrar todos los buzones.

- Los usuarios han mantenido su configuración predeterminada de correo no deseado y no han desactivado la protección contra correo electrónico no deseado. (Consulte [cambiar el nivel de protección en el filtro de correo no deseado](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b) para obtener más información acerca de las opciones de usuario en Outlook). 
  
## <a name="how-does-zap-work"></a>¿Cómo funciona el ZAP?

Office 365 actualiza las firmas de malware y del motor de correo no deseado en tiempo real de manera diaria. Sin embargo, es posible que los usuarios sigan teniendo mensajes malintencionados entregados a sus bandejas de correo por diversos motivos, incluso si el contenido se ha armado después de que se entregue a los usuarios. ZAP soluciona el control continuado de las actualizaciones de las firmas de correo no deseado y malware de Office 365. ZAP puede buscar y quitar los mensajes previamente entregados que ya se encuentran en las bandejas de los usuarios. 

- En el caso del correo identificado como correo no deseado, ZAP mueve los mensajes no leídos a la carpeta de correo no deseado de los usuarios. 

- En el caso del correo identificado como phish, ZAP mueve los mensajes a la carpeta de correo no deseado de los usuarios, independientemente de si el correo electrónico se ha leído.

- Para el malware recién detectado, ZAP quita los datos adjuntos de los mensajes de correo electrónico, independientemente de si el correo electrónico se ha leído. 
  
La acción ZAP es fluida para el usuario del buzón de correo; no se notifica si se mueve un mensaje de correo electrónico.
  
Las listas de permitidos, [las reglas de flujo de correo](https://go.microsoft.com/fwlink/p/?LinkId=722755)y las reglas de usuario final o los filtros adicionales tienen prioridad sobre Zap.
  
## <a name="to-review-or-set-up-a-spam-filter-policy"></a>Para revisar o configurar una directiva de filtro de correo no deseado
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa para Office 365.

2. En **Administración de amenazas**, elija **anti-spam**.

3. Revise la configuración estándar. 

4. Si desea personalizar la configuración, seleccione la pestaña **personalizado** y active la **Configuración personalizada**. Modifique la configuración y, si quiere, elija **+ crear una directiva** para agregar una nueva Directiva. 
    
## <a name="to-see-if-zap-moved-your-message"></a>Para ver si ZAP movió el mensaje

Si desea ver si el mensaje se movió a un ZAP, puede usar el [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report) (o el [Explorador de amenazas](use-explorer-in-security-and-compliance.md)).
    
## <a name="to-disable-zap"></a>Para deshabilitar ZAP
  
Si desea deshabilitar ZAP para el inquilino de Office 365 o un conjunto de usuarios, use el parámetro **ZapEnabled** de [set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), un cmdlet de EOP.
    
En el siguiente ejemplo, se deshabilita ZAP para una directiva de filtro de contenido denominada "Test".
    
```Powershell
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

## <a name="faq"></a>Preguntas frecuentes

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>¿Qué sucede si un mensaje legítimo se mueve a la carpeta correo no deseado?
  
Debe seguir el proceso normal de informes para [falsos positivos](prevent-email-from-being-marked-as-spam.md). La única razón por la que el mensaje se movería de la bandeja de entrada a la carpeta correo no deseado sería porque el servicio determinó que el mensaje era correo no deseado o malintencionado.
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>¿Qué ocurre si utilizo la cuarentena de Office 365 en lugar de la carpeta de correo no deseado?
  
ZAP no mueve los mensajes a cuarentena de la bandeja de entrada en este momento.
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>¿Qué ocurre si tengo una regla de flujo de correo personalizada (regla de bloqueo/permiso)?
  
Las reglas creadas por los administradores (reglas de flujo de correo) o las reglas de bloqueo y permiso tienen prioridad. Estos mensajes se excluyen de los criterios de la característica, por lo que el flujo de correo seguirá la acción de regla (bloquear/permitir regla).
  
## <a name="related-topics"></a>Temas relacionados

[Protección contra correo no deseado de Office 365](anti-spam-protection.md)
  
[Bloquear el correo no deseado con el filtro de correo no deseado de Office 365 para evitar problemas de negativos falsos](reduce-spam-email.md)
  


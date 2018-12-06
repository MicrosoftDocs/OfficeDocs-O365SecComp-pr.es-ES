---
title: 'Purga automática cero horas: protección contra correo no deseado y malware'
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
description: Purgar cero horas automático (ZAP) es una característica de protección de correo electrónico que detecta los mensajes con el correo no deseado o malware que ya se han entregado a las bandejas de entrada de los usuarios y, a continuación, representa el contenido malintencionado inocua. ZAP ¿cómo esto depende del tipo de contenido malintencionado detectado.
ms.openlocfilehash: 1cf14051e91801a74a0d739c69900bb3f825b318
ms.sourcegitcommit: 204fb0269b5c10b63941055824e863d77e3e9b02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2018
ms.locfileid: "27180850"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>Purga automática cero horas: protección contra correo no deseado y malware

## <a name="overview"></a>Información general

Purgar cero horas automático (ZAP) es una característica de protección de correo electrónico que detecta los mensajes con phishing, spam o malware que ya se han entregado a las bandejas de entrada de los usuarios y, a continuación, representa el contenido malintencionado inocua. ¿Cómo ZAP hace esto depende del tipo de contenido malintencionado detectado; Puede que haya que hacerlo correo debido a contenido de correo, las direcciones URL o los datos adjuntos.
  
ZAP está disponible con el valor predeterminado de Exchange Online Protection que se incluye con cualquier suscripción de Office 365 que contiene los buzones de Exchange Online.

ZAP está activado de forma predeterminada, pero se deben cumplir las condiciones siguientes:
  
- **Acción de spam** se establece para **mover el mensaje a la carpeta correo no deseado**. <br/>También puede crear una nueva directiva de filtro de spam que sólo se aplica a un conjunto de usuarios si no desea que todos los buzones que se filtran por ZAP.

- Los usuarios conservan su valor predeterminado configuración del correo electrónico no deseado y no han desactivado de protección de correo electrónico no deseado. (Para obtener información detallada acerca de las opciones de usuario en Outlook, vea [cambiar el nivel de protección en el filtro de correo electrónico no deseado](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b) ). 
  
## <a name="how-does-zap-work"></a>¿Cómo funciona ZAP?

Las firmas de motor y malware contra correo no deseadas en las actualizaciones de Office 365 en tiempo real de manera diaria. Sin embargo, los usuarios aún es posible que obtenga malintencionados mensajes entregados a sus bandejas de entrada para una variedad de motivos, incluido si el contenido se weaponized después de que se envía a los usuarios. ZAP soluciona este problema mediante la supervisión de forma continua las actualizaciones de las firmas de correo no deseado y malware de Office 365. ZAP puede buscar y quitar mensajes entregados que ya están en las bandejas de entrada de los usuarios. 

- Para el correo que se identifica como correo no deseado, ZAP mueve mensajes no leídos a la carpeta de correo electrónico no deseado de los usuarios. 

- Para el correo que se identifica como correo no deseado, ZAP mueve los mensajes a la carpeta de correo electrónico no deseado de los usuarios, independientemente de si se ha leído el correo electrónico.

- Para recién detectado malware, ZAP quita los datos adjuntos de mensajes de correo electrónico, independientemente de si se ha leído el correo electrónico. 
  
La acción ZAP es transparente para el usuario del buzón; no se notifica sobre esto si se mueve un mensaje de correo electrónico.
  
Permitir listas, [reglas de flujo de correo](https://go.microsoft.com/fwlink/p/?LinkId=722755)y las reglas de usuario final o filtros adicionales tienen prioridad sobre ZAP.
  
## <a name="to-review-or-set-up-a-spam-filter-policy"></a>Para revisar o configurar una directiva de filtro de spam
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e iniciar sesión con su cuenta de trabajo o escuela para Office 365.

2. En **administración de amenaza**, elija **contra correo no deseado**.

3. Revise la configuración estándar. 

4. Si desea personalizar la configuración, seleccione la ficha **personalizado** y activar la **configuración personalizada**. Editar la configuración y si lo desea, elija **+ crear una directiva** para agregar una nueva directiva. 
    
## <a name="to-see-if-zap-moved-your-message"></a>Para ver si ZAP mueve el mensaje

Si desea ver si ZAP mueve el mensaje, puede utilizar ya sea el [informe de estado de protección de amenaza](view-email-security-reports.md#threat-protection-status-report-new) (o [El Explorador de amenaza](use-explorer-in-security-and-compliance.md)).
    
## <a name="to-disable-zap"></a>Para deshabilitar ZAP
  
Si desea deshabilitar eliminar para el inquilino de Office 365, o un conjunto de usuarios, use el parámetro **ZapEnabled** de [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), un cmdlet de elevación de privilegios.
    
En el siguiente ejemplo, ZAP está deshabilitado para una directiva de filtro de contenido denominada "Prueba".
    
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

## <a name="faq"></a>Preguntas más frecuentes

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>¿Qué ocurre si un mensaje legítimo se mueve a la carpeta correo electrónico no deseado?
  
Debe seguir el proceso de generación de informes normal de falsos positivos. La única razón se pasaría el mensaje de la Bandeja de entrada a la carpeta correo electrónico no deseado sería debido a que el servicio ha determinado que el mensaje es correo no deseado o malintencionado.
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>¿Qué ocurre si utilizo la cuarentena de Office 365 en lugar de la carpeta de correo electrónico no deseado?
  
ZAP no mover los mensajes en cuarentena desde la Bandeja de entrada en este momento.
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>¿Qué ocurre si tiene una regla de flujo de correo personalizado (bloquear o permitir regla)?
  
Las reglas creadas por administradores (reglas de flujo de correo) o las reglas de bloqueo y permitir tiene prioridad. Este tipo de mensajes se excluye de los criterios de la característica.
  
## <a name="related-topics"></a>Temas relacionados

[Protección contra correo no deseado de Office 365](anti-spam-protection.md)
  
[Bloquear el correo no deseado con el filtro de correo no deseado de Office 365 para evitar problemas de negativos falsos](block-email-spam-to-prevent-false-negatives.md)
  


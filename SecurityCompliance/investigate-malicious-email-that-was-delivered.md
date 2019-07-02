---
title: Buscar y investigar correo electrónico malintencionado que se entregó (Office 365 de investigación y respuesta de amenazas
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo usar la investigación de amenazas y las capacidades de respuesta para buscar y investigar correo electrónico malintencionado.
ms.openlocfilehash: febcf6704b1ba9dc23bf4e698715fb4b929b998b
ms.sourcegitcommit: d3b2bffa8af5f19d97fe9771068c80705b890e85
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2019
ms.locfileid: "35414810"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-advanced-threat-protection-plan-2"></a>Buscar e investigar correo electrónico malintencionado que se entregó (Office 365 Advanced Threat Protection Plan 2)

[Office 365 Advanced Threat Protection](office-365-atp.md) le permite investigar las actividades que ponen en riesgo a los usuarios y emprender acciones para proteger su organización. Por ejemplo, si forma parte del equipo de seguridad de su organización, puede encontrar e investigar los mensajes de correo electrónico sospechosos que se entregaron a los usuarios. Para ello, puede usar el [Explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md).
  
## <a name="before-you-begin"></a>Antes de comenzar...

Asegúrese de que se cumplen los siguientes requisitos:
  
- Su organización tiene [Office 365 Advanced Threat Protection](office-365-atp.md) (plan 1 o plan 2) y [se asignan licencias a los usuarios](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).
    
- El [registro de auditoría de Office 365](turn-audit-log-search-on-or-off.md) está activado para su organización. 
    
- Su organización tiene directivas definidas para protección contra correo electrónico no deseado, antimalware, antiphishing, etc. Consulte [proteger contra amenazas en Office 365](protect-against-threats.md).
    
- Es un administrador global de Office 365 o bien tiene el rol de administrador de seguridad o de búsqueda y depuración asignado en &amp; el centro de seguridad y cumplimiento. Consulte [permisos en el centro de seguridad &amp; y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md).
    
## <a name="dealing-with-suspicious-emails"></a>Tratar los correos sospechosos

Los atacantes malintencionados pueden enviar correo a sus usuarios para probar y phish sus credenciales y obtener acceso a sus secretos corporativos. Para evitarlo, debe usar los servicios de protección contra amenazas en Office 365, incluidos [Exchange Online Protection](eop/exchange-online-protection-overview.md) y la [protección contra amenazas avanzada](office-365-atp.md). Sin embargo, hay veces en las que un atacante puede enviar correo a los usuarios que contengan una dirección URL y que, más adelante, esta dirección URL apunte a contenido malintencionado (malware, etc.). Como alternativa, es posible que se vea demasiado tarde que un usuario de la organización se ha puesto en peligro y, mientras que el usuario ha estado en peligro, el atacante ha usado esa cuenta para enviar correo electrónico a otros usuarios de la compañía. Como parte de la limpieza de ambos escenarios, es posible que desee quitar los mensajes de correo electrónico de las bandejas de los usuarios. En situaciones como estas, puede aprovechar [el explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md) para buscar y quitar los mensajes de correo electrónico.

## <a name="where-re-routed-emails-are-located-after-actions-are-taken"></a>Dónde se encuentran los mensajes de correo electrónico redistribuidos una vez que se llevan a cabo acciones

Detecciones en tiempo real del explorador de amenazas ha agregado los campos acción de entrega y ubicación de entrega en el estado del lugar de entrega. Esto da como resultado una imagen más completa de dónde se encuentran los correos electrónicos. Parte del objetivo de este cambio es facilitar la búsqueda para los operadores de seguridad, pero el resultado neto es conocer la ubicación de los correos electrónicos con problemas de un vistazo.

El estado de entrega ahora se divide en dos columnas:

- **Acción de entrega** : ¿Cuál es el estado de este correo electrónico?
- **Ubicación de entrega** : ¿Dónde se distribuyó este correo electrónico como resultado?

La acción de entrega es la acción que se realiza en un correo electrónico debido a las directivas o detecciones existentes. Estas son las posibles acciones que puede realizar un correo electrónico:

1. **Delivered** : el correo electrónico se entregó a la bandeja de entrada o a la carpeta de un usuario y el usuario puede acceder a él directamente.
2. Correo electrónico **no deseado** : el correo electrónico se envió a la carpeta de correo no deseado o a la carpeta eliminada del usuario y el usuario tiene acceso a los correos electrónicos en su carpeta de correo no deseado o eliminado.
3. **Bloqueado** : cualquier correo electrónico que esté en cuarentena, que falle o que se haya cancelado. El usuario no tiene acceso completamente a esto.
4. **Reemplazado** : cualquier correo electrónico en el que los datos adjuntos malintencionados se reemplazan por archivos. txt que indican que los datos adjuntos eran malintencionados.
 
Ubicación de entrega muestra los resultados de las directivas y detecciones que se ejecutan después de la entrega. Está vinculado a una acción de entrega. Este campo se agregó para proporcionar información sobre la acción tomada cuando se encuentra un mensaje problemático. Estos son los valores posibles de la ubicación de entrega:

1. **Bandeja de entrada o carpeta** : el correo electrónico se encuentra en la bandeja de entrada o en una carpeta (según las reglas de correo electrónico).
2. Local **o externa** : el buzón de correo no existe en la nube pero es local.
3. **Carpeta de correo no deseado** : el correo electrónico en la carpeta de correo no deseado de un usuario.
4. **Carpeta elementos eliminados** : el correo electrónico de la carpeta elementos eliminados de un usuario.
5. **Cuarentena** : el correo electrónico en cuarentena y no se encuentra en el buzón de un usuario.
6. **Failed** – el correo electrónico no pudo llegar al buzón.
7. **** Perdido: el correo electrónico se pierde en algún lugar del flujo de correo.
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>Buscar y eliminar correo electrónico sospechoso que se entregó

> [!TIP]
> El explorador de amenazas (a veces denominado explorador) es un informe eficaz que puede servir para varios propósitos, como buscar y eliminar mensajes, identificar la dirección IP de un remitente de correo electrónico malintencionado o iniciar un incidente para una mayor investigación. El siguiente procedimiento se centra en usar el explorador para buscar y eliminar correo electrónico malintencionado de los buzones de los destinatarios.

Para ver los cambios en el campo Estado de entrega anterior (ahora acción de entrega y ubicación de entrega): 

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa para Office 365. Esto le llevará al centro de &amp; seguridad y cumplimiento. 
    
2. En el panel de navegación izquierdo, elija **Threat Management** \> **Explorer**.
<!--Comment>
![Threat Explorer with Delivery Action and Delivery Location fields.](media/ThreatExFields.PNG)

    
3. In the View menu, choose **All email**.<br/>![Use the View menu to choose between Email and Content reports](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
4. Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.<br/>![Threat Explorer showing data for all email](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)<br/>(Depending on the actions that were taken on email messages for your organization, you might see additional labels, such as **Blocked** or **Replaced**.)
    
5. In the report, choose **Delivered** to view only emails that ended up in users' inboxes.<br/>![Clicking "Delivered to junk" removes that data from view](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. Below the chart, review the **Email** list below the chart.<br/>![Below the chart, view a list of email messages that were detected](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. In the list, choose an item to view more details about that email message. For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.<br/>![You can view additional information about an item, including details and any attachments](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. After viewing information about email messages, select one or more items in the list to activate **+ Actions**.
    
9. Use the **+ Actions** list to apply an action, such as **Move to deleted** items. This will delete the selected messages from the recipients' mailboxes.<br/>![When you select one or more email messages, you can choose from several available actions](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)
  
-->
## <a name="related-topics"></a>Temas relacionados

[Plan 2 de protección contra amenazas avanzada de Office 365](office-365-ti.md)
  
[Protección contra amenazas en Office 365](protect-against-threats.md)
  
[Ver informes para la protección contra amenazas avanzada de Office 365](view-reports-for-atp.md)
  


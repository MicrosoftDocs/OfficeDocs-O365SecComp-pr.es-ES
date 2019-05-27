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
ms.openlocfilehash: 7e2cef742339e54c094cfb0c3b32fbf596896a3d
ms.sourcegitcommit: 2b46fba650df8d252b1dd2b3c3f080a383183a06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2019
ms.locfileid: "34408305"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-advanced-threat-protection-plan-2"></a>Buscar e investigar correo electrónico malintencionado que se entregó (Office 365 Advanced Threat Protection Plan 2)

La [protección contra amenazas avanzada de Office 365](office-365-atp.md) le permite investigar actividades que pongan en riesgo a los usuarios y emprender acciones para proteger su organización. Por ejemplo, si forma parte del equipo de seguridad de su organización, puede encontrar e investigar los mensajes de correo electrónico sospechosos que se entregaron a los usuarios. Para ello, puede usar el [Explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md).
  
## <a name="before-you-begin"></a>Antes de comenzar...

Asegúrese de que se cumplen los siguientes requisitos:
  
- Su organización tiene [Office 365 Advanced Threat Protection](office-365-atp.md) (plan 1 o plan 2) y [se asignan licencias a los usuarios](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).
    
- El [registro de auditoría de Office 365](turn-audit-log-search-on-or-off.md) está activado para su organización. 
    
- Su organización tiene directivas definidas para protección contra correo electrónico no deseado, antimalware, antiphishing, etc. Consulte [proteger contra amenazas en Office 365](protect-against-threats.md).
    
- Es un administrador global de Office 365 o bien tiene el rol de administrador de seguridad o de búsqueda y depuración asignado en &amp; el centro de seguridad y cumplimiento. Consulte [permisos en el centro de seguridad &amp; y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md).
    
## <a name="dealing-with-suspicious-emails"></a>Tratar los correos sospechosos

Los atacantes malintencionados pueden enviar correo a sus usuarios para probar y phish sus credenciales y obtener acceso a sus secretos corporativos. Para evitar esto, debe usar los servicios de protección contra amenazas ofrecidos por Office 365, incluidos [Exchange Online Protection](eop/exchange-online-protection-overview.md) y la [protección contra amenazas avanzada](office-365-atp.md). Sin embargo, hay veces en las que un atacante puede enviar correo a los usuarios que contengan una dirección URL y que, más adelante, esta dirección URL apunte a contenido malintencionado (malware, etc.). Como alternativa, es posible que se vea demasiado tarde que un usuario de la organización se ha puesto en peligro y, mientras que el usuario ha estado en peligro, el atacante ha usado esa cuenta para enviar correo electrónico a otros usuarios de la compañía. Como parte de la limpieza de ambos escenarios, es posible que desee quitar los mensajes de correo electrónico de las bandejas de los usuarios. En situaciones como estas, puede aprovechar [el explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md) para buscar y quitar los mensajes de correo electrónico.
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>Buscar y eliminar correo electrónico sospechoso que se entregó

> [!TIP]
> El explorador de amenazas (también conocido como explorador) es un eficaz informe que puede servir para varios propósitos, como buscar y eliminar mensajes, identificar la dirección IP de un remitente de correo electrónico malintencionado o iniciar un incidente para una mayor investigación. El siguiente procedimiento se centra en usar el explorador para buscar y eliminar correo electrónico malintencionado de los buzones de los destinatarios. 
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa para Office 365. Esto le llevará al centro de &amp; seguridad y cumplimiento. 
    
2. En el panel de navegación izquierdo, elija **Threat Management** \> **Explorer**.
    
3. En el menú Ver, elija **todo el correo electrónico**.<br/>![Usar el menú Ver para elegir entre los informes de correo electrónico y de contenido](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
4. Observe las etiquetas que aparecen en el informe, como **entregado**, **desconocido**o **entregado a correo no deseado**.<br/>![Explorador de amenazas que muestra datos de todo el correo electrónico](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)<br/>(En función de las acciones realizadas en los mensajes de correo electrónico de su organización, es posible que vea etiquetas adicionales, como **bloqueado** o **reemplazado**.)
    
5. En el informe, seleccione **entregado** para ver solo los correos electrónicos que finalizaron en las bandejas de correo de los usuarios.<br/>![Al hacer clic en "entregado a correo no deseado" se quitan los datos de la vista](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. Debajo del gráfico, revise la lista de **correo electrónico** que hay debajo del gráfico.<br/>![Debajo del gráfico, se muestra una lista de los mensajes de correo electrónico que se detectaron](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. En la lista, elija un elemento para ver más detalles sobre el mensaje de correo electrónico. Por ejemplo, puede hacer clic en la línea de asunto para ver información sobre el remitente, los destinatarios, los datos adjuntos y otros mensajes de correo electrónico similares.<br/>![Puede ver información adicional acerca de un elemento, incluidos los detalles y los datos adjuntos](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. Después de ver la información sobre los mensajes de correo electrónico, seleccione uno o más elementos de la lista para activar **+ acciones**.
    
9. Utilice la lista de **acciones +** para aplicar una acción, como **mover a** elementos eliminados. Se eliminarán los mensajes seleccionados de los buzones de correo de los destinatarios.<br/>![Al seleccionar uno o más mensajes de correo electrónico, puede elegir entre varias acciones disponibles.](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)
  
## <a name="related-topics"></a>Temas relacionados

[Plan 2 de protección contra amenazas avanzada de Office 365](office-365-ti.md)
  
[Protección contra amenazas en Office 365](protect-against-threats.md)
  
[Ver informes para la protección contra amenazas avanzada de Office 365](view-reports-for-atp.md)
  


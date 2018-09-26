---
title: Conservar los destinatarios de grupos de distribución expandidos y CCO para la exhibición de documentos electrónicos
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/19/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: eb8ddf15-0080-457e-9d83-e73e193da334
description: Las directivas de retención de Office 365, juicio y conservación local permiten conservar el contenido de los buzones para satisfacer el cumplimiento de normativas y requisitos de exhibición de documentos electrónicos.
ms.openlocfilehash: 1149834181bca527bd06cea846f455e36fad283c
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038163"
---
# <a name="preserve-bcc-and-expanded-distribution-group-recipients-for-ediscovery"></a>Conservar los destinatarios de grupos de distribución expandidos y CCO para la exhibición de documentos electrónicos
  
[Las directivas de retención de Office 365](http://go.microsoft.com/fwlink/?LinkID=827811) , juicio y conservación local (creado en la seguridad de Office 365 &amp; centro de cumplimiento) permiten conservar el contenido de los buzones para cumplir las normativas de cumplimiento y exhibición de documentos electrónicos. Información acerca de los destinatarios directamente tratadas en para y Cc campos de un mensaje se incluye en todos los mensajes de forma predeterminada, pero es posible que requiere su organización la capacidad de buscar y reproducir detalles acerca de todos los destinatarios de un mensaje. Esto incluye: 
  
- **Destinatarios a los que se dirigió mediante el campo CCO de un mensaje:** los destinatarios CCO se almacenan en el mensaje en el buzón de correo del remitente, pero no se incluyen en los encabezados del mensaje que se entrega a los destinatarios. 
    
- **Destinatarios del grupo de distribución expandido:** destinatarios que reciben el mensaje porque son miembros de un grupo de distribución al que estaba dirigido el mensaje, ya sea en los campos Para, CC o CCO. 
    
Exchange Online y Exchange Server 2013 (actualización acumulativa 7 y versiones posteriores) conservan la información acerca de CCO y los destinatarios del grupo de distribución expandidas. Puede buscar esta información mediante una búsqueda de exhibición de documentos electrónicos en contexto en el centro de administración de Exchange (EAC) o una búsqueda de contenido en la seguridad &amp; centro de cumplimiento. 
  
## <a name="how-bcc-recipients-and-expanded-distribution-group-recipients-are-preserved"></a>Forma de conservación de los destinatarios CCO y los destinatarios del grupo de distribución expandido
<a name="sectionSection0"> </a>

Como se indicó anteriormente, se almacena información acerca de los destinatarios de Bcc'ed con el mensaje en el buzón del remitente. Esta información se indizados y está disponible para las búsquedas de exhibición de documentos electrónicos y las suspensiones. 
  
Información acerca de los destinatarios del grupo de distribución expandido se almacena con el mensaje después de colocar un buzón de correo en retención local o juicio. En Office 365, esta información también se almacena cuando se aplica una directiva de retención de Office 365 a un buzón de correo. Pertenencia a grupos de distribución se determina en el momento en que se envía el mensaje. La lista de destinatarios expandida almacenada en el mensaje no se ve afectada por los cambios en la pertenencia del grupo después de que el mensaje se envía. 
  
|**La información sobre...**|**se almacena en...**|**¿se almacena de forma predeterminada?**|**es accesible para...**|
|:-----|:-----|:-----|:-----|
|Destinatarios de Para y CC  <br/> |Propiedades del mensaje en los buzones de correo del remitente y los destinatarios  <br/> |Sí  <br/> |Remitente, destinatarios y responsables de cumplimiento normativo  <br/> |
|Destinatarios CCO  <br/> |Propiedad del mensaje en el buzón de correo del remitente  <br/> |Sí  <br/> |Remitente y responsables de cumplimento normativo  <br/> |
|Destinatarios del grupo de distribución expandido  <br/> |Propiedades del mensaje en el buzón de correo del remitente  <br/> |No. Información de destinatarios de grupo de distribución expandido se almacenan después de un buzón de correo se coloca en suspensión en contexto o juicio o asignado a una directiva de retención de Office 365.  <br/> |Responsables de cumplimento normativo  <br/> |
   
## <a name="searching-for-messages-sent-to-bcc-and-expanded-distribution-group-recipients"></a>Buscar mensajes enviados a destinatarios CCO y del grupo de distribución expandido
<a name="sectionSection1"> </a>

Cuando se buscan mensajes enviados a un destinatario, los resultados de la búsqueda de exhibición de documentos electrónicos ahora incluyen los mensajes enviados a un grupo de distribución del que es miembro el destinatario. En la tabla siguiente se muestran los escenarios en los que los mensajes enviados a destinatarios CCO y del grupo de distribución ampliado se proporcionan en las búsquedas de exhibición de documentos electrónicos.
  
Escenario 1: John es miembro del grupo de distribución US-Sales En esta tabla se muestran los resultados de búsqueda de la exhibición de documentos electrónicos cuando Bob le envía un mensaje a John directamente o indirectamente mediante un grupo de distribución.
  
|**Cuando busca en el buzón de correo de Bob mensajes enviados...**|**Y el mensaje se envía con...**|**¿Los resultados incluyen el mensaje?**|
|:-----|:-----|:-----|
|To:John  <br/> |John en TO  <br/> |Sí  <br/> |
|To:John  <br/> |US-Sales en TO  <br/> |Sí  <br/> |
|To:US-Sales  <br/> |US-Sales en TO  <br/> |Sí  <br/> |
|Cc:John  <br/> |John en CC  <br/> |Sí  <br/> |
|Cc:John  <br/> |US-Sales en CC  <br/> |Sí  <br/> |
|Cc:US-Sales  <br/> |US-Sales en CC  <br/> |Sí  <br/> |
   
Escenario 2: Bob le envía un correo electrónico a John (Para/CC) y Jack (CCO directamente o indirectamente mediante un grupo de distribución). En la tabla siguiente se muestran los resultados de búsqueda de la exhibición de documentos electrónicos.
  
|**Cuando busca...**|**Para los mensajes enviados...**|**¿Los resultados incluyen el mensaje?**|**Notas**|
|:-----|:-----|:-----|:-----|
|Buzón de correo de Bob  <br/> |To/Cc:John  <br/> |Sí  <br/> |Presenta una indicación de que Jack se incluyó en CCO.  <br/> |
|Buzón de correo de Bob  <br/> |Bcc:Jack  <br/> |Sí  <br/> |Presenta una indicación de que Jack se incluyó en CCO.  <br/> |
|Buzón de correo de Bob  <br/> |Bcc:Jack (mediante grupo de distribución)  <br/> |Sí  <br/> |La lista de miembros del grupo de distribución con CCO, que se expandió cuando se envió el mensaje, es visible en la vista previa de la búsqueda de la exhibición de documentos electrónicos, exportación y registros.  <br/> |
|Buzón de correo de John  <br/> |To/Cc:John  <br/> |Sí  <br/> |Sin indicación de los destinatarios CCO.  <br/> |
|Buzón de correo de John  <br/> |Bcc:Jack (directamente o mediante grupo de distribución)  <br/> |No  <br/> |La información de CCO no se almacena en el mensaje que se entrega a los destinatarios. Debe buscar en el buzón de correo del remitente.  <br/> |
|Buzón de correo de Jack  <br/> |To/Cc:John (directamente o mediante grupo de distribución)  <br/> |Sí  <br/> |La información de Para/CC se incluye en el mensaje que se entrega a todos los destinatarios.  <br/> |
|Buzón de correo de Jack  <br/> |Bcc:Jack (directamente o mediante grupo de distribución)  <br/> |No  <br/> |La información de CCO no se almacena en el mensaje que se entrega a los destinatarios. Debe buscar en el buzón de correo del remitente.  <br/> |
   
## <a name="frequently-asked-questions"></a>Preguntas más frecuentes
<a name="sectionSection2"> </a>

 **P. ¿Cuándo y dónde se almacena la información de destinatarios CCO?**
  
Se conserva la información de los destinatarios CCO r. de forma predeterminada en el mensaje original en el buzón de correo del remitente. Si el destinatario CCO es un grupo de distribución, pertenencia a grupos de distribución sólo se expande si el buzón del remitente se encuentra en suspensión o asignado a una directiva de retención de Office 365.
  
 **P. ¿Cuándo y dónde está almacenada la lista de destinatarios del grupo de distribución expandido?**
  
R. pertenencia a grupos de se expande en el momento en que se envía el mensaje. La lista de miembros del grupo de distribución expandido se almacena en el mensaje original en el buzón del remitente. Buzón de correo del remitente debe estar en suspensión en contexto, la suspensión por litigio, o asignado a una directiva de retención de Office 365.
  
 **P. ¿Los destinatarios incluidos en Para/CC: pueden ver qué destinatarios figuran en CCO?**
  
R. No. Esta información no se incluye en los encabezados del mensaje y no está visible para los destinatarios incluidos en Para/CC. El remitente puede ver el campo CCO almacenado en el mensaje original almacenado en el buzón de correo. Los responsables de cumplimento normativo pueden ver esta información cuando buscan en el buzón de correo del remitente.
  
 **P. ¿Cómo puedo asegurarme de que se conserven siempre los destinatarios del grupo de distribución expandido?**
  
R. para garantizar que los miembros del grupo de distribución expandido se conservan siempre con un mensaje, [colocarlos todos los buzones en suspensión](http://technet.microsoft.com/library/4c141604-3210-44cc-b98e-f3e0f15613b8.aspx) o creación una directiva de retención de Office 365 de toda la organización. 
  
 **P. ¿Qué tipos de grupos se admiten?**
  
R. Se admiten grupos de distribución, grupos de seguridad habilitados para correo y grupos de distribución dinámicos. 
  
 **P. ¿Existe un límite en la cantidad de destinatarios del grupo de distribución que se amplía y se almacena en el mensaje?**
  
R. Se conservan hasta 10.000 miembros de un grupo de distribución.
  
 **P. ¿Se admiten los grupos de distribución anidados?**
  
R. Sí, se expanden 25 niveles de grupos de distribución anidados.
  
 **P. ¿Dónde se puede ver la información de los destinatarios del grupo de distribución expandido y CCO?**
  
R. La información de los destinatarios CCO y del grupo de distribución expandido aparece visible para los responsables del cumplimiento normativo cuando se realiza una búsqueda de exhibición de documentos electrónicos. Los destinatarios CCO y del grupo de distribución expandido se incluyen en los resultados de la búsqueda que se hayan copiado en un buzón de correo de detección o se hayan exportado a un archivo PST y en el registro de exhibición de documentos electrónicos incluidos en los resultados de la búsqueda. La información de los destinatarios CCO también se encuentra disponible en la vista previa de la búsqueda.
  
 **P. ¿Qué ocurre si se oculta un miembro de un grupo de distribución de lista global de direcciones de la organización (GAL)?**
  
R. No pasa nada. Si los destinatarios están ocultas en la GAL, todavía se incluirán en la lista de destinatarios del grupo de distribución expandido.
  


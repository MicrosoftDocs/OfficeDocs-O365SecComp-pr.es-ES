---
title: Usar el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/18/2016
ms.audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
description: ¿Recibe un mensaje de error cuando intenta enviar un correo electrónico a un destinatario cuya dirección de correo electrónico está en Office 365? Si cree que no debería recibir este mensaje de error, use el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados de Office 365.
ms.openlocfilehash: 4964429f4d3aa1a585b1b543929f83c2cebfb9a4
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003259"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-list"></a>Usar el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados de Office 365

¿Recibe un mensaje de error cuando intenta enviar un correo electrónico a un destinatario cuya dirección de correo electrónico está en Office 365? Si cree que no debería recibir este mensaje de error, use el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados de Office 365.
  
## <a name="what-is-the-office-365-blocked-senders-list"></a>¿Qué es la lista de remitentes bloqueados de Office 365?

Microsoft usa la lista de remitentes bloqueados para proteger a sus clientes contra el spam, la suplantación de identidad y los ataques de phishing. La dirección IP de su servidor de correo, es decir, la dirección que usa su servidor de correo para identificarse en Internet, se ha considerado como una amenaza potencial para Office 365 por uno de numerosos motivos. Cuando Office 365 agrega la dirección IP a la lista, evita todas las comunicaciones entre la dirección IP y cualquiera de nuestros clientes a través de nuestros centros de datos.
  
Sabrá que lo hemos agregado a la lista cuando reciba una respuesta a un mensaje de correo que incluya un error similar al siguiente:
  
550 5.7.606-649 acceso denegado, prohibido enviar IP [_dirección IP_]; Para solicitar la eliminación de esta lista, visite https://sender.office.com/ y siga las instrucciones. Para obtener más información, consulte [informes de no entrega de correo electrónico en Office 365](http://go.microsoft.com/fwlink/?LinkID=526653).
  
_IP address_ es la dirección IP del equipo en el que se ejecuta el servidor de correo. 
  
### <a name="to-use-the-office-365-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Para usar el portal de eliminación de la lista de Office 365 para quitarse de la lista de remitentes bloqueados

1. En un explorador web, vaya a [https://sender.office.com](https://sender.office.com).
    
2. Siga las instrucciones que se indican en la página. Asegúrese de que usa la dirección de correo electrónico a la que se envió el mensaje de error, así como la dirección IP especificada en el mensaje de error. Solo se puede especificar una dirección de correo electrónico y una dirección IP por visita.
    
3. Haga clic en **Enviar**.
    
    El portal envía un correo electrónico a la dirección de correo electrónico que usted proporcione. El correo electrónico será similar a lo siguiente: ![captura de pantalla de correo electrónico recibido al enviar una solicitud a través del portal de delist](media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)
  
4. Haga clic en el vínculo de confirmación que aparece en el correo electrónico que le ha enviado el portal de eliminación de la lista.
    
    Regresará al portal de eliminación de la lista.
    
5. En el portal de eliminación de la lista, haga clic en **Quitar de la lista una IP**.
    
    Después de quitar la dirección IP de la lista de remitentes bloqueados, los mensajes de correo electrónico que procedan de esa dirección IP se entregarán a los destinatarios que usen Office 365. Por lo tanto, asegúrese de que el correo electrónico enviado desde esa dirección IP no es ofensivo ni malintencionado; de lo contrario, es posible que se vuelva a bloquear la dirección IP.
    


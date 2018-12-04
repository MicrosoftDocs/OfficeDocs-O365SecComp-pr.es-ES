---
title: Configurar notificaciones de correo no deseado para el usuario final en Exchange Online
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
description: Puede configurar notificaciones de spam para el usuario final para la directiva de filtro de spam de toda la compañía predeterminada o para las directivas de filtro de correo no deseado personalizadas que se aplican a dominios.
ms.openlocfilehash: 77ca32224cecaca2f558119db909ad74fdb6e858
ms.sourcegitcommit: cc8550452d099b4c5852c6559f6ca94a77f1d93b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2018
ms.locfileid: "27134774"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a>Configurar notificaciones de correo no deseado para el usuario final en Exchange Online

> [!IMPORTANT]
> En este tema es para los clientes de Exchange Online que va a proteger los buzones de correo hospedada en la nube. Los clientes de independiente de Exchange Online Protection (EOP) que va a proteger los buzones locales deben leer el tema siguiente en su lugar: [Configurar notificaciones de spam para el usuario final en EOP](configure-end-user-spam-notifications-in-eop.md). 
  
Puede configurar notificaciones de spam para el usuario final para la directiva de filtro de spam de toda la compañía predeterminada o para las directivas de filtro de correo no deseado personalizadas que se aplican a dominios. Habilitación de los mensajes de notificación de spam para el usuario final permite a los usuarios finales Self-administrar sus propios mensajes en cuarentena de correo no deseado. Notificaciones de spam para el usuario final no pueden usarse con las directivas que se aplica a los usuarios o grupos, o a una directiva con excepciones.
  
Las notificaciones de correo no deseado para el usuario final contienen una lista de los mensajes de correo no deseado puestos en cuarentena que recibió el usuario final durante el período de tiempo que usted configure (puede especificar cualquier valor entre 1 y 15 días). También puede configurar el idioma en el que está escrito el mensaje de notificación.
  
Después de recibir un mensaje de notificación, los usuarios finales puede elegir entre las siguientes opciones:

**Vista previa** del mensaje si desea obtener una vista previa del contenido o encabezado antes de realizar ninguna acción.

**Descargar** el mensaje si desea revisar el mensaje y los datos adjuntos (si hay alguno) en su dispositivo antes de realizar ninguna acción.

**Versión** si el mensaje no es correo no deseado y se desea que Office 365 para enviar el mensaje a su buzón de correo.

**Versión & Permitir remitente** si el mensaje no es correo no deseado y se desea que Office 365 para agregar el remitente a los remitentes seguros y la lista de destinatarios para futuros mensajes de correo electrónico. Tenga en cuenta que el administrador puede tener otras configuraciones de permitir o bloquear amplia de organización que reemplazar la lista de remitentes seguros.

**Versión & informe**, si el mensaje no es correo no deseado y desea enviar el mensaje a su buzón de correo y notificar a Microsoft para su análisis.

**Bloque** si desea que Office 365 para agregar el remitente a la lista de remitentes bloqueados.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

Tiempo estimado para finalizar: 2 minutos
  
Debe tener asignados los permisos puede llevar a cabo estos procedimientos. Para ver qué permisos necesita, vea la entrada "Contra correo no deseado" en el tema [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) . 
  
Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Keyboard shortcuts in Exchange 2013**.
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a>Usar el EAC para configurar las notificaciones de correo no deseado para el usuario final

1. En el Centro de administración de Exchange (EAC), vaya a **Protección** \> **Filtro de correo no deseado**.
    
2. Seleccione la directiva de filtro de spam para el que desea habilitar las notificaciones de spam para el usuario final (están deshabilitadas de forma predeterminada).
    
3. En el panel derecho, donde aparece la información de resumen sobre la directiva, haga clic en el vínculo **Configurar notificaciones de correo no deseado para el usuario final**. 
    
4. En el cuadro de diálogo siguiente, puede configurar las siguientes opciones:
    
1. **Habilitar las notificaciones de correo no deseado para el usuario final** Active esta casilla para habilitar las notificaciones de correo no deseado para el usuario final en esta directiva. (Y viceversa: si la directiva está habilitada, puede desactivar la casilla para deshabilitar las notificaciones de correo no deseado para el usuario final en esta directiva). 
    
2. **Enviar notificaciones de correo no deseado para el usuario final cada (días)** Especifique la frecuencia con la que quiere que se envíen las notificaciones de correo no deseado para el usuario final. El valor predeterminado es 3 días. Puede especificar cualquier valor entre 1 y 15 días. Si especifica 7 días, por ejemplo, la notificación incluirá una lista de todos los mensajes destinados a ese usuario en los 7 últimos días que se enviaron, en lugar de al usuario, a la cuarentena de correo no deseado. 
    
3. **Idioma de notificación** En la lista desplegable, seleccione el idioma en el que se escribirán las notificaciones de correo no deseado para el usuario final en esta directiva. 
    
5. Haga clic en **Guardar**. Se mostrará un resumen de su configuración de directiva de filtro de correo no deseado, incluida la configuración de notificación de correo no deseado del usuario final, en el panel derecho.
    
> [!NOTE]
>  Notificaciones de spam para el usuario final sólo será funcionales para directivas de filtro de correo no deseado que están habilitadas. > Sólo se envían las notificaciones de spam para el usuario final una vez al día. La hora de la notificación de entrega no se puede garantizar para cualquier cliente específico y no se puede configurar. 
  
 **Sugerencia:** Si desea probar las notificaciones de spam para el usuario final mediante el envío a un conjunto limitado de usuarios antes de implementarlos totalmente, crear una directiva de filtro de correo no deseado personalizadas que habilita las notificaciones de spam para el usuario final para los dominios en la que residen los usuarios. A continuación, en el CEF, bajo **flujo de correo \> reglas**, crear una regla de transporte para bloquear los mensajes de quarantine@messaging.microsoft.com (la dirección de correo electrónico que envía notificaciones) con excepciones para los usuarios que desea recibir las notificaciones. La imagen siguiente es un ejemplo de creación de una excepción para dos usuarios (SaraD y AlexD) desde el dominio Contoso.com: 
  
![Regla de transporte para probar las notificaciones de correo no deseado de usuario final](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a>Más información

[Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md)
  

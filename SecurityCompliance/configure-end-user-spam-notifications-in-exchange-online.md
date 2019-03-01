---
title: Configurar notificaciones de correo no deseado para el usuario final en Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: Puede configurar notificaciones de correo no deseado para el usuario final para la directiva predeterminada de filtro de correo no deseado de toda la compañía o para directivas personalizadas de filtro de correo no deseado que se aplican a dominios.
ms.openlocfilehash: e3e5ce044879318dab55f5d08ec2ee0e3379dfb2
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341371"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a>Configurar notificaciones de correo no deseado para el usuario final en Exchange Online

> [!IMPORTANT]
> Este tema es para los clientes de Exchange online que protegen los buzones hospedados en la nube. Exchange Online Protection (EOP) los clientes independientes que protegen buzones locales deben leer el siguiente tema: [configurar notificaciones de correo no deseado para el usuario final en EOP](configure-end-user-spam-notifications-in-eop.md). 
  
Puede configurar notificaciones de correo no deseado para el usuario final para la directiva predeterminada de filtro de correo no deseado de toda la compañía o para directivas personalizadas de filtro de correo no deseado que se aplican a dominios. La habilitación de mensajes de notificación de correo no deseado para el usuario final permite a los usuarios finales administrar automáticamente sus propios mensajes de correo no deseado en cuarentena. Las notificaciones de correo no deseado para el usuario final no se pueden usar con las directivas que se aplican a usuarios o grupos, o a una directiva con excepciones.
  
Las notificaciones de correo no deseado para el usuario final contienen una lista de los mensajes de correo no deseado puestos en cuarentena que recibió el usuario final durante el período de tiempo que usted configure (puede especificar cualquier valor entre 1 y 15 días). También puede configurar el idioma en el que está escrito el mensaje de notificación.
  
Después de recibir un mensaje de notificación, los usuarios finales pueden elegir entre las siguientes opciones:

**Obtenga una vista previa** del mensaje si desea obtener una vista previa del contenido o encabezado antes de llevar a cabo la acción.

**Descargue** el mensaje si desea revisar el mensaje y los datos adjuntos (si los hay) en el dispositivo antes de realizar la acción.

**Release** si el mensaje no es correo no deseado y desea que Office 365 envíe el mensaje al buzón de correo.

**Versión _AMP_ Permitir remitente** si el mensaje no es correo no deseado y desea que Office 365 agregue el remitente a la lista de remitentes seguros y destinatarios para futuros correos electrónicos. Tenga en cuenta que el administrador puede tener otras configuraciones de permitir o bloquear de toda la organización que invaliden la lista de remitentes seguros.

**Publique el informe de &**, si el mensaje no es correo no deseado y desea enviar el mensaje al buzón e identificarlo en Microsoft para su análisis.

**Bloquear** si desea que Office 365 agregue el remitente a la lista de remitentes bloqueados.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

Tiempo estimado para finalizar: 2 minutos
  
Debe tener permisos asignados para poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "contra el correo electrónico no deseado" en el tema [permisos de características de Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) . 
  
Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Keyboard shortcuts in Exchange 2013**.
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a>Usar el EAC para configurar las notificaciones de correo no deseado para el usuario final

1. En el Centro de administración de Exchange (EAC), vaya a **Protección** \> **Filtro de correo no deseado**.
    
2. Seleccione la Directiva de filtro de correo no deseado para la que desea habilitar las notificaciones de correo no deseado para el usuario final (están deshabilitadas de forma predeterminada).
    
3. En el panel derecho, donde aparece la información de resumen sobre la directiva, haga clic en el vínculo **Configurar notificaciones de correo no deseado para el usuario final**. 
    
4. En el cuadro de diálogo siguiente, puede configurar las siguientes opciones:
    
1. **Habilitar las notificaciones de correo no deseado para el usuario final** Active esta casilla para habilitar las notificaciones de correo no deseado para el usuario final en esta directiva. (Y viceversa: si la directiva está habilitada, puede desactivar la casilla para deshabilitar las notificaciones de correo no deseado para el usuario final en esta directiva). 
    
2. **Enviar notificaciones de correo no deseado para el usuario final cada (días)** Especifique la frecuencia con la que quiere que se envíen las notificaciones de correo no deseado para el usuario final. El valor predeterminado es 3 días. Puede especificar cualquier valor entre 1 y 15 días. Si especifica 7 días, por ejemplo, la notificación incluirá una lista de todos los mensajes destinados a ese usuario en los 7 últimos días que se enviaron, en lugar de al usuario, a la cuarentena de correo no deseado. 
    
3. **Idioma de notificación** En la lista desplegable, seleccione el idioma en el que se escribirán las notificaciones de correo no deseado para el usuario final en esta directiva. 
    
5. Haga clic en **Guardar**. En el panel derecho aparecerá un resumen de la configuración de la Directiva de filtro de correo no deseado, incluida la configuración de notificaciones de correo no deseado para el usuario final.
    
> [!NOTE]
>  Las notificaciones de correo no deseado para el usuario final solo serán compatibles con las directivas de filtro de correo no deseado que estén habilitadas. >: las notificaciones de correo no deseado para el usuario final solo se envían una vez al día. No se puede garantizar el tiempo de entrega de la notificación para un cliente específico y no se puede configurar. 
  
 **Sugerencia:** Si desea probar las notificaciones de correo no deseado para el usuario final enviándolas a un conjunto limitado de usuarios antes de implementarlos por completo, cree una directiva personalizada de filtro de correo no deseado que permita notificaciones de correo no deseado para el usuario final para los dominios en los que residen los usuarios. A continuación, en el EAC, en **reglas \> de flujo de correo**, cree una regla de flujo de correo (también denominada regla de transporte) para bloquear mensajes de Quarantine@messaging.microsoft.com (la dirección de correo electrónico que envía notificaciones) con excepciones para los usuarios que desee. para recibir las notificaciones. La siguiente imagen es un ejemplo de creación de una excepción para dos usuarios (SARAD y AlexD) del dominio Contoso.com: 
  
![Regla de transporte para probar las notificaciones de correo no deseado de usuario final](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a>Más información

[Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md)
  

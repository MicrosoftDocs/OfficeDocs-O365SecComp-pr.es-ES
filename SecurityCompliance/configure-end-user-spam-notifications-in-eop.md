---
title: Configurar notificaciones de correo no deseado para el usuario final en EOP
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: e9947db5-1dd1-4493-872d-7362b24c7ba0
ms.collection:
- M365-security-compliance
description: Las notificaciones de correo no deseado para el usuario final se pueden configurar en la directiva de filtro de contenido de toda la compañía, o bien en las directivas de filtro de contenido personalizadas que se aplican a los dominios.
ms.openlocfilehash: 8e2c2bd6b3e5a29beccaccea032f650936584a06
ms.sourcegitcommit: 9e2df36b05a2c93ce2629a7a5eda8f44159d114d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "35628463"
---
# <a name="configure-end-user-spam-notifications-in-eop"></a>Configurar notificaciones de correo no deseado para el usuario final en EOP
  
> [!IMPORTANT]
> Este tema va dirigido a clientes independientes de Exchange Online Protection (EOP) que protegen buzones locales. Los clientes de Exchange online que protegen buzones hospedados en la nube deben leer el siguiente tema en su lugar: [configurar notificaciones de correo no deseado para el usuario final en Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md). 
  
Las notificaciones de correo no deseado para el usuario final se pueden configurar en la directiva de filtro de contenido de toda la compañía, o bien en las directivas de filtro de contenido personalizadas que se aplican a los dominios. Cuando se habilitan los mensajes de notificación de correo no deseado para el usuario final, los usuarios finales pueden administrar sus propios mensajes de correo no deseado o en cuarentena. Las notificaciones de correo no deseado para el usuario final se pueden usar con directivas válidas que se aplican a usuarios o grupos, o bien a una directiva con excepciones.
  
Las notificaciones de correo no deseado para el usuario final contienen una lista de los mensajes de correo no deseado puestos en cuarentena que recibió el usuario final durante el período de tiempo que usted configure (puede especificar cualquier valor entre 1 y 15 días). También puede configurar el idioma en el que está escrito el mensaje de notificación.
  
Después de recibir un mensaje de notificación, los usuarios finales pueden elegir entre las siguientes opciones:

**Obtenga una vista previa** del mensaje si desea obtener una vista previa del contenido o encabezado antes de llevar a cabo la acción.

**Descargue** el mensaje si desea revisar el mensaje y los datos adjuntos (si los hay) en el dispositivo antes de realizar la acción.

**Release** si el mensaje no es correo no deseado y desea que Office 365 envíe el mensaje al buzón de correo.

**Versión & Permitir remitente** si el mensaje no es correo no deseado y desea que Office 365 agregue el remitente a la lista de remitentes seguros y destinatarios para futuros correos electrónicos. Tenga en cuenta que el administrador puede tener otras configuraciones de permitir o bloquear de toda la organización que invaliden la lista de remitentes seguros.

**Libere & Informe**, si el mensaje no es correo no deseado y desea enviar el mensaje al buzón de correo y notificarlo a Microsoft para su análisis.

**Bloquear remitente** si desea que Office 365 agregue el remitente a la lista de remitentes bloqueados.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?
<a name="sectionSection0"> </a>

Tiempo estimado para finalizar: 5 minutos
  
Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "Contra el correo electrónico no deseado" en el tema [Permisos de características en EOP](eop/feature-permissions-in-eop.md). 
  
Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Keyboard shortcuts in Exchange 2013**.
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a>Usar el EAC para configurar las notificaciones de correo no deseado para el usuario final

1. En el centro de administración de Exchange (EAC), vaya al filtro de **protección** > de**correo no deseado**.
    
2. Seleccione la directiva de filtro de contenido para la que quiera habilitar notificaciones de correo no deseado para el usuario final (están deshabilitadas de forma predeterminada).
    
3. En el panel derecho, donde aparece la información de resumen sobre la directiva, haga clic en el vínculo **Configurar notificaciones de correo no deseado para el usuario final**. 
    
4. En el cuadro de diálogo siguiente, puede configurar las siguientes opciones:
    
1. **Habilitar las notificaciones de correo no deseado para el usuario final** Active esta casilla para habilitar las notificaciones de correo no deseado para el usuario final en esta directiva. (Y viceversa: si la directiva está habilitada, puede desactivar la casilla para deshabilitar las notificaciones de correo no deseado para el usuario final en esta directiva). 
    
2. **Enviar notificaciones de correo no deseado para el usuario final cada (días)** Especifique la frecuencia con la que quiere que se envíen las notificaciones de correo no deseado para el usuario final. El valor predeterminado es 3 días. Puede especificar cualquier valor entre 1 y 15 días. Si especifica 7 días, por ejemplo, la notificación incluirá una lista de todos los mensajes destinados a ese usuario en los 7 últimos días que se enviaron, en lugar de al usuario, a la cuarentena de correo no deseado. 
    
3. **Idioma de notificación** En la lista desplegable, seleccione el idioma en el que se escribirán las notificaciones de correo no deseado para el usuario final en esta directiva. 
    
5. Haga clic en **Guardar**. Aparecerá un resumen de la configuración de la directiva de filtro de contenido, incluida la configuración de notificaciones de correo no deseado para el usuario final, en el panel derecho.
    
> [!NOTE]
>  Las notificaciones de correo no deseado para el usuario final funcionarán únicamente en las directivas de filtro de contenido en las que estén habilitadas. >  Las notificaciones de correo no deseado para el usuario final se envían solo una vez al día. La hora de envío de la notificación no es configurable y, como tal, no se puede confirmar para ningún cliente en concreto. 
  
 **Sugerencia:** Si quiere probar las notificaciones de correo no deseado para el usuario final enviándolas a un conjunto limitado de usuarios antes de implementarlas totalmente, cree una directiva de filtro de contenido personalizada que habilite notificaciones de correo no deseado para el usuario final para los dominios en los que residen los usuarios. A continuación, en el EAC, en **reglas \> de flujo de correo**, cree una regla de flujo de correo (también denominada regla de transporte) para bloquear mensajes de Quarantine@messaging.microsoft.com (la dirección de correo electrónico que envía notificaciones) con excepciones para los usuarios que desee. para recibir las notificaciones. La siguiente imagen es un ejemplo de cómo crear una excepción para dos usuarios (SaraD y AlexD) desde el dominio Contoso.com: 
  
![Regla de transporte para probar las notificaciones de correo no deseado de usuario final](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a>Más información

[Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md)
  

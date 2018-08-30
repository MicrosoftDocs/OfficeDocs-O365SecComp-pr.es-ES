---
title: Configurar notificaciones de correo no deseado para el usuario final en EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: e9947db5-1dd1-4493-872d-7362b24c7ba0
description: Las notificaciones de correo no deseado para el usuario final se pueden configurar en la directiva de filtro de contenido de toda la compañía, o bien en las directivas de filtro de contenido personalizadas que se aplican a los dominios.
ms.openlocfilehash: 990fa31cc22b33d235d6e8f106511996a52212a2
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002929"
---
# <a name="configure-end-user-spam-notifications-in-eop"></a>Configurar notificaciones de correo no deseado para el usuario final en EOP
  
> [!IMPORTANT]
> En este tema es para los clientes de independiente de Exchange Online Protection (EOP) que va a proteger los buzones locales. Los clientes de Exchange Online que va a proteger los buzones de correo hospedada en la nube deben leer el tema siguiente en su lugar: [configurar para el usuario final de correo no deseado notificaciones en Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md). 
  
Las notificaciones de correo no deseado para el usuario final se pueden configurar en la directiva de filtro de contenido de toda la compañía, o bien en las directivas de filtro de contenido personalizadas que se aplican a los dominios. Cuando se habilitan los mensajes de notificación de correo no deseado para el usuario final, los usuarios finales pueden administrar sus propios mensajes de correo no deseado o en cuarentena. Las notificaciones de correo no deseado para el usuario final se pueden usar con directivas válidas que se aplican a usuarios o grupos, o bien a una directiva con excepciones.
  
Las notificaciones de correo no deseado para el usuario final contienen una lista de los mensajes de correo no deseado puestos en cuarentena que recibió el usuario final durante el período de tiempo que usted configure (puede especificar cualquier valor entre 1 y 15 días). También puede configurar el idioma en el que está escrito el mensaje de notificación.
  
Tras recibir un mensaje de notificación, los usuarios finales pueden hacer clic en el correo electrónico no deseado para moverlo a su Bandeja de entrada o informar de que el correo es deseado, en cuyo caso se enviará al equipo de análisis de correo no deseado de Microsoft.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?
<a name="sectionSection0"> </a>

Tiempo estimado para finalizar: 5 minutos
  
Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "Contra el correo electrónico no deseado" en el tema [Permisos de características en EOP](eop/feature-permissions-in-eop.md). 
  
Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Keyboard shortcuts in Exchange 2013**.
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a>Usar el EAC para configurar las notificaciones de correo no deseado para el usuario final

1. En el Centro de administración de Exchange (EAC), vaya a **Protección** \> **Filtro de contenido**.
    
2. Seleccione la directiva de filtro de contenido para la que quiera habilitar notificaciones de correo no deseado para el usuario final (están deshabilitadas de forma predeterminada).
    
3. En el panel derecho, donde aparece la información de resumen sobre la directiva, haga clic en el vínculo **Configurar notificaciones de correo no deseado para el usuario final**. 
    
4. En el cuadro de diálogo siguiente, puede configurar las siguientes opciones:
    
1. **Habilitar las notificaciones de correo no deseado para el usuario final** Active esta casilla para habilitar las notificaciones de correo no deseado para el usuario final en esta directiva. (Y viceversa: si la directiva está habilitada, puede desactivar la casilla para deshabilitar las notificaciones de correo no deseado para el usuario final en esta directiva). 
    
2. **Enviar notificaciones de correo no deseado para el usuario final cada (días)** Especifique la frecuencia con la que quiere que se envíen las notificaciones de correo no deseado para el usuario final. El valor predeterminado es 3 días. Puede especificar cualquier valor entre 1 y 15 días. Si especifica 7 días, por ejemplo, la notificación incluirá una lista de todos los mensajes destinados a ese usuario en los 7 últimos días que se enviaron, en lugar de al usuario, a la cuarentena de correo no deseado. 
    
3. **Idioma de notificación** En la lista desplegable, seleccione el idioma en el que se escribirán las notificaciones de correo no deseado para el usuario final en esta directiva. 
    
5. Haga clic en **Guardar**. Aparecerá un resumen de la configuración de la directiva de filtro de contenido, incluida la configuración de notificaciones de correo no deseado para el usuario final, en el panel derecho.
    
> [!NOTE]
>  Las notificaciones de correo no deseado para el usuario final funcionarán únicamente en las directivas de filtro de contenido en las que estén habilitadas. >  Las notificaciones de correo no deseado para el usuario final solo se envían una vez al día. No se puede garantizar ni se puede configurar el plazo de entrega de la notificación para ningún cliente específico. 
  
 **Sugerencia:** Si quiere probar las notificaciones de correo no deseado para el usuario final enviándolas a un conjunto limitado de usuarios antes de implementarlas totalmente, cree una directiva de filtro de contenido personalizada que habilite notificaciones de correo no deseado para el usuario final para los dominios en los que residen los usuarios. Luego, en el EAC, en **Flujo de correo \> reglas**, cree una regla de transporte para bloquear mensajes de quarantine@messaging.microsoft.com (la dirección de correo electrónico que envía notificaciones) con excepciones para los usuarios que desea que reciban las notificaciones. La siguiente imagen es un ejemplo de cómo crear una excepción para dos usuarios (SaraD y AlexD) desde el dominio Contoso.com: 
  
![Regla de transporte para probar las notificaciones de correo no deseado de usuario final](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a>Más información

[Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md)
  

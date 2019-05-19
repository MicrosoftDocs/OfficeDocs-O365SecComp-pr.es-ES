---
title: Crear listas de remitentes bloqueados o seguros para toda la organización en Office 365
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/8/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: Si desea asegurarse de que recibe el correo de un remitente determinado, ya que confía en ellos y sus mensajes, puede ajustar la lista de permitidos en una directiva de filtro de correo no deseado en el centro de administración de Exchange.
ms.openlocfilehash: 4731fe4a72a3c331725b82e09240e6af91bb6afd
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153732"
---
# <a name="create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365"></a>Crear listas de remitentes bloqueados o seguros para toda la organización en Office 365
  
Si desea asegurarse de que recibe el correo de un remitente determinado, ya que confía en ellos y sus mensajes, puede ajustar la lista de permitidos en una directiva de filtro de correo no deseado en el filtro de **protección** \> contra **correo no**deseado del centro de administración de Exchange (EAC). Obtenga más información sobre esto en [configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md). Otra opción sería crear una regla de flujo de correo de Exchange (también denominada regla de transporte) que funcione como el dominio o la lista de permitidos basada en el usuario en el filtro de correo no deseado. También puede bloquear mensajes enviados desde un dominio o usuario concreto de forma similar.
  
Una regla de flujo de correo sería útil en esta situación si necesita filtrar criterios complejos como comprobar los encabezados de mensaje o los nombres de los datos adjuntos o si desea agregar acciones complejas, como agregar un aviso de declinación de responsabilidades al mensaje o aplicar un período de tiempo en el que regla e está activo. Sin embargo, el método preferido para asegurarse de que los correos electrónicos de un remitente o dominio específicos eluden el filtro de correo no deseado es agregarlos a la Directiva de filtro de correo no deseado. Para empezar con esto en el EAC, vaya a **protección** \> contra **correo no deseado**. Para obtener más información, vea [configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).
  
> [!TIP]
> Una lista basada en dominio de una regla de flujo de correo no es tan segura como una lista basada en direcciones IP, ya que los dominios se pueden suplantar. Además, si la dirección IP del remitente está en una lista de bloqueados, se bloqueará aun cuando se omita el filtrado para el dominio o el usuario. Esto se debe a que una regla de flujo de correo en un dominio o usuario no invalida la lista global de direcciones IP bloqueadas. En la mayoría de casos se recomienda utilizar una lista basada en direcciones IP. Para crear una lista basada en direcciones IP, puede usar la Lista de direcciones IP permitidas o la Lista de direcciones IP bloqueadas en el filtro de conexión. Los mensajes enviados desde estas direcciones IP no están protegidos por el filtro de contenido. Para obtener instrucciones acerca de cómo configurar la directiva de filtros de conexiones al añadir direcciones IP a la lista de direcciones IP permitidas o bloqueadas, vea [Configurar la directiva de filtro de conexión](configure-the-connection-filter-policy.md). 
  
Para otras tareas de administración relacionadas con las reglas de flujo de correo, vea [reglas de flujo de correo (reglas de transporte) en Exchange Online](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx).
  
## <a name="use-the-eac-to-customize-a-block-or-allow-list-to-prevent-or-receive-email-from-a-domain-or-user"></a>Usar el EAC para personalizar una lista de bloqueados o de permitidos para impedir o recibir correo electrónico de un dominio o usuario

1. En el EAC, vaya a filtro de **protección** \> **contra correo no deseado**. 
    
2. En la página **General** , realice una de las siguientes acciones: 
    
  - Haga doble clic en la directiva predeterminada o en una directiva existente para empezar a editarla.
    
  - Haga clic en **nuevo** para crear una nueva directiva personalizada de filtro de correo no deseado que se puede aplicar a los usuarios, grupos y dominios de la organización. 
    
3. En la página **Listas de permitidos**, puede especificar entradas, como remitentes o dominios, que siempre se entregarán en la Bandeja de entrada. El filtro contra correo no deseado no procesa el correo electrónico de estas entradas. Haga lo siguiente: 
    
  - Agregue remitentes de confianza a la lista de permitidos del remitente. Haga clic en **Agregar**y, a continuación, en el cuadro de diálogo de selección, agregue las direcciones del remitente que desea permitir. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en Aceptar para volver a la página **Listas de permitidos**. 
    
  - Agregue dominios de confianza a la lista de permitidos del dominio. Haga clic en **Agregar**y, a continuación, en el cuadro de diálogo de selección, agregue los dominios que desea permitir. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en Aceptar para volver a la página **Listas de permitidos**. 
    
    > [!CAUTION]
    > Si permite dominios de primer nivel, es probable que el correo no deseado se entregue en una bandeja de entrada. 
  
4. En la página **Listas de bloqueados**, puede especificar entradas, como remitentes o dominios, que siempre se marcarán como correo no deseado. El servicio aplicará la acción de correo no deseado de alta confianza configurada en el correo electrónico que coincida con estas entradas. 
    
  - Agregue remitentes no deseados a la lista de bloqueados del remitente. Haga clic en **Agregar**![Agregar icono](media/ITPro-EAC-AddIcon.gif) y, a continuación, en el cuadro de diálogo de selección, agregue las direcciones del remitente que desea bloquear. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en **Aceptar** para volver a la página **Listas de bloqueados**. 
    
  - Agregue dominios no deseados a la lista de bloqueados del dominio. Haga clic en **Agregar**![Agregar icono](media/ITPro-EAC-AddIcon.gif) y, a continuación, en el cuadro de diálogo de selección, agregue los dominios que desea bloquear. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en **Aceptar** para volver a la página **Listas de bloqueados**. 
    
    > [!CAUTION]
    > Si bloquea dominios de primer nivel, es probable que el correo electrónico que no desea se marque como correo no deseado. 
  
## <a name="what-do-you-need-to-know-before-you-begin-creating-a-mail-flow-rule"></a>¿Qué necesita saber antes de empezar a crear una regla de flujo de correo?
    
- No es necesario crear una regla de flujo de correo para omitir el filtrado de correo no deseado o marcar el correo electrónico como correo no deseado para un remitente o dominio. Use las listas bloquear y permitir de Exchange Online Protection en una directiva de correo no deseado en lugar de esta regla de flujo de correo si simplemente desea bloquear o permitir a un remitente o dominio específicos y no adjuntar condiciones adicionales. Obtenga más información sobre esto en [configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).
    
- Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "reglas de flujo de correo" en el tema [permisos de directivas de mensajería y conformidad](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) . 
    
- Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Métodos abreviados de teclado en el Centro de administración de Exchange**.
    
> [!TIP]
> ¿Problemas? Solicite ayuda en los foros de Exchange. Visite los foros en [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612), [Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-bypass-spam-filtering-for-a-domain-or-user"></a>Usar el EAC para crear una regla de flujo de correo para omitir el filtrado de correo no deseado para un dominio o usuario

1. En el EAC, vaya a **Flujo de correo** \> **Reglas**. Elija **Agregar** ![icono](media/ITPro-EAC-AddIcon.gif) agregar y, a continuación, elija desviar el **filtrado de correo no deseado**.
    
2. Asigne un nombre a la regla. En **Aplicar esta regla si**, elija **El remitente** y, a continuación, seleccione una de las siguientes condiciones: 
    
  - Si desea especificar un dominio, elija **el dominio es**. En el cuadro de diálogo **Especificar dominio**, escriba el dominio del remitente que desea designar como seguro, como contoso.com. **Agregar** ![Agregue un](media/ITPro-EAC-AddIcon.gif) icono para moverlo a la lista de frases. Repita este paso si desea agregar otros dominios y haga clic en **Aceptar** cuando haya terminado. 
    
  - Si desea especificar un dominio, elija **es esta persona**. En el cuadro de diálogo **Seleccionar miembros**, agregue el usuario de la lista o escriba el usuario y haga clic en **Comprobar nombres**. Repita este paso si desea agregar otros usuarios y haga clic en **Aceptar** cuando haya terminado. 
    
3. Active la casilla **Detener el procesamiento de más reglas** para garantizar que ninguna otra regla pueda revertir la acción de omisión. 
    
4. Para la opción **La dirección del remitente debe coincidir con el siguiente elemento del mensaje**, seleccione **Encabezado o sobre**.
    
5. Si lo desea, puede realizar selecciones para auditar la regla, probarla, activarla durante un período de tiempo específico y otras selecciones.
    
6. Seleccione **Guardar** para guardar la regla. 
    
Una vez que se ha creado y aplicado la regla, el filtrado de correo no deseado se omite para el dominio o usuario que haya especificado.
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-that-blocks-messages-sent-from-a-domain-or-user"></a>Usar el EAC para crear una regla de flujo de correo que bloquee los mensajes enviados desde un dominio o usuario

1. En el EAC, vaya a **Flujo de correo** \> **Reglas**. Elija **Agregar** ![icono](media/ITPro-EAC-AddIcon.gif) agregar y, a continuación, elija **crear una nueva regla**.
    
2. Especifique un nombre para la regla y luego haga clic en **Más opciones**. 
    
3. En **Aplicar esta regla si**, elija **El remitente** y, a continuación, seleccione una de las siguientes condiciones: 
    
  - Si desea especificar un dominio, elija **el dominio es**. En el cuadro de diálogo Especificar dominio, escriba el dominio del remitente al que desea bloquear los mensajes, como contoso.com. Haga **** ![clic en agregar](media/ITPro-EAC-AddIcon.gif) icono para agregarlo para moverlo a la lista de frases. Repita este paso si desea agregar otros dominios y haga clic en **Aceptar** cuando haya terminado. 
    
  - Si desea especificar un dominio, elija **es esta persona**. En el cuadro de diálogo **Seleccionar miembros**, agregue el usuario de la lista o escriba el usuario y haga clic en **Comprobar nombres**. Repita este paso si desea agregar otros usuarios y haga clic en **Aceptar** cuando haya terminado. 
    
4. En **Hacer lo siguiente**, elija **Bloquear el mensaje** y haga clic en una de las otras opciones, como **Borrar el mensaje sin notificar a nadie**.
    
5. Haga clic en **Más opciones** y, en la opción **La dirección del remitente debe coincidir con el siguiente elemento del mensaje**, seleccione **Encabezado o sobre**.
    
6. Si lo desea, puede realizar selecciones para auditar la regla, probarla, activarla durante un período de tiempo específico y otras selecciones. Es recomendable probar la regla durante un tiempo antes de aplicarla en la organización.
    
7. Seleccione **Guardar** para guardar la regla. 
    
Tras crear y aplicar la regla, los mensajes enviados desde el dominio o usuario que especifique se bloquearán.
  
## <a name="see-also"></a>Vea también

[Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md)
  
[Usar reglas de flujo de correo para configurar el filtrado de correo electrónico masivo](use-transport-rules-to-configure-bulk-email-filtering.md)


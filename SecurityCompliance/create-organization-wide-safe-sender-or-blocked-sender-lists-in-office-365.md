---
title: Crear listas de remitentes bloqueados o seguros para toda la organización en Office 365
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/8/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: Si desea para asegurarse de que recibe el correo de un remitente determinado, debido a que confía en ellos y sus mensajes, puede ajustar la lista de permitidos en una directiva de filtro de spam en el centro de administración de Exchange.
ms.openlocfilehash: a90679fc900ca5695904898af3627fc1900a8545
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003169"
---
# <a name="create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365"></a>Crear listas de remitentes bloqueados o seguros para toda la organización en Office 365
  
Si desea para asegurarse de que recibe el correo de un remitente determinado, debido a que confía en ellos y sus mensajes, puede ajustar la lista de permitidos en una directiva de filtro de spam en el centro de administración de Exchange (EAC) en **protección** \> **Spam filter**. Más información sobre esto en la [configuración de sus directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md). Otra opción sería crear una regla de transporte de Exchange que funciona como el dominio o basadas en usuarios lista de permitidos en el filtro de spam. Puede bloquear los mensajes enviados desde un dominio en particular o un usuario de una manera similar demasiado.
  
Una regla de transporte sería útil en esta situación, si necesita filtrar los criterios complejos como la comprobación de encabezados de los mensajes o los nombres de los datos adjuntos o si desea agregar acciones complejas, como la adición de una renuncia al mensaje o aplicar un período de tiempo donde la rul e está activo. Sin embargo, el método preferido para asegurarse de que el filtro de spam el desvío de mensajes de correo electrónico de un remitente específico o dominio es agregarlos a su directiva de filtro de spam. Introducción a esto en el EAC, vaya a **protección** \> **Spam filter**. Encontrará más información en la [configuración de sus directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).
  
> [!TIP]
> Una lista basada en dominio en una regla de transporte no es tan segura como una lista basada en la dirección IP, porque pueden ser suplantados dominios. Además, si la dirección IP remitente está en una lista de bloqueo, aún se bloqueará incluso si el filtrado para el dominio o usuario se omitió. Esto es debido a que una regla de transporte en un dominio o un usuario no reemplaza a la lista global de direcciones IP bloqueadas. Se recomienda usar una lista de basados en direcciones IP en la mayoría de los casos. Para crear una lista de basados en direcciones IP, puede usar la lista de direcciones IP permitidas o la lista de direcciones IP bloqueadas en el filtro de conexión. Todos los mensajes enviados desde estas direcciones IP no están activados por el filtro de contenido. Para obtener instrucciones acerca de cómo configurar la directiva de filtro de conexión mediante la adición de las direcciones IP a la lista de direcciones IP permitidas o la lista de direcciones IP bloqueadas, vea [Configurar la directiva de filtro de conexión](configure-the-connection-filter-policy.md). 
  
Para otras tareas de administración relacionadas con reglas de transporte, consulte [Transport Rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx).
  
## <a name="use-the-eac-to-customize-a-block-or-allow-list-to-prevent-or-receive-email-from-a-domain-or-user"></a>Use el CEF para personalizar un bloque o permitir lista impedir o recibir correo electrónico de un dominio o un usuario

1. En el EAC, vaya a **protección** \> **Spam filter**. 
    
2. En la página **general** , realice una de las siguientes opciones: 
    
  - Haga doble clic en la directiva predeterminada o una directiva existente para comenzar la modificación.
    
  - Haga clic en **nuevo** para crear una nueva directiva de filtro de correo no deseado personalizado que se puede aplicar a los usuarios, grupos y dominios de la organización. 
    
3. En la página **Permitir listas** , puede especificar las entradas, como los remitentes o dominios, que siempre se entregarán en la Bandeja de entrada. Correo electrónico de estas entradas no se procesa por el filtro de spam. Haga lo siguiente: 
    
  - Agregar a remitentes de confianza al remitente de la lista de permitidos. Haga clic en **Agregar**y, a continuación, en el cuadro de diálogo de selección, agregue las direcciones del remitente que desea permitir. Se pueden separar varias entradas con un punto y coma o una nueva línea. Haga clic en Aceptar para volver a la página **Permitir listas** . 
    
  - Agregar dominios de confianza para el dominio de la lista de permitidos. Haga clic en **Agregar**y, a continuación, en el cuadro de diálogo de selección, agregue los dominios que desea permitir. Se pueden separar varias entradas con un punto y coma o una nueva línea. Haga clic en Aceptar para volver a la página **Permitir listas** . 
    
    > [!CAUTION]
    > Si permite dominios de primer nivel, es probable que el correo no deseado se entregue en una bandeja de entrada. 
  
4. En la página **Listas de bloqueados**, puede especificar entradas, como remitentes o dominios, que siempre se marcarán como correo no deseado. El servicio aplicará la acción de correo no deseado de alta confianza configurada en el correo electrónico que coincida con estas entradas. 
    
  - Agregue remitentes no deseados a la lista de bloqueados del remitente. Haga clic en **Agregar**![Agregar icono](media/ITPro-EAC-AddIcon.gif) y, a continuación, en el cuadro de diálogo de selección, agregue las direcciones del remitente que desea bloquear. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en **Aceptar** para volver a la página **Listas de bloqueados**. 
    
  - Agregue dominios no deseados a la lista de bloqueados del dominio. Haga clic en **Agregar**![Agregar icono](media/ITPro-EAC-AddIcon.gif) y, a continuación, en el cuadro de diálogo de selección, agregue los dominios que desea bloquear. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en **Aceptar** para volver a la página **Listas de bloqueados**. 
    
    > [!CAUTION]
    > Si bloquea dominios de primer nivel, es probable que el correo electrónico que no desea se marque como correo no deseado. 
  
## <a name="what-do-you-need-to-know-before-you-begin-creating-a-transport-rule"></a>¿Qué necesita saber antes de empezar a crear una regla de transporte?
    
- No es necesario crear una regla de transporte para el desvío de filtrado de spam o marcar el correo electrónico como correo no deseado para un remitente o un dominio. Utilizar el bloque de Exchange Online Protection y permitir que las listas en una directiva de correo en lugar de esta regla de transporte si simplemente desea bloquear o permitir que un remitente específico o un dominio y no adjunta las condiciones adicionales. Más información sobre esto en la [configuración de sus directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).
    
- Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el la entrada "Reglas de transporte" en el tema [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx). 
    
- Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Métodos abreviados de teclado en el Centro de administración de Exchange**.
    
> [!TIP]
> ¿Teniendo problemas? Solicitar ayuda en los foros de Exchange. Visite los foros de [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612), [Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="use-the-eac-to-create-a-transport-rule-to-bypass-spam-filtering-for-a-domain-or-user"></a>Usar el EAC para crear una regla de transporte para que omita el filtrado para un dominio o un usuario de spam

1. En el EAC, vaya a **flujo de correo** \> **reglas**. Elija **Agregar** ![icono Agregar](media/ITPro-EAC-AddIcon.gif) y, a continuación, elija **el desvío de correo no deseado filtrado**.
    
2. Asigne un nombre a la regla. En **Aplicar esta regla si**, elija **El remitente** y, a continuación, seleccione una de las siguientes condiciones: 
    
  - Si desea especificar un dominio, elija el **dominio es**. En el cuadro de diálogo **Especificar dominio** , escriba el dominio del remitente que desea designar como seguros, por ejemplo, contoso.com. **Agregar** ![Icono Agregar](media/ITPro-EAC-AddIcon.gif) para moverlo a la lista de frases. Repita este paso si desea agregar dominios adicionales y haga clic en **Aceptar** cuando haya terminado. 
    
  - Si desea especificar un dominio, elija **es esta persona**. En el cuadro de diálogo **Seleccionar miembros**, agregue el usuario de la lista o escriba el usuario y haga clic en **Comprobar nombres**. Repita este paso si desea agregar otros usuarios y haga clic en **Aceptar** cuando haya terminado. 
    
3. Active la casilla **Detener el procesamiento de más reglas** para garantizar que ninguna otra regla pueda revertir la acción de omisión. 
    
4. Para la opción **La dirección del remitente debe coincidir con el siguiente elemento del mensaje**, seleccione **Encabezado o sobre**.
    
5. Si lo desea, puede realizar selecciones para auditar la regla, probarla, activarla durante un período de tiempo específico y otras selecciones. Es recomendable probar la regla durante un tiempo antes de aplicarla en la organización. Para obtener más información acerca de estas selecciones, consulte [Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx).
    
6. Seleccione **Guardar** para guardar la regla. 
    
Una vez que se ha creado y aplicado la regla, el filtrado de correo no deseado se omite para el dominio o usuario que haya especificado.
  
## <a name="use-the-eac-to-create-a-transport-rule-that-blocks-messages-sent-from-a-domain-or-user"></a>Usar el EAC para crear una regla de transporte que bloquea los mensajes enviados desde un dominio o un usuario

1. En el EAC, vaya a **flujo de correo** \> **reglas**. Elija **Agregar** ![icono Agregar](media/ITPro-EAC-AddIcon.gif) y, a continuación, elija **crear una nueva regla**.
    
2. Especifique un nombre para la regla y luego haga clic en **Más opciones**. 
    
3. En **Aplicar esta regla si**, elija **El remitente** y, a continuación, seleccione una de las siguientes condiciones: 
    
  - Si desea especificar un dominio, elija el **dominio es**. En el cuadro de diálogo Especificar dominio, escriba el dominio del remitente desde el que desea bloquear mensajes, por ejemplo, contoso.com. Haga clic en **Agregar** ![icono Agregar](media/ITPro-EAC-AddIcon.gif) para moverlo a la lista de frases. Repita este paso si desea agregar dominios adicionales y haga clic en **Aceptar** cuando haya terminado. 
    
  - Si desea especificar un dominio, elija **es esta persona**. En el cuadro de diálogo **Seleccionar miembros**, agregue el usuario de la lista o escriba el usuario y haga clic en **Comprobar nombres**. Repita este paso si desea agregar otros usuarios y haga clic en **Aceptar** cuando haya terminado. 
    
4. En **Hacer lo siguiente**, elija **Bloquear el mensaje** y haga clic en una de las otras opciones, como **Borrar el mensaje sin notificar a nadie**.
    
5. Haga clic en **Más opciones** y, en la opción **La dirección del remitente debe coincidir con el siguiente elemento del mensaje**, seleccione **Encabezado o sobre**.
    
6. Si lo desea, puede realizar selecciones para auditar la regla, probarla, activarla durante un período de tiempo específico y otras selecciones. Es recomendable probar la regla durante un tiempo antes de aplicarla en la organización. Para obtener más información acerca de estas selecciones, consulte [Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx).
    
7. Seleccione **Guardar** para guardar la regla. 
    
Tras crear y aplicar la regla, los mensajes enviados desde el dominio o usuario que especifique se bloquearán.
  
## <a name="see-also"></a>Vea también

[Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md)
  
[Usar reglas de transporte para configurar el filtrado de correo electrónico masivo](use-transport-rules-to-configure-bulk-email-filtering.md)


---
title: Configurar la Directiva de filtro de conexión, lista de permitidos, lista de bloqueados
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
description: Para asegurarse de que el correo electrónico enviado por personas de confianza no está bloqueado, puede usar la Directiva de filtro de conexión para crear una lista de permitidos, también conocida como lista de remitentes seguros, de las direcciones IP en las que confía. También puede crear una lista de remitentes bloqueados.
ms.openlocfilehash: 71dd34ea822324936713380e557d2341e1e389c0
ms.sourcegitcommit: 769b506c828c475c713dbb337e115714dcc7f17c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "36699265"
---
# <a name="configure-the-connection-filter-policy"></a>Configurar la directiva de filtro de conexión

La mayoría de nosotros tenemos amigos y socios comerciales en los que confiamos. Puede resultar frustrante encontrar correo electrónico de ellos en la carpeta de correo electrónico no deseado o incluso bloqueado totalmente por un filtro contra correo no deseado. Si desea asegurarse de que el correo electrónico que le envían las personas en las que confía no se bloquea, puede usar la directiva de filtro de conexión para crear una lista de direcciones IP permitidas, también conocida como lista de remitentes seguros, en las que confía. También puede crear una lista de remitentes bloqueados, que es una lista de direcciones IP, normalmente de spammers conocidos, de las que nunca quiere recibir mensajes de correo electrónico.
  
- Al pensar en *[las listas](create-safe-sender-lists-in-office-365.md)* de permitidos, tenga en cuenta que las directivas de filtro de conexión se refieren a las *cuentas de confianza permitidas* por el filtro. Esto se hace con el interés de filtrar de forma más precisa los mensajes de correo de menor confianza o no confiable mientras se conservan los elementos necesarios. Una lista de permitidos de la Directiva de filtro de conexión consiste en filtrar las direcciones IP de confianza de un grupo mucho más amplio de cuentas e IPs y garantizar el acceso de los correos electrónicos de confianza fácilmente.

- Una directiva de filtro de conexión que crea una lista de bloqueo puede considerarse como la detección de menos o con cuentas no fidedignas en el filtro en su lugar.

 Para obtener más información sobre configuración de correo no deseado que se aplica a toda la organización, consulte [Cómo ayudar a garantizar que un mensaje no se marque como correo no deseado](https://go.microsoft.com/fwlink/p/?LinkId=534224) o [Bloquear el correo no deseado con el filtro de correo no deseado de Office 365 para evitar problemas de negativos falsos](https://go.microsoft.com/fwlink/p/?LinkId=534225). Estos son útiles si tiene control de nivel de administrador y desea evitar falsos positivos o negativos falsos.

> [!TIP]
> Puede que quiera pausar y leer sobre cómo crear listas de bloqueo [(o remitentes seguros)](create-safe-sender-lists-in-office-365.md) y [bloquear listas](create-block-sender-lists-in-office-365.md).
  
En el siguiente vídeo se muestran los pasos de configuración para la directiva de filtro de conexión:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/b2f5bea3-e1a7-44b3-b7e2-07fac0d0ca40?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Tiempo estimado para finalizar: 15 minutos

- Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "contra el correo electrónico no deseado" en el tema [permisos de características de Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .

- Para obtener la dirección IP del remitente cuyos mensajes quiere permitir o bloquear, consulte el encabezado de Internet del mensaje. Busque el encabezado CIP tal y como se describe en [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md). Para obtener información sobre cómo ver un encabezado de mensaje en varios clientes de correo electrónico, consulte [Message header Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=306583).

- Los mensajes de correo electrónico enviados desde una dirección IP de la lista de IP bloqueadas se rechazan, no se marcan como correo no deseado y no se produce ningún filtro adicional.

- El siguiente procedimiento de filtro de conexión también se puede llevar a cabo mediante PowerShell remoto. Use el cmdlet [Get-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx) para revisar su configuración y [Set-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx) para editar su configuración de directiva de filtro de conexión. Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online Protection, vea [conectarse a PowerShell de Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkid=627290). Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online, vea [Conexión a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

## <a name="use-the-eac-to-edit-the-default-connection-filter-policy"></a>Usar el EAC para editar la directiva de filtro de conexión predeterminada

Puede crear una lista de direcciones IP permitidas o una lista de direcciones IP bloqueadas editando la directiva de filtro de conexión en el Centro de administración de Exchange (EAC). La configuración de la directiva de filtro de conexión se aplica únicamente a los mensajes entrantes.
  
1. En el Centro de administración de Exchange (EAC), vaya a **Protección** \> **Filtro de conexión** y, luego, haga doble clic en la directiva predeterminada.

2. Haga clic en el elemento de menú **Filtrado de conexiones** y, a continuación, cree las listas que desee: una lista de direcciones IP deseadas, una lista de direcciones IP bloqueadas, o ambas.

   Para crear estas listas, haga clic en ![Agregar icono](media/ITPro-EAC-AddIcon.gif). En el cuadro de diálogo que sigue, especifique la dirección IP o el intervalo de direcciones y, a continuación, haga clic en **aceptar**. Repita este proceso para agregar direcciones adicionales. (También puede editar o quitar direcciones IP después de haberlas agregado).

   Especifique direcciones IP IPV4 con el formato NNN. nnn. nnn. nnn donde nnn es un número entre 0 y 255. También puede especificar intervalos de Enrutamiento de interdominios sin clases (CIDR) con el formato nnn.nnn.nnn.nnn/rr, donde rr es un número del 24 al 32. Para especificar intervalos fuera del intervalo de 24 a 32, consulte la siguiente sección, [consideraciones adicionales para configurar listas de direcciones IP permitidas](#additional-considerations-when-configuring-ip-allow-lists).

   > [!NOTE]
   > Si agrega una dirección IP a ambas listas, se permitirá el correo electrónico enviado desde esa dirección IP. <br/><br/> Puede especificar un máximo de 1273 entradas; una entrada es una dirección IP única o un intervalo CIDR de direcciones IP de /24 a /32.<br/><br/> Si va a enviar mensajes con cifrado TLS, no se admiten direcciones IPv6 e intervalos de direcciones.
  
3. Opcionalmente, active la casilla **Habilitar lista segura** para impedir que se pierdan mensajes de determinados remitentes conocidos. ¿Cómo se hace? Microsoft se suscribe a fuentes de terceros de remitentes de confianza. El uso de esta lista segura significa que estos remitentes de confianza no se marcan por error como correo no deseado. Se recomienda seleccionar esta opción porque debe reducir el número de falsos positivos (correo correcto que se ha clasificado como correo no deseado) que recibe. 

4. Haga clic en **Guardar**. En el panel a la derecha, aparece un resumen de la configuración predeterminada de directiva.

## <a name="additional-considerations-when-configuring-ip-allow-lists"></a>Consideraciones adicionales para configurar listas de direcciones IP permitidas

A continuación, se muestran consideraciones adicionales que posiblemente necesite tener en cuenta o que debería conocer a la hora de configurar una lista de direcciones IP permitidas.
  
### <a name="specifying-a-cidr-range-that-falls-outside-of-the-recommended-range"></a>Especificación de un intervalo CIDR que está fuera del intervalo recomendado

Para especificar un intervalo de direcciones IP de CIDR desde/1 hasta/23, debe crear una regla de flujo de correo que opere en el intervalo de direcciones IP que establece el nivel de confianza contra correo no deseado (SCL) para omitir el **filtrado de correo no deseado** (lo que significa que todos los mensajes recibidos desde dentro de este intervalo de direcciones IP están establecer en "no es correo no deseado") y el servicio no realiza ningún filtrado adicional). Sin embargo, si alguna de estas direcciones IP aparece en cualquiera de las listas de bloqueados propias de Microsoft o en cualquiera de nuestras listas de bloqueados de terceros, estos mensajes seguirán bloqueados. Por lo tanto, se recomienda encarecidamente que use el intervalo de direcciones IP de/24 a/32.
  
Para crear esta regla de flujo de correo, siga estos pasos.
  
1. En el EAC, vaya a **Flujo de correo** \> **Reglas**.

2. Click ![Agregar icono](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.

3. Especifique un nombre para la regla y luego haga clic en **Más opciones**.

4. Dentro de **Aplicar esta regla si**, seleccione **El remitente** y luego elija **La dirección IP se encuentra en cualquiera de estos intervalos o coincide exactamente con**.

5. En **especificar direcciones IP**, especifique el intervalo de direcciones IP, haga **** ![clic en agregar](media/ITPro-EAC-AddIcon.gif)icono de agregar y, a continuación, haga clic en **Aceptar**.

6. En el cuadro **Haga lo siguiente**, establezca la acción al elegir **Modificar propiedades del mensaje** y luego **Establecer el nivel de confianza contra correo no deseado (SCL)**. En el cuadro **Especificar SCL**, seleccione **Omitir filtrado contra correo no deseado** y haga clic en **Aceptar**.

7. Si lo desea, puede realizar selecciones para auditar la regla, probarla, activarla durante un período de tiempo específico y otras selecciones. Recomendamos probar la regla durante un tiempo antes de aplicarla. [Procedimientos para reglas de flujo de correo en Exchange Server](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) contiene más información acerca de estas selecciones.

8. Haga clic en **Guardar** para guardar la regla. La regla aparece en la lista de reglas.

Después de crear y aplicar la regla, el servicio omite el filtrado de correo no deseado para el intervalo de direcciones IP que haya especificado.

### <a name="scoping-an-ip-allow-list-exception-for-a-specific-domain"></a>Ámbito de una excepción de lista de direcciones IP permitidas para un dominio específico

En general, recomendamos agregar las direcciones IP (o los intervalos de direcciones IP) para todos los dominios que considere seguros para la lista de direcciones IP permitidas. Sin embargo, si no quiere que la entrada de la lista de direcciones IP permitidas se aplique a todos los dominios, puede crear una regla de flujo de correo (también denominada regla de transporte) que no sea un dominio específico.
  
Por ejemplo, supongamos que tiene tres dominios: ContosoA.com, ContosoB.com y and ContosoC.com y desea agregar la dirección IP (para simplificar el proceso, usaremos la dirección 1.2.3.4) y omitir el filtrado solo para el dominio ContosoB.com. Para ello, deberá crear una lista de direcciones IP permitidas para la dirección 1.2.3.4, que establecerá el nivel de confianza contra correo no deseado (SCL) en -1 (lo que implica que no se clasificará como correo no deseado) para todos los dominios. A continuación, puede crear una regla de flujo de correo que establezca el SCL para todos los dominios excepto ContosoB.com a 0. De este modo, el mensaje se volverá a analizar para todos los dominios asociados a la dirección IP salvo para el dominio ContosoB.com, que es el dominio que figura como excepción en la regla. ContosoB.com seguirá teniendo un SCL de -1, con lo que se omitirá el filtrado, mientras que los dominios ContosoA.com y ContosoC.com tendrán un SCL de 0, lo que implica que el filtro analizará todo el contenido.
  
Para ello, realice los siguientes pasos:
  
1. En el EAC, vaya a **Flujo de correo** \> **Reglas**.

2. Click ![Agregar icono](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.

3. Especifique un nombre para la regla y luego haga clic en **Más opciones**.

4. Dentro de **Aplicar esta regla si**, seleccione **El remitente** y luego elija **La dirección IP se encuentra en cualquiera de estos intervalos o coincide exactamente con**.

5. En el cuadro **especificar direcciones IP** , especifique la dirección IP o el intervalo de direcciones IP que ha especificado en la lista de direcciones IP permitidas, haga clic en **Agregar** ![icono](media/ITPro-EAC-AddIcon.gif)agregar y, a continuación, haga clic en **Aceptar**.

6. En **hacer lo siguiente**, seleccione **modificar las propiedades del mensaje** para establecer la acción y, a continuación, **establezca el nivel de confianza contra correo no deseado (SCL)**. En el cuadro **especificar SCL** , seleccione **0**y, a continuación, haga clic en **Aceptar**.

7. Haga clic en **Agregar excepción**y, en **excepto si**, seleccione **el remitente** y elija el **dominio es**.

8. En el cuadro **especificar dominio** , escriba el dominio para el que desea omitir el filtrado de correo no deseado, como **contosob.com**. Haga **** ![clic en agregar](media/ITPro-EAC-AddIcon.gif) icono para agregarlo para moverlo a la lista de frases. Repita este paso si desea agregar dominios adicionales como excepciones y haga clic en **Aceptar** cuando finalice. 

9. Si lo desea, puede realizar selecciones para auditar la regla, probarla, activarla durante un período de tiempo específico y otras selecciones. Recomendamos probar la regla durante un tiempo antes de aplicarla. [Procedimientos para reglas de flujo de correo en Exchange Server](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) contiene más información acerca de estas selecciones.

10. Haga clic en **Guardar** para guardar la regla. La regla aparece en la lista de reglas.

Después de crear y aplicar la regla, solo se omitirá el filtrado contra correo no deseado para la dirección IP o el intervalo de direcciones IP de la excepción de dominio especificada.

### <a name="scenarios-where-allowed-ip-addresses-are-still-filtered"></a>Escenarios en los que se siguen filtrando direcciones IP permitidas

Los mensajes de las direcciones IP permitidas que haya configurado en las directivas de filtro de conexión todavía están sujetos al filtrado de correo no deseado en las siguientes situaciones:

- La dirección IP de origen de la Directiva de filtro de conexión también se configura en un conector de entrada basado en IP local en *cualquier* inquilino (vamos a llamar a este inquilino a), **y** al inquilino a y al servidor de Exchange Online Protection que encuentra por primera vez el mensaje en Office 365 ambos suceden en el mismo bosque de Active Directory en los centros de recursos de Microsoft. En este escenario, **IPV: cal** se agrega a los encabezados de los [mensajes contra correo no deseado](anti-spam-message-headers.md) del mensaje (lo que indica que el mensaje ha omitido el filtrado de correo no deseado), pero el mensaje sigue sujeto al filtrado de correo no deseado.

- Su espacio empresarial (donde haya configurado la Directiva de filtro de conexión) y el servidor de Exchange Online Protection que encuentra el mensaje en Office 365, ambos suceden en bosques de Active Directory diferentes en los centros de recursos de Microsoft. En este escenario, **IPV: cal** no se agrega a los encabezados de los mensajes, por lo que el mensaje sigue sujeto al filtrado de correo no deseado.

Si encuentra alguno de estos escenarios, puede crear una regla de flujo de correo en el EAC con (como mínimo) la siguiente configuración para garantizar que los mensajes de la dirección IP o direcciones eluden el filtrado de correo no deseado:

- Condición de regla **: aplique esta regla si** \> **la dirección IP del remitente** \> **está en cualquiera de estos intervalos o coincide exactamente con** \> la dirección o las direcciones IP.

- Acción de regla: **modifique las propiedades** \> del mensaje **establecer el nivel de confianza contra correo no deseado (SCL)** \> **pasar por alto el filtrado de correo no deseado**.

Básicamente es el mismo procedimiento de creación de reglas desde el [ámbito anterior de una excepción de lista de direcciones IP permitidas para una sección de dominio específica](#scoping-an-ip-allow-list-exception-for-a-specific-domain) .

## <a name="new-to-office-365"></a>¿Es la primera vez que usa Office 365?

||
|:-----|
|![El icono reducido de LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **¿Es la primera vez que usa Office 365?** LinkedIn Learning pone a su disposición vídeos gratuitos de cursos de **Office 365 admins and IT pros**.|

## <a name="for-more-information"></a>Más información

[Listas de remitentes seguros y bloqueados en Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)
  
[Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md)
  
[Configurar la directiva de correo no deseado saliente](configure-the-outbound-spam-policy.md)
  
[Cómo ayudar a garantizar que un mensaje no se marque como correo no deseado](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[Bloquear el correo no deseado con el filtro de correo no deseado de Office 365 para evitar problemas de negativos falsos](https://go.microsoft.com/fwlink/p/?LinkId=534225)

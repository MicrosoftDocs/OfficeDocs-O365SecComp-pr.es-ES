---
title: Configurar la directiva de filtro de conexión
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/24/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
description: Para asegurarse de que no se bloquea el correo electrónico enviado desde usuarios de que confianza, puede usar la directiva de filtro de conexión para crear una lista de permitir, también conocido como una lista de remitentes seguros, de direcciones IP de confianza. También puede crear una lista de remitentes bloqueados.
ms.openlocfilehash: 2f8ec3d01de4358d7394c68d0efae9222db08282
ms.sourcegitcommit: a07b91723bae9ecee2cb092bfbc5b208b30b11a1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "25793565"
---
# <a name="configure-the-connection-filter-policy"></a>Configurar la directiva de filtro de conexión
 
La mayoría de nosotros tenemos amigos y socios comerciales en los que confiamos. Puede resultar frustrante encontrar correo electrónico de ellos en la carpeta de correo electrónico no deseado o incluso bloqueado totalmente por un filtro contra correo no deseado. Si desea asegurarse de que el correo electrónico que le envían las personas en las que confía no se bloquea, puede usar la directiva de filtro de conexión para crear una lista de direcciones IP permitidas, también conocida como lista de remitentes seguros, en las que confía. También puede crear una lista de remitentes bloqueados, que es una lista de direcciones IP, normalmente de spammers conocidos, de las que nunca quiere recibir mensajes de correo electrónico.
  
 Para obtener más información sobre configuración de correo no deseado que se aplica a toda la organización, consulte [Cómo ayudar a garantizar que un mensaje no se marque como correo no deseado](https://go.microsoft.com/fwlink/p/?LinkId=534224) o [Bloquear el correo no deseado con el filtro de correo no deseado de Office 365 para evitar problemas de negativos falsos](https://go.microsoft.com/fwlink/p/?LinkId=534225). Estos son útiles si tiene control de nivel de administrador y desea evitar falsos positivos o negativos falsos.
  
En el siguiente vídeo se muestran los pasos de configuración para la directiva de filtro de conexión:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/b2f5bea3-e1a7-44b3-b7e2-07fac0d0ca40?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?
<a name="sectionSection0"> </a>

- Tiempo estimado para completarlo: 15 minutos
    
- Debe tener asignados los permisos puede llevar a cabo estos procedimientos. Para ver qué permisos necesita, vea la entrada "Contra correo no deseado" en el tema [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) . 
    
- Para obtener la dirección IP del remitente cuyos mensajes desea permitir o bloquear, puede comprobar el encabezado de Internet del mensaje. Busque el encabezado CIP tal como se describe en [los encabezados de mensaje contra correo no deseado](anti-spam-message-headers.md). Para obtener información acerca de cómo ver un encabezado de mensaje en diversos clientes de correo electrónico, vea [Analizador de encabezado de mensaje](https://go.microsoft.com/fwlink/p/?LinkId=306583). 
    
- Los mensajes de correo electrónico enviados desde una dirección IP de la lista de IP bloqueadas se rechazan, no se marcan como correo no deseado y no se produce ningún filtro adicional.
    
- El siguiente procedimiento de filtro de conexión también se puede realizar mediante PowerShell remoto. Use el cmdlet [Get-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx) para revisar la configuración y el [Set-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx) para editar la configuración de directiva de filtro de conexión. Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online Protection, vea [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290). Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online, vea [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
## <a name="use-the-eac-to-edit-the-default-connection-filter-policy"></a>Usar el EAC para editar la directiva de filtro de conexión predeterminada
<a name="sectionSection1"> </a>

Puede crear una lista de direcciones IP permitidas o una lista de direcciones IP bloqueadas editando la directiva de filtro de conexión en el Centro de administración de Exchange (EAC). La configuración de la directiva de filtro de conexión se aplica únicamente a los mensajes entrantes.
  
1. En el Centro de administración de Exchange (EAC), vaya a **Protección** \> **Filtro de conexión** y, luego, haga doble clic en la directiva predeterminada.
    
2. Haga clic en el elemento de menú **Filtrado de conexiones** y, a continuación, cree las listas que desee: una lista de direcciones IP deseadas, una lista de direcciones IP bloqueadas, o ambas. 
    
    Para crear estas listas, haga clic en ![Agregar icono](media/ITPro-EAC-AddIcon.gif). En el cuadro de diálogo que sigue, especifique la dirección IP o el intervalo de direcciones y, a continuación, haga clic en **aceptar**. Repita este proceso para agregar direcciones adicionales. (También puede editar o quitar direcciones IP después de haberlas agregado).
    
    > [!NOTE]
    >  Si agrega una dirección IP a ambas listas, se permite el correo electrónico enviado desde esa dirección IP. 

    Especifique las direcciones IP de IPV4 en la nnn.nnn.nnn.nnn formato donde nnn es un número entre 0 y 255. También puede especificar intervalos de enrutamiento entre dominios sin clases (CIDR) en el nnn.nnn.nnn.nnn/rr formato donde rr es un número de 24 a 32. Para especificar intervalos fuera del intervalo de 24 a 32, vea [listas de consideraciones adicionales al configurar direcciones IP permitidas](configure-the-connection-filter-policy.md#bkmk_addtionalconsiderationswhenconfiguringipallowlists). 

    Puede especificar un máximo de 1273 entradas, donde una entrada es una sola dirección IP o un CIDR intervalo de direcciones IP de/24 a/32. > Si va a enviar mensajes cifrados mediante TLS, no se admiten las direcciones IPv6 y los intervalos de direcciones. 
  
3. Opcionalmente, active la casilla de verificación **Habilitar lista segura** para evitar que falta el correo electrónico de determinados remitentes conocidos. ¿Cómo? Microsoft se suscribe a orígenes de terceros de remitentes de confianza. Con esta lista segura significa que estos confianza remitentes no se marquen erróneamente como correo no deseado. Se recomienda seleccionar esta opción, ya que debe reducir el número de falsos positivos (correo correcto que se clasifica como correo no deseado) que recibe. 
    
4. Haga clic en **Guardar**. En el panel a la derecha, aparece un resumen de la configuración predeterminada de directiva.
    
## <a name="additional-considerations-when-configuring-ip-allow-lists"></a>Consideraciones adicionales para configurar listas de direcciones IP permitidas
<a name="bkmk_addtionalconsiderationswhenconfiguringipallowlists"> </a>

A continuación, se muestran consideraciones adicionales que posiblemente necesite tener en cuenta o que debería conocer a la hora de configurar una lista de direcciones IP permitidas.
  
### <a name="specifying-a-cidr-range-that-falls-outside-of-the-recommended-range"></a>Especificación de un intervalo CIDR que está fuera del intervalo recomendado

Para especificar un intervalo de direcciones IP CIDR desde /1 a /23, debe crear una regla de flujo de correo que opera en el intervalo de direcciones IP que establece el nivel de confianza de correo no deseado (SCL) para **el desvío de correo no deseado filtrado** (lo que significa que todos los mensajes recibidos desde dentro de este intervalo de direcciones IP se establece en "no de correo no deseado") y filtrado adicionales no se lleva a cabo por el servicio). Sin embargo, si cualquiera de estas direcciones IP aparecen en cualquiera de los bloques propietario de Microsoft se enumeran o en cualquiera de nuestro bloqueo de otro fabricante listas, aún se bloqueará estos mensajes. Por lo tanto, se recomienda encarecidamente que utilice el intervalo de direcciones IP de /24 a /32. 
  
Para crear esta regla de flujo de correo, realice los pasos siguientes.
  
1. En el EAC, vaya a **Flujo de correo** \> **Reglas**.
    
2. Click ![Agregar icono](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.
    
3. Especifique un nombre para la regla y luego haga clic en **Más opciones**.
    
4. Dentro de **Aplicar esta regla si**, seleccione **El remitente** y luego elija **La dirección IP se encuentra en cualquiera de estos intervalos o coincide exactamente con**.
    
5. En **especificar direcciones IP**, especifique el intervalo de direcciones IP, haga clic en **Agregar** ![icono Agregar](media/ITPro-EAC-AddIcon.gif)y, a continuación, haga clic en **Aceptar**.
    
6. En el cuadro **Haga lo siguiente**, establezca la acción al elegir **Modificar propiedades del mensaje** y luego **Establecer el nivel de confianza contra correo no deseado (SCL)**. En el cuadro **Especificar SCL**, seleccione **Omitir filtrado contra correo no deseado** y haga clic en **Aceptar**.
    
7. Si lo desea, puede realizar las selecciones para la regla de auditoría, probar la regla, active la regla durante un período de tiempo específico y otras selecciones. Se recomienda probar la regla para un período antes de aplicarlo. [Reglas de procedimientos para el flujo de correo en Exchange Server](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) contiene más información acerca de estas opciones seleccionadas. 
    
8. Haga clic en **Guardar** para guardar la regla. La regla aparecerá en la lista de reglas. 
    
Después de crear y aplicar la regla, el servicio pasa por alto deseado filtrado para el intervalo de direcciones IP.
  
### <a name="scoping-an-ip-allow-list-exception-for-a-specific-domain"></a>Ámbito de una excepción de lista de direcciones IP permitidas para un dominio específico

En general, recomendamos agregar las direcciones IP (o los intervalos de direcciones IP) para todos los dominios que considere seguros para la lista de direcciones IP permitidas. Sin embargo, si no desea que su entrada de lista de direcciones IP permitidas se aplique a todos los dominios, puede crear una regla de transporte que excluya dominios específicos. 
  
Por ejemplo, supongamos que tiene tres dominios: ContosoA.com, ContosoB.com y and ContosoC.com y desea agregar la dirección IP (para simplificar el proceso, usaremos la dirección 1.2.3.4) y omitir el filtrado solo para el dominio ContosoB.com. Para ello, deberá crear una lista de direcciones IP permitidas para la dirección 1.2.3.4, que establecerá el nivel de confianza contra correo no deseado (SCL) en -1 (lo que implica que no se clasificará como correo no deseado) para todos los dominios. A continuación, podrá crear una regla de transporte que establezca el SCL de todos los dominios en 0 excepto para el dominio ContosoB.com. De este modo, el mensaje se volverá a analizar para todos los dominios asociados a la dirección IP salvo para el dominio ContosoB.com, que es el dominio que figura como excepción en la regla. ContosoB.com seguirá teniendo un SCL de -1, con lo que se omitirá el filtrado, mientras que los dominios ContosoA.com y ContosoC.com tendrán un SCL de 0, lo que implica que el filtro analizará todo el contenido.
  
Para ello, realice los siguientes pasos:
  
1. En el EAC, vaya a **Flujo de correo** \> **Reglas**.
    
2. Click ![Agregar icono](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.
    
3. Especifique un nombre para la regla y luego haga clic en **Más opciones**.
    
4. Dentro de **Aplicar esta regla si**, seleccione **El remitente** y luego elija **La dirección IP se encuentra en cualquiera de estos intervalos o coincide exactamente con**.
    
5. En el cuadro **especificar direcciones IP** , especifique la dirección IP o el intervalo de direcciones IP que escribió en la lista de direcciones IP permitidas, haga clic en **Agregar** ![icono Agregar](media/ITPro-EAC-AddIcon.gif)y, a continuación, haga clic en **Aceptar**.
    
6. Dentro de **Haga lo siguiente**, establezca la acción al elegir **Modificar propiedades del mensaje** y luego **Establecer el nivel de confianza contra correo no deseado (SCL)**. En el cuadro **Especificar SCL**, seleccione **0** y haga clic en **Aceptar**.
    
7. Haga clic en **Agregar excepción** y, dentro de **Excepto si**, seleccione **El remitente** y elija **El dominio es**. 
    
8. En el cuadro **Especificar dominio** , escriba el dominio para el que desea omitir el filtrado de spam, como **contosob.com**. Haga clic en **Agregar** ![icono Agregar](media/ITPro-EAC-AddIcon.gif) para moverlo a la lista de frases. Repita este paso si desea agregar dominios adicionales como excepciones y haga clic en **Aceptar** cuando haya terminado. 
    
9. Si lo desea, puede realizar las selecciones para la regla de auditoría, probar la regla, active la regla durante un período de tiempo específico y otras selecciones. Se recomienda probar la regla para un período antes de aplicarlo. [Reglas de procedimientos para el flujo de correo en Exchange Server](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) contiene más información acerca de estas opciones seleccionadas. 
    
10. Haga clic en **Guardar** para guardar la regla. La regla aparecerá en la lista de reglas. 
    
Después de crear y aplicar la regla, solo se omitirá el filtrado contra correo no deseado para la dirección IP o el intervalo de direcciones IP de la excepción de dominio especificada.
  
## <a name="new-to-office-365"></a>¿Es la primera vez que usa Office 365?
<a name="sectionSection3"> </a>

||
|:-----|
|![El icono reducido de LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **¿Es la primera vez que usa Office 365?**         LinkedIn Learning pone a su disposición vídeos gratuitos de cursos de **Office 365 admins and IT pros**. |
   
## <a name="for-more-information"></a>Para obtener más información
<a name="sectionSection4"> </a>

[Listas de remitentes seguros y bloqueados en Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)
  
[Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md)
  
[Configurar la directiva de correo no deseado saliente](configure-the-outbound-spam-policy.md)
  
[Cómo ayudar a garantizar que un mensaje no se marque como correo no deseado](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[Bloquear el correo no deseado con el filtro de correo no deseado de Office 365 para evitar problemas de negativos falsos](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  


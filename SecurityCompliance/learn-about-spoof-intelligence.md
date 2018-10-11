---
title: Obtenga más información sobre la inteligencia de suplantación de identidad
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/14/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
description: Usar suplantación de la inteligencia de la seguridad &amp; centro de cumplimiento en la página de configuración contra correo no deseado para revisar todos los remitentes que los dominios que forman parte de la organización de suplantación de identidad, o de dominios externos de suplantación de identidad. Suplantación de la inteligencia está disponible como parte de Office 365 Enterprise E5 o por separado como parte de la protección contra amenazas de avanzada y Exchange Online Protection.
ms.openlocfilehash: 3be606c05dde4a13d3a6a4a43ce927cf4f0ca53c
ms.sourcegitcommit: 176ce86e2b440c079414fe99d4b0b9e89ccebb40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2018
ms.locfileid: "25496561"
---
# <a name="learn-more-about-spoof-intelligence"></a>Obtenga más información sobre la inteligencia de suplantación de identidad

Usar suplantación de la inteligencia de la seguridad &amp; centro de cumplimiento en la **página de configuración contra correo no deseado** para revisar todos los remitentes que los dominios que forman parte de la organización de suplantación de identidad, o de dominios externos de suplantación de identidad. Suplantación de la inteligencia está disponible como parte de Office 365 Enterprise E5 o por separado como parte de la protección de amenaza avanzada (ATP) y a partir de octubre, 2018 Exchange Online Protection (EOP). 
  
## <a name="what-types-of-email-spoofing-can-i-review-and-which-should-i-protect-against-with-spoof-intelligence"></a>¿Qué tipos de suplantación de identidad de correo electrónico se debe revisar y que debo proteger contra con inteligencia de suplantación?

Para dominios de propios, se pueden revisar los remitentes que son suplantación de su dominio y, a continuación, elija Permitir que el remitente continuar o bloquear al remitente. Para dominios externos, puede permitir que el dominio del remitente combinado con la infraestructura de envía, aunque no individuales envío dirección de correo electrónico.
  
Cuando un remitente suplanta una dirección de correo electrónico, aparecen va a enviar correo en nombre de una o más cuentas de usuario dentro de uno de los dominios de la organización, o un dominio externo que se envía a su organización. Sorprendentemente, hay algunos motivos comerciales legítimos de suplantación de identidad. Por ejemplo, en estos casos, no bloquear al remitente de su dominio de suplantación de identidad:
  
- Tienen remitentes de terceros que usen su dominio para enviar correo masivo a sus propios empleados de sondeos de la compañía.
    
- Ha contratado a una empresa externa para generar y enviar publicidad o actualizaciones del producto en su nombre.
    
- Un asistente que necesita con regularidad para enviar correo electrónico para otra persona dentro de la organización.
    
- Una aplicación que está configurada para suplantar la propia organización con el fin de enviar notificaciones internas por correo electrónico.
    
Dominios externos con frecuencia envían correo electrónico simulado y muchos de estos motivos son legítimos. Por ejemplo, presentamos algunos casos legítimos que los remitentes externos envían correo electrónico simulado:
  
- El remitente está en una lista de distribución de correo de discusión y la lista de correo es la retransmisión del correo electrónico del remitente original a todos los participantes en la lista de correo.
    
- Una empresa externa está enviando correo electrónico en nombre de otra empresa (por ejemplo, un informe de automatizada o una compañía de software como servicio).
    
Se necesita una forma para asegurarse de que el correo enviado por legítimos suplantadores de la identidad no centrarse en filtros de spam en Office 365 o sistemas de correo electrónico externa. Normalmente, Office 365 trata estos mensajes de correo electrónico como correo no deseado. Como un administrador de Office 365, tiene la capacidad para evitar que esto mediante la configuración de filtros de réplicas en la seguridad &amp; centro de cumplimiento. Si el propietario del dominio, puede configurar SPF, DKIM y DMARC para permitir estos remitentes.
  
Por otro lado, malintencionados suplantadores de la identidad, los remitentes que son suplantación de su dominio o dominios externos, para enviar correo electrónico de correo no deseado o suplantación de identidad, necesitan se va a bloquear. Suplantación de identidad también es una manera común para los suplantadores de identidad obtener las credenciales de usuario. Office 365 tiene protección integrada simulado para ayudar a proteger la organización de los remitentes de estos mensajes de correo electrónico. Suplantación de la protección de dominios de la organización siempre está activada para todos los clientes de Office 365 y la protección de suplantación de la de dominio externo está activada de forma predeterminada para los clientes de protección contra amenazas de avanzada y a partir de octubre de 2018 EOP así como los clientes. Para reforzar aún más esta protección, Díganos qué remitentes tienen autorización para imitar dominios de la organización y enviar correo electrónico en su nombre y, si todos los dominios externos tiene permiso para suplantar. Cualquier correo electrónico enviado desde un remitente que no autorice se tratará como correo no deseado o suplantación de identidad por Office 365. Mantenerse al tanto de los remitentes de su dominio de suplantación de identidad y nos ayudará a mejorar la suplantación de la inteligencia mediante el uso de la seguridad &amp; centro de cumplimiento.
  
## <a name="managing-spoof-intelligence-in-the-security-amp-compliance-center"></a>Administración de suplantación de la inteligencia de la seguridad &amp; centro de cumplimiento
<a name="Managespooflist"> </a>

Siempre se aplica la directiva de inteligencia de suplantación de la de que configuración Office 365. No se puede deshabilitar, pero puede elegir cuánto desea administrarlo activamente.
  
Puede revisar los remitentes que son suplantación de identidad su dominio o dominios externos y, a continuación, decidir si se debe permitir cada remitente para hacerlo mediante el uso de la seguridad &amp; centro de cumplimiento. Para cada cuenta de usuario suplantado que un remitente suplanta desde su dominio o un dominio externo, puede ver la información en la tabla siguiente.
  
|**Parámetro**|**Descripción**|
|:-----|:-----|
|Sender  <br/> |También se denomina el remitente es true. Esto suele ser el dominio desde el que se origina el correo electrónico falso. Office 365 determina el dominio del puntero de registro DNS (PTR) de la dirección IP de envío que es la falsificación de la organización. Si no se encuentra ningún dominio, el informe muestra la dirección IP del remitente en su lugar.  <br/> |
|Usuario suplantado  <br/> |La cuenta de usuario que se va a suplantar por el remitente.  <br/> Ficha de **interno** . Este campo contiene una dirección de correo electrónico única, o si el remitente es la falsificación de varias cuentas de usuario, que contiene **más de uno**.<br/> Ficha **externo** . Dominios externos sólo contienen un dominio envío y no contienen una dirección de correo electrónico completa.<br/> > [!TIP]> **Para los administradores avanzados.** El usuario suplantado es el campo de dirección (5322.From) que también es la dirección que se muestra como la dirección de origen por el cliente de correo. En ocasiones, esto se denomina la dirección header.from. Esta validez de esta dirección no está protegida por SPF.           |
|Número de mensajes  <br/> |El número de mensajes de correo enviados por el remitente a su organización en nombre del remitente falsificada identificado o los remitentes dentro de los últimos 30 días.  <br/> |
|Número de quejas del usuario  <br/> |Reclamaciones presentadas por los usuarios contra este remitente por los usuarios dentro de los últimos 30 días. Quejas normalmente están en el formulario de envíos no deseados a Microsoft.  <br/> |
|Resultado de la autenticación  <br/> |Este valor es **pasa** si el remitente pasado a remitente de Exchange Online Protection (EOP) comprobaciones de autenticación, como SPF o DKIM, **no se pudo** si el remitente no pudo comprobaciones de autenticación de remitente de elevación de privilegios o **desconocido** si no es el resultado de estos controles conocidos.  <br/> |
|Decisión establecido por  <br/> |Muestra si el Administrador de Office 365 o la directiva de inteligencia de suplantación de la que se determina si se permite el remitente para suplantar al usuario.  <br/> |
|Visto por última vez  <br/> |La última fecha en la que se recibió un mensaje de este remitente en nombre de este usuario suplantado.  <br/> |
|¿Permiso para suplantar?  <br/> | Muestra si o no se permite este remitente para enviar correo electrónico en nombre del usuario suplantado. Los valores posibles son:<br/> **Sí** Todas las direcciones suplantadas desde este remitente suplantación podrán suplantar la organización.  <br/> **No** Direcciones suplantadas desde este remitente de suplantación de identidad no se pueden suplantar la organización. En su lugar, los mensajes de este remitente se marcarán como correo no deseado por Office 365.<br/> **Algunos usuarios** Si un remitente es la falsificación de varios usuarios, algunos direcciones suplantadas desde este remitente podrán suplantar la organización, el resto se marcarán como correo no deseado. Use la ficha **Detailed** para ver las direcciones específicas.<br/> |
|Tipo de suplantación  <br/> |Este valor es **interno** si el dominio es uno de los dominios aprovisionados de su organización, en caso contrario, el valor es **externo**.  <br/> |
   
 **Para administrar los remitentes que son suplantación de su dominio mediante el uso de la seguridad &amp; centro de cumplimiento**
  
1. Vaya a la [seguridad &amp; centro de cumplimiento](https://protection.office.com).
    
2. Inicie sesión con su cuenta de trabajo o escuela en Office 365. La cuenta debe tener credenciales de administrador de la organización de Office 365.
    
3. En la seguridad &amp; centro de cumplimiento, expanda **Administración de amenaza** \> **Directiva** \> **contra correo no deseado**.
  
![](media/0a098e68-5ecf-40d7-984f-d15fcc1f958d.jpg)
  
4. En la página de **configuración de correo no deseado** en el panel derecho, seleccione la ficha **personalizado** y, a continuación, desplácese hacia abajo y expanda **Directiva de suplantación de la inteligencia**. 
  
![](media/a5112100-0b37-460f-932d-5b2f98157871.jpg)
  
5. Para ver la lista de remitentes de su dominio de suplantación de identidad, elija **nueva remitentes de revisión** y seleccione el ** dominios Your ** ficha. 
    
    Si ya ha revisado los remitentes y desea cambiar algunas de las opciones anteriores, puede elegir **Mostrarme remitentes contenida** en su lugar. En cualquier caso, aparece el siguiente panel. 
  
![](media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)
  
Cada usuario suplantado se muestra en una fila independiente, por lo que puede elegir si desea permitir o bloquear al remitente de suplantación de identidad cada usuario individualmente.
  
Para agregar un remitente a la lista Permitir de un usuario, seleccione **Sí** en la columna **permitido para suplantar** . Para agregar un remitente a la lista de bloqueo para un usuario, elija **No**.
  
Para establecer la directiva para dominios no es el propietario, seleccione la ficha **Dominios externos** cambiar cualquier remitente en **Sí** en la columna **permitido a Falso** para permitir que el remitente a enviar correo electrónico sin autenticar en su organización. Como alternativa, si piensa que Office 365 ha realizado un error en lo que permite que el remitente para enviar correo electrónico simulado, cambie la columna **permitido para suplantar** a **No**. 
  
![](media/5dbef9cf-103f-49cd-9638-4b0083d6baa7.jpg)
  
6. Elija **Guardar** para guardar los cambios. 

Si usted es un cliente E5 o ATP, también puede administrar los remitentes que son de su dominio a través de la [Suplantación de la inteligencia Insight](https://docs.microsoft.com/en-us/office365/securitycompliance/walkthrough-spoof-intelligence-insight) suplantación
    
## <a name="configuring-the-anti-spoofing-policy"></a>Configuración de la directiva contra la suplantación
<a name="Managespooflist"> </a>

Además de permitir o bloquear a un remitente concreto de envío de correo electrónico simulado en su organización, también puede configurar estricto cómo desea que el filtro que se va, la acción que se realizará cuando se encuentra un mensaje de suplantación de identidad y si se deben habilitar sugerencias de seguridad para contra la suplantación.
  
Protección contra la suplantación se aplica a correo electrónico de los remitentes de dominios que son externos a la organización de Office 365. Puede aplicar la directiva a los destinatarios cuyos buzones de correo se concede bajo licencia para Office 365 Enterprise E5, protección avanzada de amenaza y a partir de octubre, así como los clientes de EOP de 2018. Administrar la directiva contra la suplantación junto con las demás opciones contra suplantación de identidad. Para obtener más información acerca de la configuración contra suplantación de identidad, vea [configurar las directivas contra suplantación de identidad de Office 365](https://support.office.com/article/set-up-office-365-atp-anti-phishing-policies-5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578?ui=en-US&amp;rs=en-US&amp;ad=US#phishpolicyoptions).
  
Office 365 incluye la protección contra la suplantación predeterminada que siempre se ejecuta. Esta protección predeterminada no está visible en la seguridad &amp; centro de cumplimiento o se puede recuperar a través de los cmdlets de Windows PowerShell. No se puede modificar la protección contra la suplantación de forma predeterminada. En su lugar, puede configurar cómo estrictamente Office 365 aplica la protección contra la suplantación en cada directiva contra suplantación de identidad que cree. 
  
Aunque la directiva contra la suplantación aparece bajo la directiva contra suplantación de identidad en la seguridad &amp; centro de cumplimiento, no heredan su comportamiento predeterminado de la suplantación de identidad existente en la configuración contra correo no deseado de la configuración. Si tiene una configuración en **contra correo no deseado** \> **suplantación de identidad** que se desea replicar para contra la suplantación, tendrá que crear una directiva contra suplantación de identidad, a continuación, modifique la parte de suplantación de la directiva contra suplantación de identidad para reflejar la configuración de suplantación como se describe en la sección siguiente, en lugar de aceptar la configuración predeterminada que se ejecutan en segundo plano. 
  
 **Para configurar la protección contra la suplantación dentro de una directiva contra suplantación de identidad mediante el uso de la seguridad &amp; centro de cumplimiento**
  
1. Vaya a la [seguridad &amp; centro de cumplimiento](https://protection.office.com).
    
2. Inicie sesión con su cuenta de trabajo o escuela en Office 365. La cuenta debe tener credenciales de administrador de la organización de Office 365.
    
3. En la seguridad &amp; centro de cumplimiento, expanda **Administración de amenaza** \> **Directiva** \> **contra suplantación de identidad**. 
    
4. En la página **contra suplantación de identidad** en el panel derecho, seleccione la directiva contra suplantación de identidad que desea configurar. 
    
5. En la página que aparece, en la fila de **suplantación** , elija **Editar**. 
    
6. A continuación, configure las acciones llevar a cabo cuando se detecta un mensaje como suplantación entre dominios. El comportamiento predeterminado es mover el mensaje a la carpeta de correo electrónico no deseado del destinatario. La otra opción es enviar el mensaje a la cuarentena. Para obtener más información acerca de cómo administrar los mensajes que se envían a cuarentena, consulte [los mensajes de correo electrónico de cuarentena en Office 365](quarantine-email-messages.md).
  
![](media/7a868dff-2c4b-46b9-88ca-f2d523ca2307.jpg)(
  
7. Elija si desea habilitar o deshabilitar las sugerencias de seguridad contra la suplantación. Office 365, recomienda habilitar la sugerencia de seguridad **se produce un error en la autenticación** para advertir a los usuarios cuando se evaluará su interacción con un remitente no se pudo comprobar cuya identidad. Office 365 también recomienda habilitar la sugerencia de seguridad para una **autenticación de paso temporalmente** de grupos más pequeños de usuarios, debido a que esta sugerencia de seguridad puede generar una gran cantidad de advertencias si el usuario recibe un correo electrónico de muchos orígenes legítimos, pero sin autenticar. 
  
![](media/1ed675c0-48c2-4587-a957-60eb68dc9628.jpg)
  
Asegúrese de su elección y, a continuación, seleccione **Guardar**. 
    
## <a name="other-ways-to-manage-spoofing-and-phishing-with-office-365"></a>Otras maneras de administrar la suplantación de identidad y suplantación de identidad con Office 365
<a name="Managespooflist"> </a>

Ser diligente acerca de la protección de suplantación de identidad y suplantación de identidad. Estas son formas relacionados para comprobar en su dominio de suplantación de identidad de los remitentes y ayudar a impedir que perjudican la organización:
  
- Consulte el informe de correo de suplantación de la protección en línea de Exchange como parte de la rutina. Puede usar este informe a menudo para ver y ayudar a administrar los remitentes falsos. Para obtener información, vea **informe de correo de suplantación** en los [informes de protección de correo de uso en Office 365 para ver datos sobre malware, correo no deseado y detecciones de regla](https://technet.microsoft.com/library/dn500744%28v=exchg.150%29.aspx).
    
- Para los administradores de Office 365 más avanzados:
    
  - Revise la configuración del marco de directivas de remitentes (SPF). Para obtener una introducción rápida a SPF y para obtenerlo configurado rápidamente, vea [Set up SPF en Office 365 para ayudar a evitar la suplantación de identidad](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx). Para obtener una descripción más detallada de cómo Office 365 usa SPF, o para las implementaciones de solución de problemas o no estándar, como las implementaciones híbridas, empiece con [cómo Office 365 usa el marco de directivas de remitentes (SPF) para evitar la suplantación de identidad](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx).
    
  - Revise la configuración de correo identificado por claves de dominio (DKIM). Debe usar DKIM además de SPF y DMARC para ayudar a evitar suplantadores de la identidad de envío de mensajes que parecen provenir de su dominio. DKIM le permite agregar una firma digital a los mensajes de correo electrónico en el encabezado del mensaje. Para obtener información, vea [Uso de DKIM para validar el correo electrónico saliente enviado desde su dominio en Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx).
    
  - Revise la configuración de autenticación de mensajes, informes y conformidad (DMARC) basada en dominio. Implementación de DMARC con SPF y DKIM proporciona protección adicional contra el correo electrónico de suplantación de identidad y suplantación de identidad. Ayuda DMARC sistemas de correo de recepción determinan qué hacer con los mensajes enviado desde su dominio que comprueba fail SPF o DKIM. Para obtener información, vea [Usar DMARC para validar el correo electrónico en Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).
    
  - Use el cmdlet [Get-PhishFilterPolicy](https://technet.microsoft.com/en-us/library/mt735158%28v=exchg.160%29.aspx) Windows PowerShell para recopilar datos detallados sobre remitentes falsos, generar permitir y bloquear las listas y le ayudará a determinar cómo generar registros de SPF, DKIM y DMARC DNS más integrales sin necesidad de su correo electrónico legítimo obtener capturados en filtros de spam externo. Para obtener más información, vea [cómo funciona la protección de antispoofing en Office 365](https://blogs.msdn.microsoft.com/tzink/2016/02/23/how-antispoofing-protection-works-in-office-365/).
    


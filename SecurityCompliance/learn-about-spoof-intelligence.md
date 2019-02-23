---
title: Obtener más información sobre la inteligencia de suplantación de identidad
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/22/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
description: Use inteligencia de identidad en el &amp; centro de seguridad y cumplimiento en la página Configuración contra correo no deseado para revisar todos los remitentes que suplantan dominios que forman parte de la organización o suplantación de dominios externos. La inteligencia de identidad está disponible como parte de Office 365 Enterprise E5 o por separado como parte de la protección contra amenazas avanzada y de Exchange Online Protection.
ms.openlocfilehash: b8c791dc47198fa0da08dec1de6fdab8ebfbdb32
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214847"
---
# <a name="learn-more-about-spoof-intelligence"></a>Obtener más información sobre la inteligencia de suplantación de identidad

Use inteligencia de identidad en el &amp; centro de seguridad y cumplimiento en la **página Configuración contra correo no deseado** para revisar todos los remitentes que suplantan dominios que forman parte de la organización o suplantación de dominios externos. La inteligencia de identidad está disponible como parte de Office 365 Enterprise E5 o por separado como parte de la protección contra amenazas avanzada (ATP) y de octubre de 2018 Exchange Online Protection (EOP). 
  
## <a name="what-types-of-email-spoofing-can-i-review-and-which-should-i-protect-against-with-spoof-intelligence"></a>¿Qué tipos de falsificación de correo electrónico puedo revisar y con qué protegerse con inteligencia de suplantación?

Para los dominios que son de su propiedad, puede revisar los remitentes que están suplantando su dominio y, a continuación, elegir permitir que el remitente continúe o bloquee el remitente. Para los dominios externos, puede permitir el dominio del remitente combinado con la infraestructura de envío, aunque no es una dirección de correo electrónico de envío individual.
  
Cuando un remitente suplanta una dirección de correo electrónico, parece que envía correo en nombre de una o varias cuentas de usuario dentro de uno de los dominios de la organización, o bien un dominio externo que envía a su organización. Sorprendentemente, hay razones empresariales legítimas para la suplantación de identidad. Por ejemplo, en estos casos, no impedirá que el remitente falsifique su dominio:
  
- Tiene remitentes de terceros que usan el dominio para enviar correo masivo a sus propios empleados para los sondeos de la compañía.
    
- Ha contratado a una compañía externa para generar y enviar anuncios o actualizaciones de productos en su nombre.
    
- Un asistente que tiene que enviar un correo electrónico a otra persona de la organización con regularidad.
    
- Una aplicación configurada para simular su propia organización a fin de enviar notificaciones internas por correo electrónico.
    
Los dominios externos suelen enviar correo electrónico falso y muchos de estos motivos son legítimos. Por ejemplo, estos son algunos casos legítimos en los que los remitentes externos envían correo electrónico falso:
  
- El remitente está en una lista de correo de discusión y la lista de distribución de correo retransmite el correo electrónico del remitente original a todos los participantes de la lista de distribución de correo.
    
- Una compañía externa está enviando correo electrónico en nombre de otra empresa (por ejemplo, un informe automatizado o una compañía de software como servicio).
    
Necesita una forma de asegurarse de que el correo enviado por los suplantadores de identidad legítima no se quede atrapado en los filtros de correo no deseado en Office 365 o en los sistemas de correo electrónico externos. Normalmente, Office 365 trata estos mensajes de correo electrónico como correo no deseado. Como administrador de Office 365, tiene la posibilidad de evitar esto configurando filtros falsos en el centro de &amp; seguridad y cumplimiento. Si es el propietario del dominio, puede configurar SPF, DKIM y DMARC para permitir estos remitentes.
  
Por otra parte, los usuarios malintencionados malintencionados, los remitentes que están suplantando su dominio o dominios externos para enviar correo no deseado o de suplantación de identidad (phishing), deben estar bloqueados. La suPlantación de identidad también es una forma común para que los phish obtengan las credenciales del usuario. Office 365 tiene una protección de suplantación integrada para ayudar a proteger a su organización de los remitentes de estos correos electrónicos malintencionados. La protección contra la suPlantación de identidad de los dominios de su organización siempre está activada para todos los clientes de Office 365 y la protección de suplantación de dominio externa está activada de forma predeterminada para los clientes de la protección contra amenazas avanzada y los clientes de EOP de octubre de 2018 también. Para reforzar aún más esta protección, díganos qué remitentes están autorizados a suplantar los dominios de su organización y enviar correo electrónico en su nombre, y si se permite que los dominios externos suplante. Los mensajes de correo electrónico enviados por un remitente que no autorice se tratarán como correo no deseado o suplantación de identidad en Office 365. No deje de mirar a los remitentes que falsifican su dominio y nos ayudan a mejorar la inteligencia &amp; de la identidad mediante el centro de seguridad y cumplimiento.
  
## <a name="managing-spoof-intelligence-in-the-security-amp-compliance-center"></a>Administración de inteligencia de identidad en &amp; el centro de seguridad y cumplimiento
<a name="Managespooflist"> </a>

La Directiva de inteligencia de suplantación que configure siempre se aplica a Office 365. No puede deshabilitarla, pero puede elegir cuánto desea administrarla activamente.
  
Puede revisar los remitentes que están suplantando su dominio o dominios externos y, a continuación, decidir si debe permitirse a cada remitente mediante el centro de seguridad &amp; y cumplimiento. Para cada cuenta de usuario suplantada que un remitente suplante de su dominio o de un dominio externo, puede ver la información de la tabla siguiente.
  
|**Parámetro**|**Descripción**|
|:-----|:-----|
|Sender  <br/> |También se denomina remitente real. Suele ser el dominio desde el que se origina el correo electrónico de suplantación de identidad. Office 365 determina el dominio del registro DNS de puntero (PTR) de la dirección IP de envío que está suplantando la identidad de su organización. Si no se encuentra ningún dominio, el informe muestra la dirección IP del remitente en su lugar.  <br/> |
|Usuario suPlantado  <br/> |La cuenta de usuario que el remitente suplantará.  <br/> Solo pestaña **interna** . Este campo contiene una sola dirección de correo electrónico o, si el remitente imita varias cuentas de usuario, contiene **más de una**.<br/> Sólo la pestaña **externa** . Los dominios externos solo contienen un dominio de envío y no contienen una dirección de correo electrónico completa.<br/> **Sugerencia! Para administradores avanzados.** El usuario suplantado es la dirección de (5322. from), que también es la dirección que se muestra como dirección from por el cliente de correo. A veces, se denomina la dirección header. from. SPF no comprueba la validez de esta dirección.           |
|Número de mensajes  <br/> |El número de mensajes de correo enviados por el remitente a su organización en nombre del remitente o los remitentes suplantados que se han identificado en los últimos 30 días.  <br/> |
|Número de quejas del usuario  <br/> |Quejas enviadas por los usuarios contra este remitente por parte de los usuarios en los últimos 30 días. Las quejas suelen estar en forma de envíos de correo no deseado a Microsoft.  <br/> |
|Resultado de autenticación  <br/> |Este valor se **pasa** si el remitente ha superado las comprobaciones de autenticación del remitente de Exchange Online Protection (EOP), como SPF o DKIM, **produjo un error** si el remitente no supera las **** comprobaciones de autenticación de remitentes de EOP, o se desconoce si el resultado de estas comprobaciones no es válida.  <br/> |
|Decisión establecida por  <br/> |Muestra si el administrador de Office 365 o la Directiva de inteligencia de suplantación determina si el remitente puede o no suplantar al usuario.  <br/> |
|Último visto  <br/> |La última fecha en la que este remitente recibió un mensaje en nombre de este usuario suplantado.  <br/> |
|¿Se permite la suplantación?  <br/> | Muestra si el remitente tiene permiso para enviar correo electrónico en nombre del usuario suplantado. Los valores posibles son:<br/> **Sí** Se permitirá que todas las direcciones falsas de este remitente de suplantación de identidad suplante a su organización.  <br/> **No** No se permitirá que las direcciones falsas de este remitente de suplantación de identidad suplante a su organización. En su lugar, los mensajes de este remitente se marcarán como correo no deseado en Office 365.<br/> **Algunos usuarios** Si un remitente suplanta a varios usuarios, algunas direcciones falsas de este remitente podrán suplantar a su organización, el resto se marcará como correo no deseado. Use la pestaña **detalles** para ver las direcciones específicas.<br/> |
|Tipo de imitación  <br/> |Este valor es **interno** si el dominio es uno de los dominios que se han aprovisionado de la organización; en caso contrario, el valor es **externo**.  <br/> |
   
 **Para administrar los remitentes que están suplantando su dominio mediante el &amp; centro de seguridad y cumplimiento**
  
1. Vaya al [centro de &amp; seguridad y cumplimiento](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa. La cuenta debe tener credenciales de administrador en la organización de Office 365.
    
3. En el centro &amp; de seguridad y cumplimiento, expanda **protección contra correo no deseado**de la **Directiva** \> de **Administración** \> de amenazas.  
  
    ![Captura de pantalla que muestra el acceso a la página contra correo electrónico no deseado](media/0a098e68-5ecf-40d7-984f-d15fcc1f958d.jpg)
  
4. En la página **configuración de correo no deseado** del panel derecho, seleccione la pestaña **personalizado** y, a continuación, desplácese hacia abajo y expanda la **Directiva inteligencia empresarial**de suplantación de identidad.  
  
    ![Captura de pantalla que muestra el acceso a la configuración personalizada de bloqueo de correo no deseado](media/a5112100-0b37-460f-932d-5b2f98157871.jpg)
  
5. Para ver la lista de remitentes que suplantan la identidad del dominio, elija **revisar nuevos remitentes** y seleccione la pestaña **dominios** . 
    
    Si ya ha revisado los remitentes y desea cambiar algunas de las opciones anteriores, puede elegir **Mostrar los remitentes que ya he revisado** en su lugar. En cualquier caso, aparece el siguiente panel.  
  
    ![Captura de pantalla que muestra el acceso a la pestaña remitentes falseados](media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)
  
    Cada usuario imitado se muestra en una fila separada para que pueda elegir si desea permitir o bloquear al remitente la falsificación individual de cada usuario.  
  
    Para agregar un remitente a la lista de permitidos de un usuario, seleccione **sí** en la columna **está permitido para** la suplantación. Para agregar un remitente a la lista de bloqueados para un usuario, elija **no**.
     
    Para establecer la Directiva para los dominios que no son de su propiedad, seleccione la ficha **dominios externos** . cambie el remitente a **sí** en la columna **permitido para** suplantación para permitir que el remitente envíe correo electrónico no autenticado a su organización. Como alternativa, si piensa que Office 365 ha cometido un error al permitir que el remitente envíe correo electrónico falsificado, cambie la columna **permitido a** suplantar a **no**.  
  
    ![Captura de pantalla que muestra si se permite que un remitente suplante](media/5dbef9cf-103f-49cd-9638-4b0083d6baa7.jpg)
  
6. Elija **Guardar** para guardar los cambios. 

Si tiene una suscripción a Office 365 Enterprise E5 o ha comprado por separado la protección contra amenazas avanzada como complemento, también puede administrar a los remitentes que están suplantando su dominio a través de la [información de inteligencia de inteligencia](https://docs.microsoft.com/en-us/office365/securitycompliance/walkthrough-spoof-intelligence-insight)de suplantación.
    
## <a name="configuring-the-anti-spoofing-policy"></a>Configuración de la Directiva contra la suplantación de identidad
<a name="Managespooflist"> </a>

Además de permitir o bloquear a un remitente en particular el envío de correo electrónico falsificado a su organización, también puede configurar el grado de restricción que debe tener el filtro y la acción que se debe realizar cuando se encuentra un mensaje de suplantación de identidad.
  
La protección contra la suplantación de identidad se aplica al correo electrónico desde remitentes de dominios externos a la organización de Office 365. Puede aplicar la Directiva a los destinatarios cuyos buzones de correo tienen una licencia de Office 365 Enterprise E5, la protección contra amenazas avanzada y los clientes de EOP de octubre de 2018 también. La Directiva contra la suplantación de identidad se administra junto con el resto de la configuración de antiphishing. Para obtener más información acerca de la configuración de la suplantación de identidad (phishing), consulte [Set Up The Office 365 anti-phishing Policies](https://support.office.com/article/set-up-office-365-atp-anti-phishing-policies-5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578?ui=en-US&amp;rs=en-US&amp;ad=US#phishpolicyoptions).
  
Office 365 incluye protección predeterminada contra la suplantación de identidad que siempre se está ejecutando. Esta protección predeterminada no está visible en el centro &amp; de seguridad y cumplimiento o se puede recuperar a través de los cmdlets de Windows PowerShell. No puede modificar la protección predeterminada contra la suplantación de identidad. En su lugar, puede configurar el grado en que Office 365 exige la protección contra la suplantación de identidad (antiphishing) en cada Directiva contra la suplantación de identidad (phishing) que cree. 
  
Aunque la Directiva contra la suplantación de identidad aparece bajo la Directiva antiphishing en el &amp; centro de seguridad y cumplimiento, no hereda el comportamiento predeterminado de la configuración de suplantación de identidad (phishing) existente en la configuración contra correo no deseado. Si tiene una configuración bajo contra la suplantación de **identidad (phishing)** **contra el correo no deseado** \> que desea replicar para la suplantación de identidad (phishing), tendrá que crear una directiva antiphishing y, a continuación, editar la parte falsa de la Directiva contra la suplantación de identidad (phishing) para reflejar la configuración falsa se describe en la siguiente sección, en lugar de aceptar la configuración predeterminada que se ejecuta en segundo plano. 
  
 **Para configurar la protección contra la suplantación de identidad en una directiva antiphishing mediante &amp; el centro de seguridad y cumplimiento**
  
1. Vaya al [centro de &amp; seguridad y cumplimiento](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa. La cuenta debe tener credenciales de administrador en la organización de Office 365.
    
3. En el centro &amp; de seguridad y cumplimiento, expanda **Threat Management** \> **Policy** \> **anti-phishing**. 
    
4. En la página contra la suplantación de **identidad** del panel derecho, seleccione la Directiva contra la suplantación de identidad (phishing) que desea configurar. 
    
5. En la fila imitada de la página **** que aparece, elija **Editar**. 
    
6. A continuación, configure las acciones que se deben realizar cuando se detecta un mensaje como una suplantación de identidad entre dominios. El comportamiento predeterminado es mover el mensaje a la carpeta de correo no deseado del destinatario. La otra opción es enviar el mensaje a la cuarentena. Para obtener más información acerca de la administración de mensajes enviados a la cuarentena, vea [cuarentena de mensajes de correo electrónico en Office 365](quarantine-email-messages.md).  
  
    ![Captura de pantalla que muestra las opciones de edición de directivas antifalsificación](media/7a868dff-2c4b-46b9-88ca-f2d523ca2307.jpg)
  
7. Realice su elección y, a continuación, elija **Guardar**. 
    
## <a name="other-ways-to-manage-spoofing-and-phishing-with-office-365"></a>Otras formas de administrar la suplantación de identidad y la suplantación de identidad con Office 365
<a name="Managespooflist"> </a>

Sea Diligent sobre la suplantación de identidad y la protección contra phishing. A continuación, se incluyen formas relacionadas de comprobar si los remitentes suplantan el dominio y ayudar a evitar que dañen la organización:
  
- Compruebe el informe de correo falsificado de Exchange Online Protection como parte de la rutina. Puede usar este informe con frecuencia para ver y ayudar a administrar los remitentes suplantados. Para obtener más información, vea **Informe de correo falsificado** en [use Mail Protection Reports in Office 365 para ver datos sobre malware, correo no deseado y detecciones de reglas](https://technet.microsoft.com/library/dn500744%28v=exchg.150%29.aspx).
    
Para administradores más avanzados de Office 365, también puede completar estas comprobaciones:
    
    
- Revise la configuración del marco de directivas de remitente (SPF). Para obtener una introducción rápida a SPF y configurarlo rápidamente, consulte [configurar SPF en Office 365 para ayudar a evitar la suplantación de identidad](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx). Para obtener una descripción más detallada de cómo Office 365 usa SPF o para la solución de problemas o implementaciones no estándar, como las implementaciones híbridas, empiece con [la forma en que Office 365 usa el marco de directivas de remitente (SPF) para evitar la](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx)suplantación de identidad.
    
- Revise la configuración de DomainKeys Identified Mail (DKIM). Debe usar DKIM además de SPF y DMARC para ayudar a evitar que los usuarios malintencionados envíen mensajes que parezcan que provienen de su dominio. DKIM le permite agregar una firma digital a los mensajes de correo electrónico en el encabezado del mensaje. Para obtener más información, vea [usar DKIM para validar el correo electrónico saliente enviado desde su dominio en Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx).
    
- Revise la configuración de autenticación de mensajes basada en el dominio, informes y conformidad (DMARC). La implementación de DMARC con SPF y DKIM proporciona protección adicional contra el correo electrónico de suplantación de identidad (phishing). DMARC ayuda a recibir sistemas de correo que determinen qué hacer con los mensajes enviados desde su dominio que no superen las comprobaciones de SPF o DKIM. Para obtener más información, vea [usar DMARC para validar el correo electrónico en Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).
    
- Use el cmdlet [Get-PhishFilterPolicy](https://technet.microsoft.com/en-us/library/mt735158%28v=exchg.160%29.aspx) de Windows PowerShell para recopilar datos detallados de los remitentes suplantados, generar listas de permitidos y bloqueados y determinar cómo generar registros DNS más completos, DKIM y DMARC sin tener su el correo electrónico legítimo se detecta en los filtros de correo no deseado externos. Para obtener más información, vea [Cómo funciona la protección contra la suplantación de identidad en Office 365](https://blogs.msdn.microsoft.com/tzink/2016/02/23/how-antispoofing-protection-works-in-office-365/).
    


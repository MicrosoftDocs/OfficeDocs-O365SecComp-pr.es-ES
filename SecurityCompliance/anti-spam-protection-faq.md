---
title: Preguntas más frecuentes sobre protección contra correo electrónico no deseado
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
description: En este tema encontrará las preguntas frecuentes y sus correspondientes respuestas sobre la protección contra el correo no deseado. Las respuestas sirven para los clientes de Microsoft Exchange Online y de Exchange Online Protection (EOP).
ms.openlocfilehash: 47ab5202e4f20bbb8cdcf1d83987b0c0c20e8f29
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341681"
---
# <a name="anti-spam-protection-faq"></a>Preguntas más frecuentes sobre protección contra correo electrónico no deseado

En este tema encontrará las preguntas frecuentes y sus correspondientes respuestas sobre la protección contra el correo no deseado. Las respuestas sirven para los clientes de Microsoft Exchange Online y de Exchange Online Protection (EOP). 
  
> [!TIP]
> Para obtener preguntas y respuestas sobre las listas de remitentes seguros y bloqueados, vea [listas de remiteNtes seguros y bloqueados en Exchange Online](safe-sender-and-blocked-sender-lists-faq.md). Para obtener preguntas y respuestas sobre la cuarentena, vea [preguntas más frecuentes](quarantine-faq.md)sobre la cuarentena. 
  
 **P: De manera predeterminada, ¿qué sucede con un mensaje de correo no deseado detectado?**
  
R. **Para mensajes entrantes:** La mayor parte del correo no deseado se elimina mediante el filtrado de conexiones, que se basa en la dirección IP del remitente. A continuación, el servicio inspecciona el contenido del mensaje. El correo no deseado con contenido filtrado se envía de manera predeterminada a la carpeta Correo electrónico no deseado del destinatario. Esta acción se puede cambiar. Por ejemplo, se puede elegir enviar los mensajes de correo no deseado a cuarentena configurando la directiva de filtro de contenido. 
  
> [!IMPORTANT]
> Para clientes independientes de EOP: para asegurarse de que la acción **mover el mensaje a la carpeta de correo electrónico no deseado** funcionará con los buzones locales, debe configurar dos reglas de flujo de correo de Exchange (también conocidas como reglas de transporte) en los servidores locales para detectar encabezados de correo no deseado agregados por EOP. Para obtener más información, consulte [asegurarse de que el correo no deseado se enruta a la carpeta de correo no deseado de cada usuario](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). 
  
 **Para mensajes salientes:** El mensaje se enruta a través del grupo de entrega de mayor riesgo o se devuelve y no se entrega, en cuyo caso el remitente debería recibir un mensaje de notificación de estado de entrega (DSN) indicando que el mensaje no se pudo entregar. 
  
 **P. ¿Qué es una variante de correo no deseado de día cero y cómo la controla el servicio?**
  
A. una variante de correo no deseado de día cero es una primera generación, una variante desconocida anteriormente de correo no deseado que nunca se ha capturado o analizado, por lo que los filtros de contenido de correo no deseado todavía no tienen información disponible para detectarlo. Una vez que nuestros analistas de correo no deseado capturan y analizan un ejemplo de correo no deseado de día cero, si cumplen los criterios de clasificación de correo no deseado, los filtros de contenido de correo no deseado se actualizan para detectarlo y ya no se considera "día cero". ( **Nota:** si recibe un mensaje que puede ser una variante de 0 días de correo no deseado, para ayudarnos a mejorar el servicio, envíe el mensaje a Microsoft mediante uno de los métodos descritos en [enviar mensajes de correo no deseado, no spam y fraude de suplantación de identidad a Microsoft para Análisis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)).
  
 **P: ¿Debo configurar el servicio para obtener protección contra el correo no deseado?**
  
R: Una vez que se suscriba al servicio y agregue su dominio, el filtrado de correo no deseado se habilitará en toda la empresa mediante las directivas contra correo no deseado predeterminadas. Las directivas predeterminadas están ajustadas para protegerle sin necesidad de realizar ninguna configuración adicional (aparte de la excepción mencionada antes para clientes independientes EOP). Como administrador, puede editar las directivas predeterminadas contra correo no deseado para que se adapten mejor a las necesidades de la organización. Para disfrutar de una mayor granularidad, también puede crear directivas personalizadas de filtro de contenido y aplicarlas a usuarios, grupos o dominios específicos de la organización. Las directivas personalizadas siempre tienen prioridad con respecto a la directiva predeterminada, pero puede cambiar la prioridad (es decir, el orden de ejecución) de las directivas personalizadas.
  
Para obtener más información sobre la configuración de directivas contra correo no deseado, consulte los siguientes temas:
  
[Configurar la directiva de filtro de conexión](configure-the-connection-filter-policy.md)
  
[Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md)
  
[Configurar la directiva de correo no deseado saliente](configure-the-outbound-spam-policy.md)
  
 **P. Si realizo cambios en una directiva contra correo no deseado, ¿cuánto tardan en tener efecto después de guardarlos?**
  
A. Los cambios pueden tardar hasta una hora en surtir efecto.
  
 **P: ¿El filtrado de correo electrónico masivo está habilitado automáticamente?**
  
R: La opción avanzada de filtrado de correo no deseado **Correo masivo** está habilitada de forma predeterminada para los clientes nuevos. En el caso de los clientes migrados, esta opción se atendrá a la configuración de FOPE establecida. Para obtener más información acerca del correo electrónico masivo, consulte [¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?](what-s-the-difference-between-junk-email-and-bulk-email.md).
  
 **P. ¿El servicio proporciona filtrado de direcciones URL?**
  
R. Si, el servicio tiene un filtro de direcciones URL que comprueba las direcciones URL dentro de los mensajes. Si se detectan direcciones URL asociadas a correo no deseado o a contenido malintencionado conocido, el mensaje se marcará como correo no deseado.
  
 **P: ¿Cómo pueden hacer los clientes del servicio para enviar mensajes falsos negativos (correo no deseado) y falsos positivos (correo deseado) a Microsoft?**
  
Los mensajes de correo no deseado y los que no son de correo no deseado pueden enviarse a Microsoft para su análisis de varias formas. Para obtener más información, vea enviar correo electrónico no deseado, mensajes de correo [no deseado y mensajes de estafa de suplantación de identidad a Microsoft para su análisis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). 
  
 **P: ¿Puedo obtener informes de correo no deseado?**
  
R. Sí, por ejemplo puede obtener un informe de detección de correo no deseado en el centro de administración de Office 365. Este informe muestra el volumen de correo no deseado como un recuento de mensajes únicos. Para obtener más información sobre los informes, consulte los siguientes vínculos:
  
Clientes de Exchange Online: [supervisión, informes y seguimiento de mensajes en Exchange Online](http://technet.microsoft.com/library/87bdeeae-bd80-4a3b-95c5-62fbaf97c2e8.aspx)
  
Clientes de Exchange Online Protection: [informes y seguimiento de mensajes en Exchange Online Protection](eop/reporting-and-message-trace-in-exchange-online-protection.md)
  
 **P: Alguien me envió un mensaje y no lo encuentro. Sospecho que se pudo haber detectado como correo no deseado. ¿Existe alguna herramienta que pueda utilizar para averiguarlo?**
  
R: Sí, la herramienta de seguimiento de mensajes le permite realizar un seguimiento de los mensajes de correo electrónico a medida que pasan por el servicio a fin de averiguar qué sucedió con ellos. Consulte [¿Se marcó un mensaje como correo no deseado?](http://technet.microsoft.com/library/aa49e3f9-a5b1-4410-aac2-ddbbf3f5bfb2.aspx#BKMB_Whywasamessagemarkedasspam) para obtener más información acerca de cómo utilizar la herramienta de seguimiento de mensajes para averiguar por qué se marcó un mensaje como correo no deseado.
  
 **P: ¿El servicio limitará (límite de tasa) mi correo si mis usuarios envían correo no deseado?**
  
A. Si Office 365 determina que más de la mitad del correo que se envía de un usuario a través del servicio en un período de tiempo determinado (por ejemplo, por hora) es correo no deseado, se bloqueará el usuario y no podrá enviar mensajes. En la mayoría de los casos, si se determina que un mensaje saliente es correo no deseado, se redirige a través del grupo de entrega de alto riesgo, lo cual reduce la probabilidad de que el grupo de IP saliente normal se agregue a una lista de bloqueados.
  
Puede enviar una notificación a la dirección de correo electrónico especificada cuando se bloquee un remitente por enviar correo electrónico no deseado. Para más información sobre esta configuración, consulte [Configurar la directiva de correo no deseado saliente](configure-the-outbound-spam-policy.md).
  
 **P. ¿Puedo usar un proveedor contra correo no deseado y contra malware de terceros junto con Exchange Online?**
  
R. Sí, puede configurar otro servicio de filtrado de correo no deseado y malware para proteger sus buzones de Exchange Online. Para hacerlo en su correo entrante, debe redirigir sus mensajes de correo electrónico al proveedor de terceros cambiando sus registros MX para que apunten al proveedor de terceros y, a continuación, redirigir los mensajes a EOP para el procesamiento adicional. Para hacerlo en su correo saliente, configure el destino de entrega del mensaje al proveedor de terceros (host inteligente), tal y como se muestra en [Scenario: Outbound Smart Hosting](http://technet.microsoft.com/library/431b3f02-4efd-4bd3-94e7-eecd03f8ef5e.aspx).
  
 **P.: ¿Microsoft tiene documentación sobre cómo protegerse de las estafas de suplantación de identidad (phishing)?**
  
R. Sí, consulte los siguientes artículos:
  
[Obtener ayuda relacionada con las estafas de suplantación de identidad (phishing), las estafas de loterías y otros tipos de estafas](http://go.microsoft.com/fwlink/p/?LinkId=325606)
  
[Estafas a través de correos electrónicos y sitios web: cómo protegerse](http://go.microsoft.com/fwlink/p/?LinkID=325607)
  
 **P. ¿Se investigan los mensajes de malware o correo no deseado en cuanto a quién los envió o se transfieren a las autoridades judiciales?**
  
R. El servicio se enfoca en la detección y eliminación de malware y correo no deseado, aunque de vez en cuando podemos investigar campañas de ataques o correo no deseado particularmente peligroso, y perseguir a sus autores. Esto puede implicar trabajar con nuestras unidades especializadas en crimen digital y legal para desmantelar la botnet de un spammer, impidiendo que el spammer use el servicio (si lo está usando para enviar correo electrónico saliente) y transmitiendo la información a las autoridades judiciales para que lleven a cabo una acusación penal.
  
 **P. ¿Qué conjunto de procedimientos recomendados para el correo saliente garantizará la entrega de mi correo?**
  
A. Las pautas presentadas a continuación son los procedimientos recomendados para el envío de mensajes de correo electrónico salientes.
  
1. **El dominio de envío del correo electrónico debe resolverse en DNS.**
    
    Por ejemplo, si el remitente es user@example.com, el dominio example.com se resuelve en la dirección IP 192.0.43.10. Si un dominio remitente no tiene registro A y no MX en DNS, el servicio enrutará el mensaje a través de su grupo de entrega de mayor riesgo independientemente de si el contenido del mensaje es o no correo no deseado. Para obtener más información acerca del grupo de entrega de mayor riesgo, consulte [grupo de entrega de alto riesgo para los mensajes salientes](high-risk-delivery-pool-for-outbound-messages.md). 
    
2. **La dirección IP de envío del servidor de correo saliente debe tener una entrada DNS (PTR) reversa.**
    
    Por ejemplo, si se envía desde la dirección IP 192.0.43.10, la entrada de DNS inverso para esta IP es 43-10.any.icann.org. 
    
3. **Los comandos HELO/EHLO y MAIL FROM deben ser coherentes y estar presentes en la forma de un nombre de dominio, en vez de una dirección IP.**
    
    El comando HELO/EHLO debe configurarse para coincidir con el DNS inverso de la dirección IP de envío, de modo que el dominio continúe siendo el mismo en varias partes de los encabezados del mensaje.
    
4. **Asegúrese de que los registros de SPF apropiados estén configurados en DNS.**
    
    Los registros de SPF son un mecanismo para validar que el correo enviado desde un dominio realmente proviene de ese domino y no es una suplantación. Para obtener más información acerca de los registros de SPF, consulte los siguientes vínculos:
    
    [Configurar SPF en Office 365 para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md)
    
    [Crear registros DNS para Office 365](https://go.microsoft.com/fwlink/?LinkID=275414)
    
5. **Firma de correo electrónico con DKIM, firma con la resolución de nombres canónicos relajada.**
    
    Si un remitente desea firmar sus mensajes con un Correo identificado con claves de dominio (DKIM) y desea enviar correo saliente mediante el servicio, para firmar debe utilizar el algoritmo de resolución de nombres canónicos relajada del encabezado. Firmar con una resolución de nombres canónicos del encabezado estricta puede invalidar la firma cuando pase por el servicio.
    
6. **Los propietarios de dominio deben disponer de información precisa en la base de datos WHOIS.**
    
    Esto identifica a los propietarios del dominio y la forma de ponerse en contacto con ellos mediante la especificación de una empresa principal estable, un punto de contacto y servidores de nombre.
    
7. **Para el envío masivo de correo, el nombre De: debe reflejar quién envía el mensaje, mientras que la línea de asunto del mensaje debe ser un resumen del tema del mensaje.**
    
    El cuerpo del mensaje debe tener un indicación clara de la oferta, el servicio o el producto. Por ejemplo, si el remitente envía correo masivamente para la empresa Contoso, los campos De y Asunto del correo electrónico deberían ser parecidos a lo siguiente:
    
    De: marketing@contoso.com
    
    Asunto: ¡Nuevo catálogo actualizado para la temporada de Navidad! 
    
    A continuación, se muestra un ejemplo de qué no se debe hacer porque no es descriptivo:
    
    De: user@hotmail.com
    
    Asunto: Catálogos
    
8. **Si se envía correo masivo a muchos destinatarios y el mensaje tiene formato de boletín, debe haber una manera de cancelar la suscripción en la parte inferior del mensaje.**
    
    La opción de cancelar la suscripción debe parecerse a:
    
    sender@fabrikam.com envió este mensaje a example@contoso.com. Actualizar perfil/Correo electrónico | Eliminación instantánea con **SafeUnsubscribe** | Directiva de privacidad
    
9. **Si envía correo masivamente, la adquisición de listas debe realizarse con una suscripción doble. Si envía correo masivamente, la suscripción doble es un procedimiento recomendado.**
    
    La suscripción doble es una práctica consistente en solicitar a un usuario que realice dos acciones para suscribirse a un correo de marketing:
    
1. Una vez, cuando el usuario hace clic en una casilla sin activar previamente para elegir recibir más ofertas o mensajes de correo electrónico del especialista en marketing.
    
2. La segunda, cuando el especialista en marketing envíe un correo electrónico de confirmación a la dirección de correo proporcionada por el usuario donde le solicite que haga clic en un vínculo sujeto a limitación temporal que completará al confirmación.
    
    El uso de la suscripción doble construye una buena reputación para las personas que envían correo electrónico masivo.
    
10. **Las personas que envían correo electrónico masivo deben crear contenido transparente del cual puedan hacerse responsables:**
    
1. El vocabulario que requiera que los destinatarios agreguen a los remitentes a la libreta de direcciones debe especificar claramente que dicha acción no es una garantía de entrega.
    
2. Cuando el cuerpo del mensaje incluya contenido que redirija, utilice un estilo coherente para los vínculos.
    
3. No envíe imágenes o datos adjuntos pesados o mensajes que estén únicamente compuestos por una imagen.
    
4. Cuando utilice píxeles de seguimiento (errores o señalizaciones web), especifique claramente su presencia en su directiva de privacidad o configuración de P3P.
    
11. **Dé formato a las notificaciones de estado de entrega.**
    
    Al generar mensajes de notificación del estado de entrega, los remitentes deben respetar el formato de un rebote, como se especifica en [RFC 3464](https://go.microsoft.com/fwlink/?LinkId=279715).
    
12. **Elimine las direcciones de correo electrónico rebotadas de los usuarios inexistentes.**
    
    Si recibe un informe de no entrega que le indica que una dirección de correo electrónico ya no se utiliza, elimine el alias de correo no existente de su lista. Las direcciones de correo electrónico cambian con el tiempo, y la gente a veces deja de utilizarlas.
    
13. **Utilice el programa de Servicios de datos de red inteligente (SNDS) de Hotmail.**
    
    Hotmail utiliza un programa denominado Servicios de datos de red inteligente que permite a los remitentes comprobar los reclamos enviados por los usuarios finales. SNDS es el portal principal para solucionar problemas de entrega a Hotmail.
    
## <a name="for-more-information"></a>Más información

[Protección contra correo no deseado de Office 365](https://support.office.com/article/6a601501-a6a8-4559-b2e7-56b59c96a586)
  
[Listas de remitentes seguros y bloqueados en Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)
  
[Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md)
  
[Mensajes de reenvío masivo de correo electrónico y EOP](backscatter-messages-and-eop.md)
  


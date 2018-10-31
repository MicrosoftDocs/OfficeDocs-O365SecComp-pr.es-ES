---
title: Cifrado de correo electrónico en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
description: Comparación de las opciones de cifrado en Office 365, incluido el cifrado de mensajes de Office (OME), S/MIME, Information Rights Management (IRM) y obtenga información acerca de la seguridad de capa de transporte (TLS).
ms.openlocfilehash: c9c83283cab09ac81ab2856aec53fe8682ec45b8
ms.sourcegitcommit: c05076501dfe118e575998ecfc08ad69d13c8abc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "25853085"
---
# <a name="email-encryption-in-office-365"></a>Cifrado de correo electrónico en Office 365

En este artículo se compara las opciones de cifrado en Office 365, incluido el cifrado de mensajes de Office (OME), S/MIME, Information Rights Management (IRM) y presenta la seguridad de capa de transporte (TLS).
  
Office 365 ofrece varias opciones de cifrado para ayudar a satisfacer sus necesidades empresariales para seguridad de correo electrónico. Este artículo presenta tres maneras para cifrar el correo electrónico en Office 365. Si desea obtener más información acerca de todas las características de seguridad en Office 365, visite el [Centro de confianza de Office 365](http://go.microsoft.com/fwlink/p/?LinkID=282470). Este artículo presenta a los tres tipos de cifrado disponible para los administradores de Office 365 ayudar a proteger el correo electrónico en Office 365:
  
- Cifrado de mensajes de Office (OME).
    
- Extensiones seguras multipropósito al correo de Internet (S/MIME).
    
- Information Rights Management (IRM).
    
## <a name="what-is-email-encryption-and-how-does-office-365-use-it"></a>¿Qué es el cifrado de correo electrónico y cómo lo usa Office 365?

El cifrado es el proceso mediante el cual se codifica la información para que solo un destinatario autorizado pueda descodificar y consumir la información. Office 365 usa el cifrado de dos maneras: en el servicio y, como un control de cliente. En el servicio, se usa el cifrado en Office 365 de forma predeterminada; no es necesario configurar nada. Por ejemplo, Office 365 utiliza seguridad de capa de transporte (TLS) para cifrar la conexión o sesión entre dos servidores. 
  
Así es cómo funciona normalmente cifrado de correo electrónico:
  
- Un mensaje se cifran o transforma de texto sin formato en texto de cifrado que debe recibirlo, ya sea en el equipo de la dirección del remitente, o por un servidor central mientras el mensaje está en tránsito.
    
- El mensaje permanece en el texto cifrado mientras está en tránsito con el fin de impedir que se leen en caso de que el mensaje se intercepta.
    
- Una vez que el destinatario recibe el mensaje, el mensaje se vuelve a transformar en texto sin formato legible de dos maneras:
    
  - Máquina del destinatario utiliza una clave para descifrar el mensaje, o
    
  - Un servidor central descifra el mensaje en nombre del destinatario, después de validar la identidad del destinatario.
    
Para obtener más información sobre cómo Office 365 protege la comunicación entre servidores, por ejemplo, entre las organizaciones dentro de Office 365 o entre Office 365 y los socios comerciales de confianza fuera de Office 365, vea [cómo Exchange Online utiliza TLS para el correo electrónico seguro conexiones en Office 365](exchange-online-uses-tls-to-secure-email-connections.md).
  
Vea este vídeo para obtener una introducción al [cifrado en Office 365](https://www.youtube.com/watch?v=KmfxCd5ublI).
  
## <a name="comparing-email-encryption-options-available-in-office-365"></a>Comparar las opciones de cifrado de correo electrónico disponibles en Office 365

||        ![Ilustración conceptual que describe OME](media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)                 |        ![Ilustración conceptual que describe IRM](media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)                 |        ![Ilustración conceptual que describe SMIME](media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)                |
|:-----|:-----|:-----|:-----|
|¿Qué es?  <br/> |El cifrado de mensajes de Office 365 (OME) es un servicio basado en Azure Rights Management (Azure RMS) que permite enviar correo electrónico cifrado a otras personas dentro o fuera de la organización, independientemente de la dirección de correo electrónico de destino (Gmail, Yahoo! Mail, Outlook.com, etc.).  <br/> Como administrador, puede configurar reglas de transporte que definen las condiciones para el cifrado. Cuando un usuario envía un mensaje que coincide con una regla, se aplica automáticamente el cifrado.  <br/> Para ver los mensajes cifrados, los destinatarios pueden obtener un código de acceso única, el inicio de sesión con una cuenta de Microsoft o el inicio de sesión con un trabajo o escuela cuenta asociada con Office 365. Los destinatarios también pueden enviar respuestas cifradas. No necesitan una suscripción a Office 365 para ver los mensajes cifrados o enviar respuestas cifradas.  <br/> |IRM es una solución de cifrado que también se aplica a las restricciones de uso para los mensajes de correo electrónico. Ayuda a evitar que personas no autorizadas impriman, reenvíen o copien información confidencial.  <br/> Las capacidades IRM en Office 365 usan Azure Rights Management (Azure RMS). 
  <br/> |S/MIME es una solución basada en el certificado de cifrado que permite cifrar y firmar digitalmente un mensaje. El cifrado de mensajes ayuda a garantizar que sólo el destinatario puede abrir y leer el mensaje. Una firma digital ayuda al destinatario a validar la identidad del remitente.  <br/> Las firmas digitales y el cifrado de mensajes son posibles gracias al uso exclusivo de certificados digitales que contienen las claves para comprobar las firmas digitales y cifrar o descifrar mensajes.  <br/> Para usar S/MIME, debe tener las claves públicas en el archivo para cada destinatario. Los destinatarios tienen que mantener sus propias claves privadas, que deben permanecer seguros. Si las claves privadas de un destinatario se ve comprometidas, el destinatario debe obtener una nueva clave privada y redistribuya las claves públicas a todos los remitentes posibles.  <br/> |
|¿Qué hace?  <br/> | OME:  <br/>  Cifra los mensajes enviados a destinatarios internos o externos.  <br/>  Permite a los usuarios enviar mensajes cifrados a cualquier dirección de correo electrónico, incluidos Outlook.com, Yahoo! Mail y Gmail.  <br/>  Le permite, como administrador, para personalizar el portal para reflejar la marca de la organización de visualización de correo electrónico.  <br/>  Microsoft forma segura administra y almacena las claves, por lo que no es necesario.  <br/>  No se necesita ningún software de cliente especial siempre y cuando el mensaje cifrado (enviado como datos adjuntos HTML) pueda abrirse en un explorador.  <br/> | IRM:  <br/>  Usa cifrado y restricciones de uso para proporcionar protección en línea y sin conexión para los mensajes de correo electrónico y datos adjuntos.  <br/>  Ofrece, como administrador, la capacidad de configurar reglas de transporte o reglas de protección de Outlook para aplicar automáticamente IRM a mensajes seleccionados.  <br/>  Permite a los usuarios aplicar manualmente las plantillas en Outlook u Outlook Web App.  <br/> |S/MIME aborda la autenticación de remitentes con firmas digitales y la confidencialidad de mensajes con cifrado.  <br/> |
|¿Qué no hace?  <br/> |OME no permite aplicar restricciones de uso para los mensajes. Por ejemplo, no se puede usar para detener a un destinatario de reenvío o imprimir un mensaje cifrado.  <br/> |Puede que algunas aplicaciones no admitan correos electrónicos IRM en todos los dispositivos. Para obtener más información sobre estos y otros productos compatibles con correo electrónico IRM, vea [funciones del dispositivo de cliente](https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities).<br/> |S/MIME no permitir los mensajes cifrados que debe examinarse para malware, correo no deseado o las directivas.  <br/> |
|Recomendaciones y escenarios de ejemplo  <br/> | Se recomienda usar OME cuando desea enviar información comercial confidencial a personas externas a su organización, tanto si están los consumidores u otras organizaciones. Por ejemplo:  <br/>  Un empleado bancario que envía extractos de tarjeta de crédito a los clientes  <br/>  Un consultorio del envío de registros médicos a un paciente  <br/>  Un abogado que envía información legal confidencial a otro abogado  <br/> | Se recomienda usar IRM para aplicar restricciones de uso y también cifrado. Por ejemplo:  <br/>  Un administrador de envío detalles confidenciales a su equipo acerca de un producto nuevo aplica a la opción "No reenviar".  <br/>  Un ejecutivo necesita compartir una propuesta de oferta con otra compañía, que incluye datos adjuntos de un socio que usa Office 365, y requieren que el correo electrónico y los datos adjuntos estén protegidos.  <br/> | Se recomienda usar S/MIME cuando la organización u organización del destinatario requiere un cifrado punto a punto es true.  <br/>  Normalmente se usa S/MIME en los siguientes escenarios:  <br/>  Autoridades gubernamentales que se comunican con otras autoridades gubernamentales  <br/>  Una empresa que se comunica con una autoridad gubernamental  <br/> |
   
## <a name="what-encryption-options-are-available-for-my-office-365-subscription"></a>¿Qué opciones de cifrado están disponibles para mi suscripción de Office 365?

Para obtener información acerca de las opciones de cifrado de correo electrónico para su suscripción de Office 365, vea la [Descripción del servicio de Exchange Online](https://technet.microsoft.com/en-us/library/exchange-online-service-description.aspx). En este caso, puede encontrar información acerca de las siguientes características de cifrado:
  
- Azure RMS, incluidas las capacidades IRM y OME
    
- S/MIME
    
- TLS
    
- Cifrado de datos en reposo (mediante BitLocker)
    
## <a name="what-about-encryption-for-data-at-rest"></a>¿Qué sucede con el cifrado de datos en reposo?

"Datos en reposo" hace referencia a los datos que no está activamente en tránsito. En Office 365, los datos de correo electrónico en reposo se cifran mediante el cifrado de unidad BitLocker. BitLocker cifra los discos duros en centros de datos de Office 365 para proporcionar la mejor protección contra el acceso no autorizado. Para obtener más información, vea [Información general de BitLocker](https://go.microsoft.com/fwlink/p/?LinkId=394737).
  
## <a name="more-information-about-email-encryption-options-in-office-365"></a>Más información sobre opciones de cifrado de correo electrónico en Office 365

Para obtener más información sobre las opciones de cifrado de correo electrónico en este artículo, así como TLS, consulte los siguientes artículos:
  
 **OME**
  
[Cifrado de mensajes de Office 365 (OME)](ome.md)
  
 **IRM**
  
[Information Rights Management en Exchange Online](https://technet.microsoft.com/en-us/library/jj983436%28v=exchg.150%29.aspx)
  
[¿Qué es Azure Rights Management?](https://technet.microsoft.com/library/jj585026)
  
 **S/MIME**
  
[S/MIME para la firma y cifrado de mensajes](https://technet.microsoft.com/library/dn626158)
  
[Descripción de S/MIME](https://technet.microsoft.com/library/aa995740%28v=exchg.65%29.aspx)
  
[Descripción de la criptografía de clave pública](https://technet.microsoft.com/library/aa998077%28v=exchg.65%29.aspx)
  
 **TLS**
  
[Configurar el flujo de correo personalizado mediante el uso de conectores en Office 365](https://technet.microsoft.com/en-us/library/jj723138%28v=exchg.150%29.aspx)
  


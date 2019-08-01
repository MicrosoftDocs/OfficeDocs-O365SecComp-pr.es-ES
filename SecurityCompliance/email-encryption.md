---
title: Cifrado de correo electrónico en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
ms.collection:
- M365-security-compliance
description: Compare las opciones de cifrado en Office 365, incluido el Cifrado de mensajes de Office (OME), S/MIME e Information Rights Management (IRM), y obtenga más información sobre la Seguridad de capa de transporte (TLS).
ms.openlocfilehash: dba0c0d890a7018f9ca5daab2c1e88c4d234c5c3
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854684"
---
# <a name="email-encryption-in-office-365"></a>Cifrado de correo electrónico en Office 365

Este articulo compara las opciones de cifrado en Office 365, incluido el Cifrado de mensajes de Office (OME), S/MIME e Information Rights Management (IRM), y presenta la Seguridad de capa de transporte (TLS).
  
Office 365 le ofrece varias opciones de cifrado para ayudar a satisfacer las necesidades que tiene su empresa sobre la seguridad del correo electrónico. Este artículo contiene tres formas de cifrar el correo electrónico en Office 365. Si quiere obtener más información acerca de todas las características de seguridad en Office 365, visite el [Centro de confianza de Office 365](http://go.microsoft.com/fwlink/p/?LinkID=282470). Este artículo presenta los tres tipos de cifrado disponibles para los administradores de Office 365 con el propósito de ayudar a proteger el correo electrónico en Office 365:
  
- Cifrado de mensajes de Office (OME).
    
- Extensiones seguras multipropósito al correo de Internet (S/MIME).
    
- Information Rights Management (IRM).
    
## <a name="what-is-email-encryption-and-how-does-office-365-use-it"></a>¿Qué es el cifrado de correo electrónico y cómo lo usa Office 365?

El cifrado es el proceso por el que se codifica la información para que solo un destinatario autorizado pueda descodificar y consumir la información. Office 365 usa el cifrado de dos maneras: en el servicio y como control de un cliente. En el servicio, el cifrado se usa de manera predeterminada en Office 365. no es necesario configurar nada. Por ejemplo, Office 365 usa Seguridad de capa de transporte (TLS) para cifrar la conexión, o sesión, entre dos servidores. 
  
Así es cómo funciona normalmente el cifrado de correo electrónico:
  
- Un mensaje está cifrado, o se transforma de texto sin formato en texto cifrado ilegible, ya sea en el equipo del remitente, o mediante un servidor central mientras el mensaje está en tránsito.
    
- El mensaje permanece como texto cifrado mientras está en tránsito para protegerlo y que no sea leído en caso de que se intercepte.
    
- Cuando el destinatario recibe el mensaje, este se transforma nuevamente en texto sin formato legible de una de estas dos maneras:
    
  - El equipo del destinatario usa una clave para descifrar el mensaje, o
    
  - Un servidor central descifra el mensaje en nombre del destinatario, después de validar la identidad del destinatario.
    
Para obtener más información sobre cómo Office 365 protege la comunicación entre servidores, entre organizaciones dentro de Office 365 o entre Office 365 y un socio comercial de confianza fuera de Office 365, puede consultar [Cómo Exchange Online usa TLS para proteger las conexiones de correo electrónico en Office 365](exchange-online-uses-tls-to-secure-email-connections.md).
  
Vea este vídeo para una introducción [al cifrado en Office 365](https://www.youtube.com/watch?v=KmfxCd5ublI).
  
## <a name="comparing-email-encryption-options-available-in-office-365"></a>Comparación de las opciones de cifrado de correo electrónico disponibles en Office 365 

||![Ilustración conceptual que describe OME](media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)|![Ilustración conceptual que describe IRM](media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)|![Ilustración conceptual que describe SMIME](media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)|
|:-----|:-----|:-----|:-----|
|¿Qué es?|El cifrado de mensajes de Office 365 (OME) es un servicio basado en Azure Rights Management (Azure RMS) que permite enviar correo electrónico cifrado a otras personas dentro o fuera de la organización, independientemente de la dirección de correo electrónico de destino (Gmail, Yahoo! Mail, Outlook.com, etc.).  <br/> Como administrador, puede configurar reglas de transporte que definen las condiciones para el cifrado. Cuando un usuario envía un mensaje que coincide con una regla, se aplica automáticamente el cifrado.  <br/> Para ver los mensajes cifrados, los destinatarios pueden obtener un código de acceso único, iniciar sesión con una cuenta de Microsoft, o iniciar sesión con una cuenta profesional o educativa asociada a Office 365. Los destinatarios también pueden enviar respuestas cifradas. No necesitan una suscripción de Office 365 para ver los mensajes cifrados o enviar respuestas cifradas.|IRM es una solución de cifrado que también se aplica a las restricciones de uso para los mensajes de correo electrónico. Ayuda a evitar que personas no autorizadas impriman, reenvíen o copien información confidencial.  <br/> Las capacidades IRM en Office 365 usan Azure Rights Management (Azure RMS).|S/MIME es una solución de cifrado basada en certificados que permite cifrar y firmar digitalmente un mensaje. El cifrado de mensajes ayuda a garantizar que solo el destinatario pueda abrir y leer el mensaje. Una firma digital ayuda a que el destinatario valide la identidad del remitente.  <br/> Las firmas digitales y el cifrado de mensajes son posibles gracias al uso exclusivo de certificados digitales que contienen las claves para comprobar las firmas digitales y cifrar o descifrar mensajes.  <br/> Para usar S/MIME, debe tener las claves públicas en el archivo para cada destinatario. Los destinatarios deben conservar sus propias claves privadas, que deben permanecer protegidas. Si se ponen en peligro las claves privadas de un destinatario, el destinatario debe obtener una nueva clave privada y redistribuir las claves públicas a todos los remitentes potenciales.|
|¿Qué hace?|OME:  <br/>  Cifra los mensajes enviados a destinatarios internos o externos.  <br/>  Permite a los usuarios enviar mensajes cifrados a cualquier dirección de correo electrónico, incluidos Outlook.com, Yahoo! Mail y Gmail.  <br/>  Le permite, como administrador, personalizar el portal de visualización de correo electrónico para reflejar la marca de su organización.  <br/>  Microsoft administra y almacena de forma segura las claves, por lo que no es necesario que usted lo haga.  <br/>  No se necesita ningún software de cliente especial siempre y cuando el mensaje cifrado (enviado como datos adjuntos HTML) pueda abrirse en un explorador.|IRM:  <br/>  Usa cifrado y restricciones de uso para proporcionar protección en línea y sin conexión para los mensajes de correo electrónico y datos adjuntos.  <br/>  Ofrece, como administrador, la capacidad de configurar reglas de transporte o reglas de protección de Outlook para aplicar automáticamente IRM a mensajes seleccionados.  <br/>  Le permite a los usuarios aplicar plantillas manualmente en Outlook o en Outlook en la Web (anteriormente denominado Outlook Web App).|S/MIME aborda la autenticación de remitentes con firmas digitales y la confidencialidad de mensajes con cifrado.|
|¿Qué no hace?|OME no permite aplicar restricciones de uso a los mensajes. Por ejemplo, no se puede usar para impedir que un destinatario reenvíe o imprima un mensaje cifrado.|Algunas aplicaciones pueden no admitir los mensajes de correo electrónico de IRM en todos los dispositivos. Para obtener más información sobre estos y otros productos compatibles con el correo electrónico de IRM, vea [Funciones del dispositivo de cliente](https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities).|S/MIME no permite analizar los mensajes cifrados en búsqueda de malware, correo no deseado o directivas.|
|Recomendaciones y escenarios de ejemplo|Se recomienda usar OME cuando desea enviar información empresarial confidencial a personas fuera de su organización, ya sean consumidores u otras empresas. Por ejemplo:  <br/>  Un empleado bancario que envía extractos de tarjeta de crédito a los clientes  <br/>  Un consultorio que envía registros médicos a un paciente  <br/>  Un abogado que envía información legal confidencial a otro abogado|Se recomienda usar IRM para aplicar restricciones de uso y también cifrado. Por ejemplo:  <br/>  Un administrador que envía detalles confidenciales a su equipo sobre un nuevo producto aplica la opción “No reenviar”.  <br/>  Un ejecutivo necesita compartir una propuesta de oferta con otra compañía, que incluye datos adjuntos de un socio que usa Office 365, y requieren que el correo electrónico y los datos adjuntos estén protegidos.|Se recomienda usar S/MIME cuando su organización o la organización del destinatario requieran un auténtico cifrado de punto a punto.  <br/>  Normalmente se usa S/MIME en los siguientes escenarios:  <br/>  Autoridades gubernamentales que se comunican con otras autoridades gubernamentales  <br/>  Una empresa que se comunica con una autoridad gubernamental|
   
## <a name="what-encryption-options-are-available-for-my-office-365-subscription"></a>¿Qué opciones de cifrado están disponibles para mi suscripción de Office 365?

Para obtener más información sobre las opciones de cifrado de correo electrónico para su suscripción de Office 365 vea la [descripción del servicio Exchange Online](https://technet.microsoft.com/en-us/library/exchange-online-service-description.aspx). Aquí encontrará información sobre las siguientes características de cifrado:
  
- Azure RMS, incluidas las capacidades IRM y OME
    
- S/MIME
    
- TLS
    
- Cifrado de datos en reposo (mediante BitLocker)
    
## <a name="what-about-encryption-for-data-at-rest"></a>¿Qué sucede con el cifrado de datos en reposo?

El término "Datos en reposo" hace referencia a datos que no están activos en tránsito. En Office 365, los datos de correo electrónico en reposo se cifran mediante el cifrado de unidad BitLocker. BitLocker cifra las unidades de disco duro en centros de datos de Office 365 para proporcionar mayor protección frente a accesos no autorizados. Para obtener más información,[consulte Información general de BitLocker](https://go.microsoft.com/fwlink/p/?LinkId=394737).
  
## <a name="more-information-about-email-encryption-options-in-office-365"></a>Más información sobre opciones de cifrado de correo electrónico en Office 365

Para obtener más información sobre las opciones de cifrado de correo electrónico en este artículo, así como TLS, consulte los siguientes artículos:
  
 **OME**
  
[Cifrado de mensajes de Office 365 (OME)](ome.md)
  
 **IRM**
  
[Information Rights Management en Exchange Online](https://technet.microsoft.com/en-us/library/jj983436%28v=exchg.150%29.aspx)
  
[¿Qué es Azure Rights Management?](https://technet.microsoft.com/library/jj585026)
  
 **S/MIME**
  
[S/MIME para la firma y cifrado de mensajes](https://technet.microsoft.com/library/dn626158)
  
[Información sobre S/MIME](https://technet.microsoft.com/library/aa995740%28v=exchg.65%29.aspx)
  
[Descripción de la criptografía mediante claves públicas](https://technet.microsoft.com/library/aa998077%28v=exchg.65%29.aspx) 
  
 **TLS**
  
[Configurar el flujo del correo personalizado mediante conectores en Office 365](https://technet.microsoft.com/en-us/library/jj723138%28v=exchg.150%29.aspx)
  


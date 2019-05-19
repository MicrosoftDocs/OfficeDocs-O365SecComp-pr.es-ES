---
title: Configurar SPF en Office 365 para ayudar a evitar la suplantación de identidad
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 2/19/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
description: 'Resumen: En este artículo se describe cómo actualizar un registro de servicio de nombre de dominio (DNS) para poder utilizar un marco de directivas de remitente (SPF) con su dominio personalizado en Office 365. SPF permite validar el correo electrónico saliente enviado desde su dominio personalizado.'
ms.openlocfilehash: 5194a9a8a8b694bc2dbac0eaf9b50517e46a9064
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158202"
---
# <a name="set-up-spf-in-office-365-to-help-prevent-spoofing"></a>Configurar SPF en Office 365 para ayudar a evitar la suplantación de identidad

 **Resumen:** En este artículo se describe cómo actualizar un registro de servicio de nombre de dominio (DNS) para poder utilizar un marco de directivas de remitente (SPF) con su dominio personalizado en Office 365. SPF permite validar el correo electrónico saliente enviado desde su dominio personalizado. 
  
Para poder utilizar un dominio personalizado, Office 365 requiere que agregue un registro TXT de marco de directivas de remitente (SPF) en su registro DNS para ayudar a evitar la suplantación de identidad. SPF identifica qué servidores de correo pueden enviar correo en su nombre. Básicamente, puede evitar la suplantación de identidad con la ayuda de SPF, junto con DKIM, DMARC y otras tecnologías compatibles con Office 365. SPF se agrega como un registro TXT que DNS usa para identificar qué servidores de correo pueden enviar correo en nombre de su dominio personalizado. Los destinatarios pueden consultar el registro TXT de SPF para determinar si un mensaje de su dominio personalizado procede de un servidor de mensajería autorizado.
  
Por ejemplo, supongamos que el dominio personalizado contoso.com usa Office 365. Le agrega un registro TXT de SPF que incluye los servidores de mensajería de Office 365 como servidores de correo legítimos para su dominio. Cuando el servidor de mensajería receptor obtiene un mensaje de joe@contoso.com, el servidor busca el registro TXT de SPF para contoso.com y averigua si el mensaje es válido. Si el servidor receptor descubre que el mensaje proviene de un servidor que no es ninguno de los servidores de mensajería de Office 365 indicados en el registro SPF, el servidor de correo receptor puede rechazar el mensaje como correo no deseado.
  
Además, si el dominio personalizado no tiene un registro TXT de SPF, algunos servidores de recepción pueden rechazar directamente el mensaje. Esto se debe a que el servidor de recepción no puede validar que los mensajes procedan de un servidor de mensajería autorizado.
  
Si ya ha configurado el correo para Office 365, ya ha incluido servidores de mensajería de Microsoft en DNS como un registro TXT de SPF. Sin embargo, en algunos casos puede que sea necesario actualizar el registro TXT de SPF en DNS. Por ejemplo:
  
- Antes, debía agregar un registro TXT de SPF diferente a su dominio personalizado si utilizaba SharePoint Online. Esto ya no es necesario. Este cambio debería reducir el riesgo de que los mensajes de notificación de SharePoint Online acaben en la carpeta de Correo no deseado. Actualice su registro SPF TXT si ha alcanzado el límite de 10 búsquedas y recibe errores como "Límite de búsqueda superado" y "Demasiados saltos".
    
- Tiene un entorno híbrido con Office 365 y Exchange local.
    
- Quiere configurar DKIM y DMARC (recomendado).
    
## <a name="updating-your-spf-txt-record-for-office-365"></a>Actualizar el registro TXT de SPF para Office 365

Antes de actualizar el registro TXT de DNS, debe recopilar cierta información y determinar el formato del registro. Esto le ayudará a impedir que se generen errores de DNS. Para obtener ejemplos avanzados y explicaciones más detalladas sobre la sintaxis admitida de SPF, vea [Cómo funciona SPF para evitar la suplantación de IP y la suplantación de identidad en Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).
  
Recopile esta información:
  
- Registro TXT de SPF actual para su dominio personalizado. Para obtener instrucciones, vea [Recopilar la información necesaria para crear los registros de DNS de Office 365](https://support.office.microsoft.com/en-us/article/Gather-the-information-you-need-to-create-Office-365-DNS-records-77f90d4a-dc7f-4f09-8972-c1b03ea85a67).
    
- Direcciones IP de todos los servidores de mensajería locales. Por ejemplo, **192.168.0.1**.
    
- Nombres de dominio que se usarán para todos los dominios de terceros que necesita incluir en el registro TXT de SPF. Algunos proveedores de correo masivo tienen configurados subdominios para sus clientes. Por ejemplo, la empresa MailChimp tiene configurado **servers.mcsv.net**.
    
- Determine qué regla de cumplimiento quiere usar para el registro TXT de SPF. Se recomienda **-all**. Para obtener más información sobre otras opciones de sintaxis, vea [Sintaxis del registro TXT SPF para Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).
    
### <a name="to-add-or-update-your-spf-txt-record"></a>Para agregar o actualizar el registro TXT de SPF

1. Si todavía no lo ha hecho, para formar el registro TXT de SPF use la sintaxis de la tabla siguiente:
    
||**Si usa...**|**¿Común para los clientes de Office 365?**|**Agregue esto...**|
|:-----|:-----|:-----|:-----|
|1  <br/> |Cualquier sistema de correo electrónico (obligatorio)  <br/> |Común. Todos los registros TXT de SPF comienzan con este valor  <br/> |v=spf1  <br/> |
|segundo  <br/> |Exchange Online  <br/> |Común  <br/> |include:spf.protection.outlook.com  <br/> |
|3  <br/> |Solo Exchange Online dedicado  <br/> |No es común  <br/> |IP4:23.103.224.0/19 IP4:206.191.224.0/19 IP4:40.103.0.0/16 include include SPF. Protection. Outlook. com  <br/> |
|4  <br/> |Solo para Office 365 Alemania y Microsoft Cloud Alemania  <br/> |No es común  <br/> |incluir include SPF. Protection. Outlook. de  <br/> |
|2,5  <br/> |Sistema de correo electrónico de terceros  <br/> |No es común  <br/> |include:\<domain name\>  <br/> Where domain name is the domain name of the third party email system.  <br/> |
|6,5  <br/> |Sistema de correo local. Por ejemplo, Exchange Online Protection y otro sistema de correo electrónico  <br/> |No es común  <br/> | Use uno de estos para cada sistema de correo adicional:  <br/>  ip4:\<  _IP address_\>  <br/>  ip6:\<  _IP address_\>  <br/>  include:\<  _domain name_\>  <br/>  Donde el valor de \<  _IP address_\> es la dirección IP del otro sistema de correo y \< _domain name_\> es el nombre de dominio del otro sistema de correo que envía correo en nombre de su dominio.  <br/> |
|0,7  <br/> |Cualquier sistema de correo electrónico (obligatorio)  <br/> |Común. Todos los registros TXT de SPF acaban con este valor  <br/> |\< _enforcement rule_\>  <br/> Puede ser uno de varios valores. Le recomendamos que use **-all**.  <br/> |
   
1,1 por ejemplo, si está completamente hospedado en Office 365, es decir, no tiene ningún servidor de correo local, el registro TXT de SPF incluiría las filas 1, 2 y 7 y tendría el siguiente aspecto:
    
  ```
   v=spf1 include:spf.protection.outlook.com -all
  ```

1,2 este es el registro TXT SPF de Office 365 más común. Este registro funciona para casi todos los usuarios, independientemente de si el centro de trabajo de Office 365 está ubicado en Estados Unidos o en Europa (incluido Alemania) o en otra ubicación.
    
1,3 sin embargo, si ha adquirido Office 365 Germany, parte de Microsoft Cloud Germany, debe usar la instrucción include de la línea 4 en lugar de la línea 2. Por ejemplo, si está completamente hospedado en Office 365 Germany, es decir, no tiene ningún servidor de correo local, el registro TXT de SPF incluiría las filas 1, 4 y 7 y tendría el siguiente aspecto:
    
  ```
   v=spf1 include:spf.protection.outlook.de -all
  ```

1,4 Si ya se ha implementado en Office 365 y ha configurado los registros TXT de SPF para su dominio personalizado y va a migrar a Office 365 Germany, debe actualizar el registro TXT de SPF. Para ello, cambie **incluir include SPF. Protection. Outlook. com** para **incluir include SPF. Protection. Outlook. de**.
    
2. Una vez que ha formado el registro TXT de SPF, debe actualizar el registro en DNS. Solo puede tener un registro TXT de SPF para un dominio. Si existe un registro TXT de SPF, en vez de agregar un registro nuevo, debe actualizar el registro existente. Vaya a [Crear registros DNS para Office 365 al administrar los registros DNS](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide) y haga clic en el vínculo para su host DNS. 
    
3. Pruebe el registro TXT de SPF.
    
## <a name="more-information-about-spf"></a>Más información sobre SPF

Para obtener ejemplos avanzados y explicaciones más detalladas sobre la sintaxis admitida de SPF, la suplantación de identidad, la solución de problemas y la manera en que Office 365 admite SPF, vea [Cómo funciona SPF para evitar la suplantación de IP y la suplantación de identidad en Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).
  
## <a name="next-steps-after-you-set-up-spf-for-office-365"></a>Pasos siguientes: Una vez configurado SPF para Office 365

¿Tiene problemas con el registro TXT de SPF? Lea [Solución de problemas: Procedimientos recomendados para SPF en Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).
  
 SPF está diseñado para ayudar a evitar la suplantación de identidad, pero existen técnicas de suplantación de identidad contra las que SPF no puede ofrecer protección. Para obtener protección contra estas, una vez que haya configurado SPF, también debe configurar DKIM y DMARC para Office 365. Vea [Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md) para comenzar. A continuación, vea [Usar DMARC para validar el correo electrónico en Office 365](use-dmarc-to-validate-email.md).
  


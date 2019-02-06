---
title: Vínculos seguros ATP de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.date: 02/05/2019
ms.topic: overview
f1_keywords:
- "197503"
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: La característica vínculos seguros proporciona comprobación de tiempo de clic de los hipervínculos en documentos de Office y en los mensajes de correo electrónico. Use los vínculos seguros para proteger la organización de suplantación de identidad y otros ataques.
ms.openlocfilehash: 7e610d23534dcd4c9ea20608bab6fca536f877cb
ms.sourcegitcommit: a64af0ebd0b03e4a5e60a33e9108c44c7d74f356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2019
ms.locfileid: "29741113"
---
# <a name="office-365-atp-safe-links"></a>Vínculos seguros ATP de Office 365

## <a name="overview-of-office-365-atp-safe-links"></a>Información general de Office 365 ATP seguras vínculos

> [!IMPORTANT]
> En este artículo está destinada a los clientes empresariales. Si es un usuario particular para obtener más información acerca de los vínculos seguros en Outlook, vea [seguridad de Outlook.com avanzadas](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

Vínculos seguros de ATP de Office 365 (parte de la [Protección contra amenazas de avanzada](office-365-atp.md)) puede ayudar a proteger su organización proporcionando comprobación de tiempo de clic de direcciones web (URL) en [mensajes de correo electrónico](#how-atp-safe-links-works-with-email) y [documentos de Office](#how-atp-safe-links-works-with-office-documents). Protección se define a través de [vínculos seguros ATP directivas](set-up-atp-safe-links-policies.md) que se han establecido por el equipo de seguridad de Office 365. 
  
Una vez que las directivas de vínculos seguros ATP, los administradores globales de Office 365, los administradores de seguridad y los lectores de seguridad pueden [Ver los informes de protección contra amenazas de avanzada](view-reports-for-atp.md). La información en los informes puede ayudar al equipo de seguridad lleve a cabo pasos adicionales para proteger su organización o la investigación de incidentes de seguridad.

Como [las nuevas características se agregan a ATP](office-365-atp.md#new-features-are-continually-being-added-to-atp), el equipo de seguridad de Office 365 puede agregar o modificar directivas de vínculos seguros ATP de su organización. Además, es posible que observe los cambios y mejoras, como nuestro recién revisado [las páginas de advertencia](atp-safe-links-warning-pages.md) y vínculo nativo de representación en Outlook.
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a>Funcionamiento de ATP seguros vínculos con direcciones URL en correo electrónico

En un nivel alto, aquí es cómo funciona la protección de vínculos seguros de ATP para las direcciones URL en el correo electrónico (hospedado en Office 365, no local):
  
1. Personas reciben mensajes de correo electrónico, algunos de los cuales contienen direcciones URL.
    
2. Todos los correos electrónicos circula a través de Exchange Online Protection, donde el protocolo de internet (IP) y sobre los filtros, firma-based malware protection, contra correo no deseado y se aplican los filtros de protección contra malware. 
    
3. Correo electrónico llega a las bandejas de entrada de otras personas.
    
4. Un usuario inicia sesión en Office 365 y va a su Bandeja de entrada de correo electrónico.
    
5. El usuario abre un mensaje de correo electrónico y hace clic en una dirección URL en el mensaje de correo electrónico.
    
6. La característica vínculos seguros ATP inmediatamente comprueba la dirección URL antes de abrir el sitio Web. La dirección URL se identifica como bloqueado, malintencionado o seguros.
    
    - Si la dirección URL es un sitio Web que se incluye en una [lista de direcciones URL de "no volver a escribir" personalizada](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) para una directiva que se aplica al usuario, se abre el sitio Web. 
    
    - Si la dirección URL es un sitio Web que se incluye en la [lista de direcciones URL bloqueado personalizada](set-up-a-custom-blocked-urls-list-wtih-atp.md)de la organización, se abre una [página de advertencia](atp-safe-links-warning-pages.md) . 
    
    - Si la dirección URL a un sitio Web que se ha determinado que ser malintencionado, se abrirá una [página de advertencia](atp-safe-links-warning-pages.md) . 
    
    - Si la dirección URL que se va a un archivo descargable y [vínculos seguros ATP directivas](set-up-atp-safe-links-policies.md) de su organización están configurados para examinar este tipo de contenido, se comprueba el archivo descargable. 
    
    - Si la dirección URL se determina como seguros, se abre el sitio Web.
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>Funcionamiento de ATP seguros vínculos con direcciones URL en documentos de Office

En un nivel alto, aquí es cómo funciona la protección de vínculos seguros de ATP para las direcciones URL en aplicaciones de Office 365 ProPlus (versiones actuales de Word, Excel y PowerPoint en Windows o Mac, las aplicaciones de Office de iOS o dispositivos Android, Visio en Windows, OneNote Online y Office Online):
  
1. Personas tener instalado Office 365 ProPlus en su equipo, smartphone o Tablet PC. (O bien, que utilicen Office Online en su explorador).
    
2. Un usuario abre un Word, Excel, PowerPoint o Visio e inicia sesión en Office 365 Enterprise mediante su cuenta de trabajo o escuela. El documento contiene las direcciones URL.
    
3. Cuando el usuario hace clic en una dirección URL del documento, se comprueba el vínculo por el servicio de vínculos seguros de ATP.
    
  - Si la dirección URL es un sitio Web que se incluye en una [lista de direcciones URL de "no volver a escribir" personalizada](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) para una directiva que se aplica al usuario, se toma ese usuario al sitio Web. 
    
  - Si la dirección URL es un sitio Web que se incluye en la [lista de direcciones URL bloqueado personalizada](set-up-a-custom-blocked-urls-list-wtih-atp.md)de la organización, se toma el usuario a una [página de advertencia](atp-safe-links-warning-pages.md).
    
  - Si la dirección URL es un sitio Web que se ha determinado que ser malintencionado, se toma el usuario a una [página de advertencia](atp-safe-links-warning-pages.md).
    
  - Si la dirección URL que se va a un archivo descargable y las [directivas de ATP seguros vínculos](set-up-atp-safe-links-policies.md) están configurados para examinar tales descargas, se comprueba el archivo descargable. 
    
  - Si la dirección URL se considera segura, se toma el usuario para el sitio Web.

## <a name="how-to-get-atp-safe-links-protection"></a>Cómo obtener protección vínculos seguros de ATP

En primer lugar, asegúrese de que la suscripción incluye [Avanzadas de protección contra amenazas](office-365-atp.md). ATP se incluye en suscripciones, como [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 educación A5, etcetera. Si su organización tiene una suscripción a Office 365 que no incluye Office 365 ATP, puede comprar potencialmente ATP como un complemento. Para obtener más información, vea [Office 365 avanzada Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). 
  
A continuación, asegúrese de que se definen las directivas de vínculos seguros de ATP. (Vea [configurar las directivas de seguros vínculos con Office 365 ATP](set-up-atp-safe-links-policies.md)). Las características de ATP seguros vínculos están activas cuando:
  
- **Las directivas de vínculos seguros de ATP se configuran** para el correo electrónico y para documentos de Word, Excel, PowerPoint y Visio. (Vea [configurar las directivas de ATP vínculos seguros en Office 365](set-up-atp-safe-links-policies.md)).

- **Aplicaciones de cliente de Office 365 están configuradas para usar autenticación moderno** (Esto es para la protección de vínculos seguros de ATP en documentos de Office). (Vea [moderno Authentication for Office 2016](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).) 
    
- **Los usuarios han iniciado sesión en Office 365** mediante su cuenta de trabajo o escuela. (Vea [iniciar sesión en Office 365 o de Office](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)).
    
- **Correo electrónico de la organización está hospedado en Office 365**. 

Para definir las directivas de ATP (o editar), debe asignar uno de los roles que se describen en la siguiente tabla:

|Rol  |Dónde y cómo asignado  |
|---------|---------|
|Administrador Global de Office 365 |La persona que se registra para comprar Office 365 es un administrador global de forma predeterminada. (Consulte [acerca de Office 365 roles de administrador](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para obtener más información).         |
|Administrador de seguridad de Office 365 |Centro de administración ([https://aka.ms/admincenter](https://aka.ms/admincenter))|
|Administración de la organización en línea de Exchange |Centro de administración de Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>o <br>  Cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
    
## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>Para que sea seguro de protección de ATP seguros vínculos está en su lugar

Como administrador global o administrador de seguridad, asegúrese de revisar las [directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md). Las directivas de vínculos seguros ATP determinan si protección se aplica a los hipervínculos en mensajes de correo electrónico sólo, o a las direcciones URL en documentos de Office así como.

Después de las directivas de vínculos seguros ATP están en su lugar, el equipo de seguridad de su organización puede ver vea cómo funciona protección vínculos seguros de ATP para la organización es mediante la [visualización de informes de protección avanzada de amenaza](view-reports-for-atp.md). 

## <a name="example-scenarios"></a>Escenarios de ejemplo
  
En la siguiente tabla se describe algunos escenarios de ejemplo donde protección vínculos seguros ATP puede ser o no en su lugar. (En todos estos casos, se supone que la organización tiene Office 365 Enterprise E5).
  
|**Escenario de ejemplo**|**¿Se aplica protección vínculos seguros de ATP en este caso?**|
|:-----|:-----|
|Jean es un miembro de un grupo que tiene directivas de vínculos seguros de ATP que tratan sobre las direcciones URL en correo electrónico y documentos de Office. Jean abre una presentación de PowerPoint que alguien envía y, a continuación, hace clic en una dirección URL de la presentación.  <br/> |Sí. Las directivas de vínculos seguros de ATP que se definen se aplican a de Jean grupo, de Jean correo electrónico y documentos de Word, Excel, PowerPoint o Visio que se abre Jean, siempre y cuando Jean ha iniciado sesión en y uso de Office 365 ProPlus en dispositivos Android, iOS o Windows.  <br/> |
|En la organización, no global o la seguridad de Chris los administradores han definido las directivas de vínculos seguros ATP todavía. Chris recibe un correo electrónico que contiene una dirección URL a un sitio Web malintencionado. Chris no conoce la dirección URL es malintencionada y hace clic en el vínculo.  <br/> |No. La directiva predeterminada que se trata las direcciones URL para todas las personas de la organización debe definirse en orden para la protección a estar en su lugar.  <br/> |
|En la organización, no global o la seguridad de Pat administradores han definido o editar las directivas de vínculos seguros ATP todavía. Pat abre un documento de Word y hace clic en una dirección URL en el archivo.  <br/> |Directiva de No. A que incluye documentos de Office debe definirse en orden para la protección a estar en su lugar. Consulte [configurar las directivas de vínculos seguros ATP de Office 365](set-up-atp-safe-links-policies.md).<br/> |
|Organización de Díaz tiene una directiva de vínculos seguros de ATP que tiene `http://tailspintoys.com` aparece como un sitio Web bloqueado. Lee recibe un mensaje de correo electrónico que contiene una dirección URL a `http://tailspintoys.com/aboutus/trythispage`. Lee hace clic en la dirección URL.<br/> |Depende de si todo el sitio y todos sus subpáginas se incluyen en la lista de URL bloquean. Consulte [Configurar una lista de direcciones URL bloqueada personalizada con vínculos seguros de ATP](set-up-a-custom-blocked-urls-list-wtih-atp.md).<br/> |
|Pablo, compañeros de Jean, envía un correo electrónico a Jean, sin saber que el correo electrónico contiene una dirección URL malintencionada.  <br/> |Depende de si se definen las directivas de vínculos seguros de ATP para el correo electrónico enviado dentro de la organización. Consulte [configurar las directivas de vínculos seguros ATP de Office 365](set-up-atp-safe-links-policies.md).<br/> |


  


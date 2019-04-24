---
title: Vínculos seguros de ATP de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.date: 03/05/2019
ms.topic: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: La característica de vínculos seguros proporciona la comprobación del tiempo de clic de los hipervínculos en los documentos de Office y en los mensajes de correo electrónico. Use vínculos seguros para proteger a su organización del phishing y otros ataques.
ms.openlocfilehash: 7dacb4184ff0b99887b2aa5f3fe2e65cd58c5b6b
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32249560"
---
# <a name="office-365-atp-safe-links"></a>Vínculos seguros de ATP de Office 365

## <a name="overview-of-office-365-atp-safe-links"></a>Información general sobre los vínculos seguros de ATP de Office 365

> [!IMPORTANT]
> Este artículo está dirigido a los clientes de Office 365 Enterprise. Si usa Outlook.com, Office 365 Home o Office 365 personal, y está buscando información sobre vínculos seguros en Outlook, consulte [Advanced Outlook.com Security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

Los vínculos seguros de Office 365 ATP (parte de la [protección contra amenazas avanzada](office-365-atp.md)) pueden ayudar a proteger su organización proporcionando una comprobación del tiempo de clic de direcciones web (URL) en [mensajes de correo electrónico](#how-atp-safe-links-works-with-urls-in-email) y [documentos de Office](#how-atp-safe-links-works-with-urls-in-office-documents). La protección se define mediante [las directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md) definidas por el equipo de seguridad de Office 365. 
  
Una vez que se hayan implementado las directivas de vínculos seguros de ATP, los administradores globales de Office 365, los administradores de seguridad y los lectores de seguridad podrán [ver los informes de la protección contra amenazas avanzada](view-reports-for-atp.md). La información de estos informes puede ayudar a su equipo de seguridad a tomar medidas adicionales para proteger su organización o investigar los incidentes de seguridad.

A medida que [se agregan nuevas características a ATP](office-365-atp.md#new-features-in-office-365-atp), el equipo de seguridad de Office 365 puede Agregar o editar [las directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md)de la organización. Además, es posible que observe cambios y mejoras como, por ejemplo, [las páginas de advertencia](atp-safe-links-warning-pages.md) recientemente revisadas y la representación de vínculos nativos en Outlook.
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a>Cómo funciona el vínculo seguro ATP con direcciones URL en el correo electrónico

En un nivel alto, aquí se muestra cómo funciona la protección de vínculos seguros de ATP para las direcciones URL en el correo electrónico (hospedado en Office 365, no en local):
  
1. Los usuarios reciben mensajes de correo electrónico, algunos de los cuales contienen direcciones URL.
    
2. Todo el correo electrónico se envía a través de Exchange Online Protection, donde se aplican los filtros de protocolo de Internet (IP) y sobre, protección contra malware basada en firmas, filtros de correo no deseado y antimalware. 
    
3. El correo electrónico llega a las bandejas de entrada de las personas.
    
4. Un usuario inicia sesión en Office 365 y se dirige a su bandeja de entrada de correo electrónico.
    
5. El usuario abre un mensaje de correo electrónico y hace clic en una dirección URL en el mensaje de correo electrónico.
    
6. La característica de vínculos seguros de ATP comprueba inmediatamente la dirección URL antes de abrir el sitio Web. La dirección URL se identifica como bloqueada, malintencionada o segura.
    
    - Si la dirección URL se refiere a un sitio web que se incluye en una [lista de direcciones URL "no reescribir" personalizada](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) para una directiva que se aplica al usuario, se abre el sitio Web. 
    
    - Si la dirección URL es un sitio web que se incluye en la [lista de direcciones URL bloqueadas personalizadas](set-up-a-custom-blocked-urls-list-wtih-atp.md)de la organización, se abre una [Página de advertencia](atp-safe-links-warning-pages.md) . 
    
    - Si la dirección URL es un sitio web que se ha determinado que es malintencionado, se abre una [Página de advertencia](atp-safe-links-warning-pages.md) . 
    
    - Si la dirección URL va a un archivo descargable y las [directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md) de la organización están configuradas para analizar dicho contenido, se comprueba el archivo descargable. 
    
    - Si se determina que la dirección URL es segura, se abrirá el sitio Web.
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>Cómo funciona el vínculo seguro ATP con direcciones URL en documentos de Office

En un nivel alto, aquí se muestra cómo funciona la protección de vínculos seguros de ATP para las direcciones URL en Office 365 proPlus Applications (versiones actuales de Word, Excel y PowerPoint en Windows o Mac, aplicaciones de Office en dispositivos iOS o Android, Visio en Windows, OneNote online y Office Online):
  
1. Los usuarios han instalado Office 365 proPlus en su equipo, smartphone o tableta. (O bien, están usando Office online en su explorador).
    
2. Un usuario abre un Word, Excel, PowerPoint o Visio y inicia sesión en Office 365 Enterprise con su cuenta profesional o educativa. El documento contiene direcciones URL.
    
3. Cuando el usuario hace clic en una dirección URL del documento, el servicio de vínculos seguros de ATP comprueba el vínculo.
    
      - Si la dirección URL se refiere a un sitio web que se incluye en una [lista de direcciones URL "no reescribir" personalizada](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) para una directiva que se aplica al usuario, dicho usuario se dirigirá al sitio Web. 
    
      - Si la dirección URL se redirigirá a un sitio web que se incluye en la [lista de direcciones URL bloqueadas personalizadas](set-up-a-custom-blocked-urls-list-wtih-atp.md)de la organización, se dirigirá al usuario a una [Página de advertencia](atp-safe-links-warning-pages.md).
    
      - Si la dirección URL es un sitio web que se ha determinado que es malintencionado, se le dirigirá a una [Página de advertencia](atp-safe-links-warning-pages.md).
    
      - Si la dirección URL va a un archivo descargable y las [directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md) están configuradas para analizar tales descargas, se comprueba el archivo descargable. 
    
      - Si la dirección URL se considera segura, el usuario se dirigirá al sitio Web.

## <a name="how-to-get-atp-safe-links-protection"></a>Cómo obtener protección de vínculos seguros de ATP

En **primer lugar, asegúrese de que la suscripción incluye [protección contra amenazas avanzada](office-365-atp.md)**. ATP se incluye en en las suscripciones, como [microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 enterprise E5, Office 365 Education A5, etc. Si su organización tiene una suscripción de Office 365 que no incluye ATP de Office 365, puede comprar ATP como complemento. Para obtener más información, vea los recursos siguientes: 

- [Planes y precios de la protección contra amenazas avanzada de Office 365](https://products.office.com/exchange/advance-threat-protection)

- [Descripción del servicio de Protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 
  
A **continuación, asegúrese de que las directivas de vínculos seguros de ATP estén definidas**. (Consulte [configurar las directivas de vínculos seguros de Office 365 ATP](set-up-atp-safe-links-policies.md).) Las características de vínculos seguros de ATP están activas cuando:
  
- Las directivas de vínculos seguros de ATP se configuran para correo electrónico y documentos de Office. (Consulte [configurar las directivas de vínculos seguros de ATP en Office 365](set-up-atp-safe-links-policies.md).)

- Las aplicaciones cliente de Office 365 están configuradas para usar la autenticación moderna (esto es para la protección de vínculos seguros de ATP en documentos de Office). (Vea [autenticación moderna para Office 2016](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).) 
    
- Los usuarios han iniciado sesión en Office 365 con su cuenta profesional o educativa. (Consulte [iniciar sesión en Office u office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)
    
- El correo electrónico de su organización pasa a través de Exchange Online Protection.  

Asegúrese **también de que tiene los permisos necesarios**. Para definir (o editar) las directivas de ATP, debe tener asignado un rol apropiado. En la tabla siguiente se describen algunos ejemplos:

|Role  |Dónde y cómo se asigna  |
|---------|---------|
|Administrador global de Office 365 |La persona que se registra para comprar Office 365 es un administrador global de forma predeterminada. (Consulte [acerca de los roles de administrador de Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para obtener más información).         |
|Administrador de seguridad |Centro de administración de Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ()|
|Administración de la organización de Exchange Online |Centro de administración de[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>o <br>  Cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
    
## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>Cómo asegurarse de que está disponible la protección de vínculos seguros de ATP

Como administrador global o administrador de seguridad, asegúrese de revisar las [directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md) con regularidad. Las directivas de vínculos seguros de ATP determinan si la protección se aplica a los hipervínculos en los mensajes de correo electrónico solamente o a las direcciones URL de los documentos de Office también.

Una vez colocadas las directivas de vínculos seguros de ATP, el equipo de seguridad de la organización puede ver cómo la protección de vínculos seguros de ATP funciona para su organización mediante la [visualización de informes para la protección contra amenazas avanzada](view-reports-for-atp.md). 

## <a name="example-scenarios"></a>Escenarios de ejemplo
  
En la tabla siguiente se describen algunos escenarios de ejemplo en los que la protección de vínculos seguros de ATP puede o no estar en su lugar. (En todos estos casos, suponemos que la organización tiene Office 365 Enterprise E5).
  
|**Escenario de ejemplo**|**¿Se aplica la protección de vínculos seguros ATP en este caso?**|
|:-----|:-----|
|Jean es miembro de un grupo que tiene directivas de vínculos seguros de ATP que abarcan direcciones URL en correo electrónico y documentos de Office. Jean abre una presentación de PowerPoint enviada por alguien y, a continuación, hace clic en una dirección URL de la presentación.  <br/> |Sí. Las directivas de vínculos seguros de ATP que se definen se aplican al grupo de Jean, el correo electrónico de Jean y los documentos de Word, Excel, PowerPoint o Visio que Jean abre, siempre que Jean inicie sesión y use Office 365 proPlus en dispositivos Windows, iOS o Android.  <br/> |
|En la organización de Carlos, ningún administrador global ni de seguridad ha definido todavía ninguna directiva de vínculos seguros de ATP. Chris recibe un correo electrónico que contiene una dirección URL a un sitio Web malintencionado. Carlos no sabe que la dirección URL es malintencionada y hace clic en el vínculo.  <br/> |No. La directiva predeterminada que cubre las direcciones URL para todos los usuarios de la organización debe definirse en orden para que la protección esté en su ubicación.  <br/> |
|En la organización de Pat, ningún administrador global ni de seguridad ha definido o modificado ninguna directiva de vínculos seguros de ATP. Pat abre un documento de Word y hace clic en una dirección URL en el archivo.  <br/> |No. Debe definirse una directiva que incluya documentos de Office para que la protección esté en su ubicación. Consulte [configurar las directivas de vínculos seguros de ATP en Office 365](set-up-atp-safe-links-policies.md).  <br/> |
|La organización de Lee tiene una directiva de vínculos seguros de `http://tailspintoys.com` ATP que se muestra como un sitio web bloqueado. Lee recibe un mensaje de correo electrónico que contiene una `http://tailspintoys.com/aboutus/trythispage`dirección URL para. Lee hace clic en la dirección URL.  <br/> |Depende de si todo el sitio y todas sus subpáginas están incluidos en la lista de direcciones URL bloqueadas. Consulte [configurar una lista de direcciones URL bloqueadas personalizadas mediante vínculos seguros de ATP](set-up-a-custom-blocked-urls-list-wtih-atp.md).  <br/> |
|Pablo, el colega de Jean, envía un correo electrónico a Jean, sin saber que el correo electrónico contiene una dirección URL malintencionada.  <br/> |Depende de si las directivas de vínculos seguros de ATP están definidas para correo electrónico enviado dentro de la organización. Consulte [configurar las directivas de vínculos seguros de ATP en Office 365](set-up-atp-safe-links-policies.md).  <br/> |


  


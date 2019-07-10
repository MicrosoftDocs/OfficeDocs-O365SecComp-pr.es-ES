---
title: Funcionamiento de los vínculos seguros de Office 365 ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.date: 05/19/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: La característica de vínculos seguros proporciona la comprobación del tiempo de clic de los hipervínculos en los documentos de Office y en los mensajes de correo electrónico. Lea este artículo para obtener información sobre cómo funciona el vínculo seguro ATP.
ms.openlocfilehash: 7570fd65a9831a6436eec8c402a2bc0c2ae09b40
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599186"
---
# <a name="how-office-365-atp-safe-links-works"></a>Funcionamiento de los vínculos seguros de Office 365 ATP
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a>Cómo funciona el vínculo seguro ATP con direcciones URL en el correo electrónico

En un nivel alto, aquí se muestra cómo funciona la protección de [vínculos seguros de ATP](atp-safe-links.md) para las direcciones URL en el correo electrónico (hospedado en Office 365, no en local):
  
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

En un nivel alto, aquí se muestra cómo funciona la protección de [vínculos seguros de ATP](atp-safe-links.md) para las direcciones URL en Office 365 ProPlus Applications (versiones actuales de Word, Excel y PowerPoint en Windows o Mac, aplicaciones de Office en dispositivos iOS o Android, Visio en Windows, OneNote online y Office En línea):
  
1. Los usuarios han instalado Office 365 ProPlus en su equipo, smartphone o tableta. (O bien, están usando Office online en su explorador).
    
2. Un usuario abre un Word, Excel, PowerPoint o Visio y inicia sesión en Office 365 Enterprise con su cuenta profesional o educativa. El documento contiene direcciones URL.
    
3. Cuando el usuario hace clic en una dirección URL del documento, el servicio de vínculos seguros de ATP comprueba el vínculo.
    
      - Si la dirección URL se refiere a un sitio web que se incluye en una [lista de direcciones URL "no reescribir" personalizada](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) para una directiva que se aplica al usuario, dicho usuario se dirigirá al sitio Web. 
    
      - Si la dirección URL se redirigirá a un sitio web que se incluye en la [lista de direcciones URL bloqueadas personalizadas](set-up-a-custom-blocked-urls-list-wtih-atp.md)de la organización, se dirigirá al usuario a una [Página de advertencia](atp-safe-links-warning-pages.md).
    
      - Si la dirección URL es un sitio web que se ha determinado que es malintencionado, se le dirigirá a una [Página de advertencia](atp-safe-links-warning-pages.md).
    
      - Si la dirección URL va a un archivo descargable y las [directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md) están configuradas para analizar tales descargas, se comprueba el archivo descargable. 
    
      - Si la dirección URL se considera segura, el usuario se dirigirá al sitio Web.


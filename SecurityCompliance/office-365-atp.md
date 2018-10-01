---
title: Protección contra amenazas avanzada de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/1/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
description: Protección contra amenazas avanzadas de Office 365 incluye inteligencia de suplantación, vínculos seguros, los datos adjuntos seguros y capacidades avanzadas de contra suplantación de identidad. Opciones avanzadas de protección contra amenazas también se ha ampliado a los archivos en SharePoint Online, OneDrive para la empresa y Microsoft Teams.
ms.openlocfilehash: 53488534d3a74f9e026142ed053dfcff5db6cbf9
ms.sourcegitcommit: 7032830867eb3fc71760e04b8342aff174c5d757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "25353276"
---
# <a name="office-365-advanced-threat-protection"></a>Protección contra amenazas avanzada de Office 365

Protección de amenaza avanzada de Office 365 (ATP) ayuda a proteger su organización frente a ataques malintencionados por:
  
- Análisis de archivos adjuntos de correo electrónico con [Datos adjuntos seguros de ATP](atp-safe-attachments.md)
    
- Análisis web direcciones (URL) en mensajes de correo electrónico y documentos de Office con [Vínculos seguros de ATP](atp-safe-links.md)
    
- Identificación y el bloqueo de archivos malintencionados en las bibliotecas en línea con [ATP para SharePoint, OneDrive y los equipos de Microsoft](atp-for-spo-odb-and-teams.md)
    
- Comprobación de los mensajes de correo electrónico de suplantación de identidad no autorizado con [suplantación de la inteligencia](learn-about-spoof-intelligence.md)
    
- Detectar cuando alguien intenta suplantar a los usuarios y dominios personalizados de la organización con [capacidades de ATP contra suplantación de identidad en Office 365](atp-anti-phishing.md)
    
**Protección a través de Office 365 ATP está determinada por las directivas que define el equipo de seguridad de su organización para vínculos seguros, los datos adjuntos seguros y contra suplantación de identidad**. Es importante revisar periódicamente y revisar las directivas para mantenerlos actualizados y a aprovechar las ventajas de las nuevas características que se agregan al servicio. [Los informes están disponibles](view-reports-for-atp.md) para mostrar cómo funciona ATP para su organización. Estos informes también pueden mostrar áreas donde es posible que necesite revisar y actualizar las directivas. Y, si dispone de los archivos que están marcados como malware que no debería ser, o archivos le gustaría que Microsoft para examinar, puede [Enviar archivos a Microsoft para su análisis](office-365-atp.md#submitlalware).
  
> [!IMPORTANT]
> Office 365 ATP se incluye en las suscripciones, como Office 365 Enterprise E5 y Office 365 educación A5 y, a partir del 30 de abril de 2018, también [las características de seguridad de Microsoft 365 empresarial](https://support.office.com/article/c123694a-1efb-459e-a8d5-2187975373dc). Si su organización tiene una suscripción a Office 365 que no incluye Office 365 ATP, puede comprar potencialmente ATP como un complemento. Para obtener más información, vea [Office 365 avanzada Threat Protection Service Description](https://technet.microsoft.com/library/exchange-online-advanced-threat-protection-service-description.aspx). 
      
## <a name="get-office-365-atp"></a>Obtener ATP de Office 365

1. Como administrador global o de seguridad, vaya a [https://portal.office.com](https://portal.office.com) y el inicio de sesión con la cuenta de trabajo o escuela para Office 365. 
    
2. Elija **Admin** \> **de facturación** para ver lo que incluye su suscripción actual. 
    
    ![Como un administrador global, inicie sesión en portal.office.com y vaya a administrador \> de facturación](media/18a3546c-bd1f-4f49-82ec-0184909b42c2.png)
  
3. Si ve **E5 Enterprise de Office 365**, **Office 365 educación A5**o **Microsoft 365 Business**, su organización tiene ATP. 
    
    Si ve una suscripción a diferente, como **Office 365 Enterprise E3** o **Office 365 Enterprise E1**, considere la posibilidad de agregar ATP. Para ello, elija **+ Agregar suscripción**.
    
Una vez que haya ATP, el siguiente paso es el equipo de seguridad definir las directivas de protección [contra suplantación de identidad](set-up-atp-anti-phishing-policies.md) , [Los datos adjuntos seguros](atp-safe-attachments.md)y [Vínculos seguros](atp-safe-links.md). 
  
[¿Qué quiere hacer?](office-365-atp.md#TOC)
  
## <a name="define-policies-for-atp"></a>Definir directivas de ATP

- **[Configurar directivas de vínculos seguros de ATP en Office 365](set-up-atp-safe-links-policies.md)** incluidos [lista personalizada de direcciones URL bloqueado](set-up-a-custom-blocked-urls-list-wtih-atp.md) y la [lista de direcciones URL personalizada "No reescritura"](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) de su organización
    
- **[Configurar los datos adjuntos seguros de ATP directivas en Office 365](set-up-atp-safe-attachments-policies.md)** que puede incluir [la entrega dinámica y obtener una vista previa](dynamic-delivery-and-previewing.md)
    
- **[Configurar directivas de ATP contra suplantación de identidad en Office 365](set-up-atp-anti-phishing-policies.md)** incluyendo ataques de suplantación en protección contra los intrusos que envían los mensajes de correo electrónico que parecen proceder de personas de confianza o dominios 
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a>Vea cómo funciona ATP mediante la visualización de informes

Una vez sus directivas de ATP, están disponibles para mostrar cómo funciona el servicio de informes.

[![La seguridad &amp; panel del centro de cumplimiento puede ayudarle a ver dónde está trabajando avanzada de protección contra amenazas](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)
  
1. Asegúrese de que es un administrador global, Administrador de seguridad o el lector de seguridad de Office 365. (Vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).)
    
2. [Visualización de informes de protección contra amenazas de avanzada y Exchange Online Protection](view-reports-for-atp.md).
    
3. Si es necesario, realizar ajustes en las directivas de seguridad. Vea los siguientes recursos:
    
  - [Directivas de vínculos seguros de ATP en Office 365](set-up-atp-safe-links-policies.md)
    
  - [Directivas de los datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md)
    
  - [Directivas de ATP contra suplantación de identidad en Office 365](set-up-atp-anti-phishing-policies.md)
    
[¿Qué quiere hacer?](office-365-atp.md)
  
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a>Enviar un archivo sospechoso a Microsoft para su análisis

Si recibe un archivo que cree que podría ser malware, puede enviar ese archivo a Microsoft para su análisis. Visite el [portal de envío de inteligencia de seguridad de Windows Defender](https://go.microsoft.com/fwlink/?linkid=857185).
  
## <a name="related-topics"></a>Temas relacionados

[Información general de la seguridad de Office 365 &amp; centro de cumplimiento](https://support.office.com/article/a5f2fd18-b029-4257-b5a8-ae83e7768c85)
  
[Ver los informes de protección contra amenazas de avanzada](view-reports-for-atp.md)
  
[Administración de la seguridad de Office 365 de amenazas &amp; centro de cumplimiento](threat-management.md)
  


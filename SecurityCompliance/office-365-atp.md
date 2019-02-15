---
title: Protección contra amenazas avanzada de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/08/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: La protección contra amenazas avanzada de Office 365 incluye inteligencia engañosa, vínculos seguros, datos adjuntos seguros, capacidades avanzadas antiphishing e inteligencia de amenazas.
ms.openlocfilehash: d78b37ca048187a298b6e083b54ad68b949638ef
ms.sourcegitcommit: 2af6c3e8a74995294a67429530af8f085e6ca136
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2019
ms.locfileid: "30051181"
---
# <a name="office-365-advanced-threat-protection"></a>Protección contra amenazas avanzada de Office 365

## <a name="overview-of-office-365-advanced-threat-protection"></a>Información general sobre la protección contra amenazas avanzada de Office 365

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales. Si es un usuario doméstico que busca información sobre vínculos seguros en Outlook, consulte [Advanced Outlook.com Security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

La protección contra amenazas avanzada de Office 365 (ATP) ayuda a proteger su organización contra ataques malintencionados al:
  
- Analizar archivos adjuntos de correo electrónico en busca de malware con [datos adjuntos seguros de ATP](atp-safe-attachments.md)
    
- Análisis de direcciones web (URL) en mensajes de correo electrónico y documentos de Office con [vínculos seguros de ATP](atp-safe-links.md)
    
- Identificación y bloqueo de archivos malintencionados en bibliotecas en línea con [ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md)
    
- Comprobación de mensajes de correo electrónico para la suplantación no autorizada con [inteligencia](learn-about-spoof-intelligence.md) de suplantación
    
- Detectar cuándo alguien intenta suplantar a los usuarios y los dominios personalizados de la organización con las [funcionalidades contra el suplantado de identidad ATP en Office 365](atp-anti-phishing.md)
    
**La protección a través de Office 365 ATP está determinada por las directivas que define el equipo de seguridad de su organización para vínculos seguros, datos adjuntos seguros y antiphishing**. Es importante definir directivas y revisar periódicamente las directivas para mantenerlas actualizadas y aprovechar las ventajas de las nuevas características que se agregan al servicio. 

Los [informes están disponibles](view-reports-for-atp.md) para mostrar cómo está trabajando ATP para su organización. Estos informes también le pueden mostrar áreas en las que es posible que deba revisar y actualizar las directivas. Además, si tiene archivos que están marcados como malware que no deben o archivos que desea que Microsoft examine, puede [Enviar un archivo a Microsoft para su análisis](#submit-a-suspicious-file-to-microsoft-for-analysis).

## <a name="new-features-are-continually-being-added-to-atp"></a>Las nuevas características se agregan continuamente a ATP

Seguimos agregando nuevas características a Office 365 y esto incluye ATP. A continuación se muestra una lista de varias características nuevas, algunas de las cuales llaman para revisar y actualizar una directiva de ATP. Para obtener más información acerca de las nuevas características disponibles para ATP (o Microsoft 365 en general), visite el [plan de desarrollo de microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).


|Actualizaciones de características  |Elementos de acción  |
|---------|---------|
|A partir de febrero de 2019 y la implementación en los próximos meses, las capacidades de inteligencia sobre amenazas se agregan a ATP. Además, si su organización no tiene ATP, tendrá que tener en cuenta nuevas opciones, incluidos el plan 1 de ATP y el plan ATP 2. Para obtener más información, consulte [planes y precios](https://products.office.com/exchange/advance-threat-protection) de la protección contra amenazas avanzada de Office 365 y la [Descripción del servicio de protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). |Revise la suscripción de su organización y, si es necesario, [compre o edite un complemento](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on).  |
|A partir de octubre de 2018 y de implementarse durante los próximos meses, cuando los usuarios usan Outlook o Outlook Web Application (OWA), los vínculos seguros ATP representan las direcciones URL originales, no las URL reescritas. (Llamamos a esta representación de vínculos nativos).<br>Cuando la representación de vínculos nativos está disponible para su organización, esta característica funcionará en Outlook 365 (hacer clic y ejecutar) y en OWA.|Ninguno         |
|A partir de 2018 de septiembre, [las páginas de advertencia de ATP de Office 365](atp-safe-links-warning-pages.md) presentan una nueva combinación de colores, más detalles y la posibilidad de continuar a un sitio a pesar de determinadas advertencias y recomendaciones. |Ninguno         |
|A partir de la segunda mitad de 2018, la protección de vínculos seguros de ATP se extiende para aplicarse a las direcciones URL en Office Online (Word online, Excel online, PowerPoint online, OneNote online) y Office 365 proPlus en Mac.   |[Revisar y editar las directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md)  |
|Desde tarde Mayo 2018, las capacidades de [cuarentena](quarantine-email-messages.md) del centro &amp; de seguridad y cumplimiento se amplían a [ATP para SharePoint Online, OneDrive para la empresa y Microsoft Teams](atp-for-spo-odb-and-teams.md). |[Revisar y editar las directivas de datos adJuntos seguros de ATP](set-up-atp-safe-attachments-policies.md) |
|A partir de 2018 de marzo, la protección de vínculos seguros de ATP se extiende para aplicarse al correo electrónico que se envía entre personas de una organización. |[Revisar y editar las directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md) |
|A partir de la 2017 de octubre de, la protección de vínculos seguros de ATP se extiende para aplicarse a las direcciones URL en el correo electrónico, así como a las direcciones URL de los documentos de Office 365 proPlus, como Word, Excel, PowerPoint y Visio en Windows, así como las aplicaciones de Office en dispositivos iOS y Android.  |Asegurarse de que está usando la [autenticación moderna para Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) |

## <a name="get-office-365-atp"></a>Obtener Office 365 ATP

Office 365 ATP se incluye en suscripciones, como [microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 enterprise E5 y Office 365 Education A5. Si su organización tiene una suscripción de Office 365 que no incluye ATP de Office 365, puede comprar ATP como complemento. Para obtener más información, consulte [planes y precios](https://products.office.com/exchange/advance-threat-protection) de la protección contra amenazas avanzada de Office 365 y la [Descripción del servicio de protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). 

## <a name="define-policies-for-atp"></a>Definir directivas para ATP

Para definir (o editar) las directivas de ATP, debe tener asignado uno de los roles descritos en la tabla siguiente:

|Rol  |Dónde y cómo se asigna  |
|---------|---------|
|Administrador global de Office 365 |La persona que se registra para comprar Office 365 es un administrador global de forma predeterminada. (Consulte [acerca de los roles de administrador de Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para obtener más información).         |
|Administrador de seguridad |Centro de administración de Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ()|
|Administración de la organización de Exchange Online |Centro de administración de[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>o <br>  Cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

> [!TIP]
> Para obtener más información acerca de los roles y los permisos, consulte perMissions [in the Office 365 &amp; Security Compliance Center](permissions-in-the-security-and-compliance-center.md).

Hay varios tipos de directivas de ATP para definir y revisar de forma periódica.

1. **[Configure las directivas antiphishing de ATP en Office 365](set-up-anti-phishing-policies.md)** , incluidos los ataques basados en suplantación para proteger contra los atacantes que envían mensajes de correo electrónico que parecen pertenecer a personas o dominios de confianza. 

2. **[Configure las directivas de vínculos seguros ATP en Office 365](set-up-atp-safe-links-policies.md)** , incluida la [lista de URL bloqueadas personalizadas](set-up-a-custom-blocked-urls-list-wtih-atp.md) de su organización y la [lista de direcciones URL personalizadas "no reescribir"](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
    
3. **[Configure las directivas de datos adjuntos seguros ATP en Office 365](set-up-atp-safe-attachments-policies.md)** y elija entre varias opciones, como la [entrega dinámica y la vista previa](dynamic-delivery-and-previewing.md).
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a>Ver cómo está funcionando ATP viendo los informes

Una vez que se hayan implementado las directivas de ATP, los informes estarán disponibles para mostrar cómo funciona el servicio. (en el centro de cumplimiento de Office 365 Security &, vaya a **informes** > de**panel**).

[![El panel &amp; del centro de seguridad y cumplimiento puede ayudarle a ver dónde está funcionando la protección contra amenazas avanzada](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)
  
1. Como administrador global de Office 365, administrador de seguridad o lector de seguridad, vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión.
    
2. Vaya a **** > **Panel**de informes. (Para obtener ayuda con estos informes, consulte [ver informes para la protección contra amenazas avanzada](view-reports-for-atp.md)).
    
3. Si es necesario, realice ajustes en las directivas de seguridad. Para obtener ayuda, vea los siguientes recursos:
    - [Directivas contra la suplantación de identidad ATP](set-up-anti-phishing-policies.md)
    - [Directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md)
    - [Directivas de datos adJuntos seguros de ATP](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a>Enviar un archivo sospechoso a Microsoft para su análisis

- Si obtiene un archivo que sospecha que podría ser malware, puede enviar ese archivo a Microsoft para su análisis. Visite el [portal de envío de inteligencia en seguridad de Windows Defender](https://go.microsoft.com/fwlink/?linkid=857185).

- Si recibe un mensaje de correo electrónico (con o sin datos adjuntos) que le gustaría enviar a Microsoft para su análisis, use el [complemento de mensajes de informe](enable-the-report-message-add-in.md). 
  


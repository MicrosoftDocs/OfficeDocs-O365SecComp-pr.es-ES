---
title: Protección contra amenazas avanzada de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/04/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
description: Protección contra amenazas avanzadas de Office 365 incluye inteligencia de suplantación, vínculos seguros, los datos adjuntos seguros y capacidades avanzadas de contra suplantación de identidad. Opciones avanzadas de protección contra amenazas también se ha ampliado a los archivos en SharePoint Online, OneDrive para la empresa y Microsoft Teams.
ms.openlocfilehash: 7d60ac9bff108a6746a5e89d05d70bba23d2671d
ms.sourcegitcommit: a64af0ebd0b03e4a5e60a33e9108c44c7d74f356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2019
ms.locfileid: "29741043"
---
# <a name="office-365-advanced-threat-protection"></a>Protección contra amenazas avanzada de Office 365

## <a name="overview-of-office-365-advanced-threat-protection"></a>Información general de Office 365 protección avanzada

Protección de amenaza avanzada de Office 365 (ATP) ayuda a proteger su organización frente a ataques malintencionados por:
  
- Análisis de archivos adjuntos de correo electrónico de malware con [Datos adjuntos seguros de ATP](atp-safe-attachments.md)
    
- Análisis web direcciones (URL) en mensajes de correo electrónico y documentos de Office con [Vínculos seguros de ATP](atp-safe-links.md)
    
- Identificación y el bloqueo de archivos malintencionados en las bibliotecas en línea con [ATP para SharePoint, OneDrive y los equipos de Microsoft](atp-for-spo-odb-and-teams.md)
    
- Comprobación de los mensajes de correo electrónico de suplantación de identidad no autorizado con [suplantación de la inteligencia](learn-about-spoof-intelligence.md)
    
- Detectar cuando alguien intenta suplantar a los usuarios y dominios personalizados de la organización con [capacidades de ATP contra suplantación de identidad en Office 365](atp-anti-phishing.md)
    
**Protección a través de Office 365 ATP está determinada por las directivas que define el equipo de seguridad de su organización para vínculos seguros, los datos adjuntos seguros y contra suplantación de identidad**. Es importante para definir las directivas y revisar periódicamente y revisar dichas directivas para mantenerlos actualizados y a aprovechar las ventajas de las nuevas características que se agregan al servicio. 

[Los informes están disponibles](view-reports-for-atp.md) para mostrar cómo funciona ATP para su organización. Estos informes también pueden mostrar áreas donde es posible que necesite revisar y actualizar las directivas. Y, si dispone de los archivos que están marcados como malware que no debería ser, o archivos le gustaría que Microsoft para examinar, puede [Enviar un archivo a Microsoft para su análisis](#submit-a-suspicious-file-to-microsoft-for-analysis).

## <a name="new-features-are-continually-being-added-to-atp"></a>Las nuevas características se están agregando continuamente ATP

Para agregar nuevas características a Office 365, estamos siguiendo e incluye ATP. A continuación se presenta una lista de varias características nuevas, algunas de las cuales llamar para que una directiva de ATP ser revisado y actualizado. Para obtener más información acerca de las nuevas características que incide en ATP (o 365 de Microsoft en general), visite la [Guía básica de 365 de Microsoft](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).


|Actualizaciones de características  |Elementos de acción  |
|---------|---------|
|A partir de octubre de 2018 e implantar durante los próximos meses, cuando las personas están utilizando Outlook o Outlook Web Application (OWA), vínculos seguros ATP procesa las direcciones URL originales, no se modificó las direcciones URL. (Llamamos a esta representación de vínculo nativo).<br>Cuando la representación de vínculo nativo está disponible para su organización, esta característica funcionará en 365 (Click-to-Run) de Outlook y OWA.|Ninguno         |
|Principio en septiembre de 2018, la característica de [páginas de advertencia de Office 365 ATP](atp-safe-links-warning-pages.md) una nueva combinación de colores, más detalles y la capacidad para seguir a un sitio a pesar de recibir advertencias y recomendaciones. |Ninguno         |
|A partir de la segunda parte de 2018, protección de vínculos seguros de ATP se ha ampliado para aplicar a las direcciones URL en Office Online (en línea de Word, Excel Online, Online de PowerPoint y OneNote en línea) y Office 365 ProPlus en Mac.   |[Revisar y modificar las directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md)  |
|A partir de las últimas mayo de 2018, capacidades de [cuarentena](quarantine-email-messages.md) en la seguridad &amp; centro de cumplimiento se están extendiendo a [ATP para SharePoint Online, OneDrive para la empresa y los equipos de Microsoft](atp-for-spo-odb-and-teams.md). |[Revisar y modificar las directivas de los datos adjuntos seguros de ATP](set-up-atp-safe-attachments-policies.md) |
|A partir de marzo de 2018, protección de vínculos seguros de ATP se ha ampliado para aplicar a correo electrónico enviado entre personas dentro de una organización. |[Revisar y modificar las directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md) |
|A partir de las últimas de 2017 octubre, protección de vínculos seguros de ATP se ha ampliado para aplicar a las direcciones URL en correo electrónico, así como las direcciones URL en documentos de Office 365 ProPlus, como Word, Excel, PowerPoint y Visio en Windows, así como Office las aplicaciones de iOS y dispositivos Android.  |Asegúrese de que está utilizando [Autenticación moderno para Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) |
  
## <a name="get-office-365-atp"></a>Obtener ATP de Office 365

Office 365 ATP se incluye en las suscripciones, como [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5 y Office 365 educación A5. Si su organización tiene una suscripción a Office 365 que no incluye Office 365 ATP, puede comprar potencialmente ATP como un complemento. Para obtener más información, vea [Office 365 avanzada Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). 

## <a name="define-policies-for-atp"></a>Definir directivas de ATP

Para definir las directivas de ATP (o editar), debe asignar uno de los roles que se describen en la siguiente tabla:

|Rol  |Dónde y cómo asignado  |
|---------|---------|
|Administrador Global de Office 365 |La persona que se registra para comprar Office 365 es un administrador global de forma predeterminada. (Consulte [acerca de Office 365 roles de administrador](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para obtener más información).         |
|Administrador de seguridad de Office 365 |Centro de administración ([https://aka.ms/admincenter](https://aka.ms/admincenter))|
|Administración de la organización en línea de Exchange |Centro de administración de Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>o <br>  Cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

Hay varios tipos de directivas de ATP para definir y revisar periódicamente.

1. **[Configurar directivas de ATP contra suplantación de identidad en Office 365](set-up-anti-phishing-policies.md)** incluyendo ataques de suplantación en protección contra los intrusos que envían los mensajes de correo electrónico que parece ser de confianza de personas o dominios. 

2. **[Configurar directivas de vínculos seguros de ATP en Office 365](set-up-atp-safe-links-policies.md)** incluidos [lista personalizada de direcciones URL bloqueado](set-up-a-custom-blocked-urls-list-wtih-atp.md) y la [lista de direcciones URL personalizada "No reescritura"](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)de su organización.
    
3. **[Configurar las directivas de los datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md)** y elija entre varias opciones, como [la entrega dinámica y obtener una vista previa](dynamic-delivery-and-previewing.md).
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a>Vea cómo funciona ATP mediante la visualización de informes

Una vez sus directivas de ATP, están disponibles para mostrar cómo funciona el servicio de informes. (En el centro de cumplimiento de seguridad de Office 365 &, vaya a **informes** > **panel**.)

[![La seguridad &amp; panel del centro de cumplimiento puede ayudarle a ver dónde está trabajando avanzada de protección contra amenazas](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)
  
1. Como un administrador global de Office 365, el Administrador de seguridad o el lector de seguridad, vaya a [https://protection.office.com](https://protection.office.com) e iniciar sesión.
    
2. Vaya a **informes** > **panel**. (Para obtener ayuda con estos informes, vea [Ver informes de protección contra amenazas de avanzada](view-reports-for-atp.md)).
    
3. Si es necesario, realizar ajustes en las directivas de seguridad. Para obtener ayuda con esto, vea los siguientes recursos:
      - [Directivas de ATP contra suplantación de identidad en Office 365](set-up-anti-phishing-policies.md)
      - [Directivas de vínculos seguros de ATP en Office 365](set-up-atp-safe-links-policies.md)
      - [Directivas de los datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a>Enviar un archivo sospechoso a Microsoft para su análisis

- Si recibe un archivo que cree que podría ser malware, puede enviar ese archivo a Microsoft para su análisis. Visite el [portal de envío de inteligencia de seguridad de Windows Defender](https://go.microsoft.com/fwlink/?linkid=857185).

- Si recibe un mensaje de correo electrónico (con o sin datos adjuntos) que le gustaría usar para enviar a Microsoft para su análisis, use el [complemento en el mensaje de informe](enable-the-report-message-add-in.md). 
  


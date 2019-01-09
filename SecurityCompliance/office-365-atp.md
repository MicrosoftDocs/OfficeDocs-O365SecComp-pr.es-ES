---
title: Protección contra amenazas avanzada de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/08/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
description: Protección contra amenazas avanzadas de Office 365 incluye inteligencia de suplantación, vínculos seguros, los datos adjuntos seguros y capacidades avanzadas de contra suplantación de identidad. Opciones avanzadas de protección contra amenazas también se ha ampliado a los archivos en SharePoint Online, OneDrive para la empresa y Microsoft Teams.
ms.openlocfilehash: 6cdbdde2c91f8a9a77eb688ae27d509163da42a1
ms.sourcegitcommit: 03e64ead7805f3dfa9149252be8606efe50375df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2019
ms.locfileid: "27769804"
---
# <a name="office-365-advanced-threat-protection"></a>Protección contra amenazas avanzada de Office 365

## <a name="overview"></a>Información general

Protección de amenaza avanzada de Office 365 (ATP) ayuda a proteger su organización frente a ataques malintencionados por:
  
- Análisis de archivos adjuntos de correo electrónico de malware con [Datos adjuntos seguros de ATP](atp-safe-attachments.md)
    
- Análisis web direcciones (URL) en mensajes de correo electrónico y documentos de Office con [Vínculos seguros de ATP](atp-safe-links.md)
    
- Identificación y el bloqueo de archivos malintencionados en las bibliotecas en línea con [ATP para SharePoint, OneDrive y los equipos de Microsoft](atp-for-spo-odb-and-teams.md)
    
- Comprobación de los mensajes de correo electrónico de suplantación de identidad no autorizado con [suplantación de la inteligencia](learn-about-spoof-intelligence.md)
    
- Detectar cuando alguien intenta suplantar a los usuarios y dominios personalizados de la organización con [capacidades de ATP contra suplantación de identidad en Office 365](atp-anti-phishing.md)
    
**Protección a través de Office 365 ATP está determinada por las directivas que define el equipo de seguridad de su organización para vínculos seguros, los datos adjuntos seguros y contra suplantación de identidad**. Es importante revisar periódicamente y revisar las directivas para mantenerlos actualizados y a aprovechar las ventajas de las nuevas características que se agregan al servicio. 

[Los informes están disponibles](view-reports-for-atp.md) para mostrar cómo funciona ATP para su organización. Estos informes también pueden mostrar áreas donde es posible que necesite revisar y actualizar las directivas. Y, si dispone de los archivos que están marcados como malware que no debería ser, o archivos le gustaría que Microsoft para examinar, puede [Enviar un archivo a Microsoft para su análisis](#submit-a-suspicious-file-to-microsoft-for-analysis).

## <a name="new-features-are-continually-being-added-to-atp"></a>Las nuevas características se están agregando continuamente ATP

Para agregar nuevas características a Office 365, estamos siguiendo e incluye ATP. A continuación se presenta una lista de varias características nuevas, algunas de las cuales llamar para que una directiva de ATP ser revisado y actualizado. Para obtener más información acerca de las nuevas características que incide en ATP (o 365 de Microsoft en general), visite la [Guía básica de 365 de Microsoft](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).


|Actualizaciones de características  |Elementos de acción  |
|---------|---------|
|A partir de octubre de 2018 e implantar durante los próximos meses, cuando las personas usan Outlook Web Application (OWA) o Outlook, vínculos seguros de ATP no procesa las direcciones URL originales, volver a escribir las direcciones URL. (Llamamos a esta visibilidad de vínculo nativo).|Ninguno         |
|Principio en septiembre de 2018, la característica de [páginas de advertencia de Office 365 ATP](atp-safe-links-warning-pages.md) una nueva combinación de colores, más detalles y la capacidad para seguir a un sitio a pesar de recibir advertencias y recomendaciones. |Ninguno         |
|A partir de la segunda parte de 2018, protección de vínculos seguros de ATP se ha ampliado para aplicar a las direcciones URL en Office Online (en línea de Word, Excel Online, Online de PowerPoint y OneNote en línea) y Office 365 ProPlus en Mac.   |[Revisar y modificar las directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md)  |
|A partir de las últimas mayo de 2018, capacidades de [cuarentena](quarantine-email-messages.md) en la seguridad &amp; centro de cumplimiento se están extendiendo a [ATP para SharePoint Online, OneDrive para la empresa y los equipos de Microsoft](atp-for-spo-odb-and-teams.md). |[Revisar y modificar las directivas de los datos adjuntos seguros de ATP](set-up-atp-safe-attachments-policies.md) |
|A partir de marzo de 2018, protección de vínculos seguros de ATP se ha ampliado para aplicar a correo electrónico enviado entre personas dentro de una organización. |[Revisar y modificar las directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md) |
|A partir de las últimas de 2017 octubre, protección de vínculos seguros de ATP se ha ampliado para aplicar a las direcciones URL en correo electrónico, así como las direcciones URL en documentos de Office 365 ProPlus, como Word, Excel, PowerPoint y Visio en Windows, así como Office las aplicaciones de iOS y dispositivos Android.  |Asegúrese de que está utilizando [Autenticación moderno para Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) |

      
## <a name="get-office-365-atp"></a>Obtener ATP de Office 365

Office 365 ATP se incluye en las suscripciones, como [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5 y Office 365 educación A5. Si su organización tiene una suscripción a Office 365 que no incluye Office 365 ATP, puede comprar potencialmente ATP como un complemento. Para obtener más información, vea [Office 365 avanzada Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). 

## <a name="define-policies-for-atp"></a>Definir directivas de ATP

- **[Configurar directivas de ATP contra suplantación de identidad en Office 365](set-up-anti-phishing-policies.md)** incluyendo ataques de suplantación en protección contra los intrusos que envían los mensajes de correo electrónico que parecen proceder de personas de confianza o dominios 

- **[Configurar directivas de vínculos seguros de ATP en Office 365](set-up-atp-safe-links-policies.md)** incluidos [lista personalizada de direcciones URL bloqueado](set-up-a-custom-blocked-urls-list-wtih-atp.md) y la [lista de direcciones URL personalizada "No reescritura"](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) de su organización
    
- **[Configurar las directivas de los datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md)** y elija entre varias opciones, como [la entrega dinámica y obtener una vista previa](dynamic-delivery-and-previewing.md)
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a>Vea cómo funciona ATP mediante la visualización de informes

Una vez sus directivas de ATP, están disponibles para mostrar cómo funciona el servicio de informes.

[![La seguridad &amp; panel del centro de cumplimiento puede ayudarle a ver dónde está trabajando avanzada de protección contra amenazas](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)
  
1. Asegúrese de que es un administrador global, Administrador de seguridad o el lector de seguridad de Office 365. (Vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).)
    
2. [Visualización de informes de protección contra amenazas de avanzada](view-reports-for-atp.md).
    
3. Si es necesario, realizar ajustes en las directivas de seguridad. Vea los siguientes recursos:
      - [Directivas de ATP contra suplantación de identidad en Office 365](set-up-anti-phishing-policies.md)
      - [Directivas de vínculos seguros de ATP en Office 365](set-up-atp-safe-links-policies.md)
      - [Directivas de los datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a>Enviar un archivo sospechoso a Microsoft para su análisis

- Si recibe un archivo que cree que podría ser malware, puede enviar ese archivo a Microsoft para su análisis. Visite el [portal de envío de inteligencia de seguridad de Windows Defender](https://go.microsoft.com/fwlink/?linkid=857185).

- Si recibe un mensaje de correo electrónico (con o sin datos adjuntos) que le gustaría usar para enviar a Microsoft para su análisis, use el [complemento en el mensaje de informe](enable-the-report-message-add-in.md). 
  


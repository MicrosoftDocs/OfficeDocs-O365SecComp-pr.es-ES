---
title: Archivado de datos de terceros en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: Los administradores pueden importar datos de terceros desde plataformas de medios sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos a los buzones de la organización de Office 365. Esto le permite archivar datos de Facebook, Twitter y otros orígenes de datos de terceros en Office 365. A continuación, puede usar y aplicar las características de cumplimiento de Office 365 (por ejemplo, retenciones legales, exhibición de documentos electrónicos, archivado local y directivas de retención) para los datos de terceros.
ms.openlocfilehash: 796ad0314374dca60d1ff5f6b9317be491b757a1
ms.sourcegitcommit: f2798d46acfbd56314e809cd3fe0350be807e420
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2019
ms.locfileid: "35014609"
---
# <a name="archive-third-party-data-in-office-365"></a>Archivado de datos de terceros en Office 365

Office 365 permite a los administradores importar y archivar datos de terceros desde plataformas de medios sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos, a los buzones de la organización de Office 365. Entre los ejemplos de orígenes de datos de terceros que puede importar a Office 365 se incluyen los siguientes servicios: 
  
- **Redes sociales** : Facebook, LinkedIn, Twitter y Yammer 
    
- **Mensajería instantánea** : Yahoo Messenger, Googletalk y Cisco Jabber 
    
- **Colaboración en documentos** : Box y Dropbox 
    
- **Sectores verticales** : administración de relaciones con el cliente (como Salesforce chatter) y servicios financieros (como Bloomberg y Thomson Reuters) 
    
- **SMS/mensajería de texto** : BlackBerry 
    
Una vez importados los datos de terceros, puede aplicar las características de cumplimiento de Office 365, como la retención por juicio, el archivado local, la auditoría, la supervisión y las directivas de retención de Office 365, a estos datos. Por ejemplo, cuando un buzón se pone en Retención por juicio, se conservan los datos de terceros. Puede buscar datos de terceros mediante las herramientas de exhibición de documentos electrónicos de Microsoft. También puede aplicar las directivas de archivado y retención a los datos de terceros, del mismo modo que a los datos de Microsoft. En Resumen, el archivado de datos de terceros en Office 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y regulatorias.

Hay dos formas de importar y archivar datos de terceros en Office 365:

- **Use un conector de datos de terceros en el centro de seguridad & cumplimiento** : Use un conector de datos personalizado que esté disponible en el centro de seguridad & cumplimiento en Office 365. Una vez que haya configurado y configurado el conector, se conecta al origen de datos de terceros, convierte el contenido de un elemento a un formato de mensaje de correo electrónico y, a continuación, importa el elemento a un buzón de correo en Office 365. En este momento, puede implementar conectores para importar y archivar datos de páginas empresariales de Facebook, cuentas corporativas de Twitter, Bloomberg instantáneo y LinkedIn. Para obtener instrucciones paso a paso para configurar un conector, consulte:
   
   - **Facebook** : [use un conector de ejemplo para archivar datos de Facebook en Office 365](archive-facebook-data-with-sample-connector.md)
  
   - **Twitter** : [use un conector de ejemplo para archivar datos de Twitter en Office 365](archive-twitter-data-with-sample-connector.md)
    
   - **LinkedIn** : [configurar un conector para archivar datos de LinkedIn en Office 365](archive-linkedin-data.md)

- **Trabajar con un socio de Microsoft** : su organización trabaja con un socio de Microsoft que proporcionará un conector personalizado que se configurará para extraer elementos del origen de datos de terceros (de forma periódica) y, a continuación, conectarse a la nube de Microsoft mediante un API de terceros e importar dichos elementos a Office 365. El conector de asociados también convierte el contenido de un elemento del origen de datos de terceros en un mensaje de correo electrónico y, a continuación, los importa a un buzón en Office 365. Para obtener una lista de los socios con los que puede trabajar y el proceso paso a paso para este método, vea [trabajar con un partner para archivar datos de terceros en Office 365](work-with-partner-to-archive-third-party-data.md).
---
title: Configurar el cifrado en Office 365 Enterprise
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: Con Office 365, algunas capacidades de cifrado están activadas de forma predeterminada; se pueden configurar otras funciones para cumplir ciertos requisitos legales o de cumplimiento normativo.
ms.openlocfilehash: 1bc4ceb7762c96f55c03f89e7c448f9e4073063e
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260798"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Configurar el cifrado en Office 365 Enterprise

El cifrado puede impedir que los usuarios no autorizados lean el contenido. Como el [cifrado en Office 365](encryption.md) puede realizarse con diferentes tecnologías y métodos, no hay un único lugar en el que activar o configurar el cifrado. En este artículo se proporciona información sobre las diversas formas de configurar o configurar el cifrado como parte de la estrategia de protección de la información.
  
> [!TIP]
> Si está buscando más detalles técnicos sobre el cifrado, consulte [información de referencia técnica sobre el cifrado en Office 365](technical-reference-details-about-encryption.md).
  
Con Office 365, hay disponibles varias capacidades de cifrado de forma predeterminada. Se pueden configurar Capacidades de cifrado adicionales para cumplir ciertos requisitos legales o de cumplimiento normativo. En la tabla siguiente se describen varios métodos de cifrado para distintos escenarios.
  
|**Escenario**|**Métodos de cifrado**|
|:-----|:-----|
|Los archivos se guardan en los equipos Windows  <br/> |El cifrado en el nivel de equipo puede realizarse con BitLocker en dispositivos Windows. Como administrador de la empresa o profesional de ti, puede configurarlo mediante el kit de herramientas de implementación de Microsoft (MDT). Consulte [configurar MDT para BitLocker](https://go.microsoft.com/fwlink/?linkid=849282).  <br/> |
|Los archivos se guardan en dispositivos móviles  <br/> |Algunos tipos de dispositivos móviles cifran los archivos que se guardan en esos dispositivos de forma predeterminada. Con las [capacidades de la administración de dispositivos móviles integrada para Office 365](https://support.office.com/article/a1da44e5-7475-4992-be91-9ccec25905b0), puede establecer directivas que determinen si se permitirá que los dispositivos móviles tengan acceso a los datos de Office 365. Por ejemplo, puede establecer una directiva que permita que solo los dispositivos que cifran contenido obtengan acceso a datos de Office 365. Consulte [crear e implementar directivas de seguridad de dispositivos](https://support.office.com/article/d310f556-8bfb-497b-9bd7-fe3c36ea2fd6).  <br/> Para obtener más control sobre cómo interactúan los dispositivos móviles con Office 365, puede considerar la posibilidad de agregar [Microsoft Intune](https://aka.ms/qzln04). Consulte [elegir entre MDM para Office 365 y Microsoft Intune](https://support.office.com/article/c93d9ab9-efb2-4349-9b93-30c30562ee22).  <br/> |
|Necesita controlar las claves de cifrado usadas para cifrar los datos en los centros de datos de Microsoft  <br/> | Como administrador de Office 365, puede controlar las claves de cifrado de su organización y, después, configurar Office 365 para usarlas para cifrar los datos en reposo en los centros de datos de Microsoft.  <br/> [Controlar los datos en Office 365 con la clave de cliente](controlling-your-data-using-customer-key.md) <br/> [Clave del cliente de Office 365 preguntas más frecuentes](service-encryption-with-customer-key-faq.md) <br/> |
|Los usuarios se comunican a través del correo electrónico (Exchange Online)  <br/> | Como administrador de Exchange Online, tiene varias opciones para configurar el cifrado de correo electrónico. Entre ellos se incluyen:  <br/>  Usar el cifrado de [mensajes de Office 365 (OME)](set-up-new-message-encryption-capabilities.md) con Azure Rights Management (Azure RMS) para permitir que los usuarios envíen mensajes cifrados dentro o fuera de la organización  <br/>  Uso [de S/MIME para la firma y el cifrado de mensajes](https://aka.ms/c6dozg) para cifrar y firmar digitalmente los mensajes de correo electrónico  <br/>  Uso de TLS para [configurar conectores para el flujo de correo seguro con otra organización](https://aka.ms/hs809p) <br/>  Consulte [cifrado de correo electrónico en Office 365](https://aka.ms/hic3f7).  <br/> |
|Se obtiene acceso a los archivos desde los sitios de grupo o las bibliotecas de documentos (OneDrive para la empresa o SharePoint Online)  <br/> |Cuando los usuarios trabajan con archivos guardados en OneDrive para la empresa o SharePoint Online, se usan las conexiones TLS. Esto se integra en Office 365 automáticamente. Consulte [cifrado de datos en OneDrive para la empresa y SharePoint Online](https://go.microsoft.com/fwlink/?linkid=526379).  <br/> |
|Los archivos se comparten en reuniones en línea y conversaciones de mensajería instantánea (Skype empresarial online)  <br/> |Cuando los usuarios trabajan con archivos que usan Skype empresarial online, se usa TLS para la conexión. Esto se integra en Office 365 automáticamente. Consulte [seguridad y archivado (Skype empresarial online)](https://aka.ms/nuq4ws).  <br/> |

## <a name="additional-information"></a>Información adicional

Para obtener más información acerca de las soluciones de protección de archivos que incluyen opciones de cifrado, consulte [soluciones de protección de archivos en Office 365](https://www.microsoft.com/en-us/download/details.aspx?id=55523).
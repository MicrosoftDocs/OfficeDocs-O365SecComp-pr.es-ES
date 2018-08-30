---
title: Configurar el cifrado en Office 365 Enterprise
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: Con Office 365, algunas funciones de cifrado están activadas de forma predeterminada; otras funciones pueden configurarse para cumplir determinados requisitos legales o cumplimiento de normas.
ms.openlocfilehash: 80deced80283ac36d82ac15cee9af6d390c4749a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535945"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Configurar el cifrado en Office 365 Enterprise

Cifrado puede proteger el contenido de la que se están leyendo por los usuarios no autorizados. Debido a que el [cifrado en Office 365](encryption.md) puede realizarse mediante varios métodos y tecnologías, no hay un único lugar donde activar o configurar el cifrado. En este artículo se proporciona información acerca de diversas maneras, puede configurar o como parte de una estrategia de protección de la información de configuración del cifrado. 
  
> [!TIP]
> Si desea obtener más detalles técnicos acerca del cifrado, vea [los detalles de referencia técnica acerca del cifrado en Office 365](technical-reference-details-about-encryption.md). 
  
Con Office 365, varias funciones de cifrado están disponibles de forma predeterminada. Las capacidades de cifrado adicional se pueden configurar para cumplir determinados requisitos legales o cumplimiento de normas. En la siguiente tabla se describe varios métodos de cifrado para escenarios diferentes.
  
|**Situación**|**Métodos de cifrado**|
|:-----|:-----|
|Los archivos se guardan en los equipos de Windows  <br/> |Cifrado en el nivel de equipo puede realizarse mediante BitLocker en los dispositivos de Windows. Como un administrador de la empresa o para profesionales de TI, puede configurar esto utilizando Microsoft Deployment Toolkit (MDT). Vea [Set up MDT para BitLocker](https://go.microsoft.com/fwlink/?linkid=849282).<br/> |
|Los archivos se guardan en dispositivos móviles  <br/> |Algunos tipos de dispositivos móviles cifrarán los archivos que se guardan en esos dispositivos de forma predeterminada. Con [las capacidades de administración de dispositivos móviles integrada para Office 365](https://support.office.com/article/a1da44e5-7475-4992-be91-9ccec25905b0), puede establecer las directivas que determinan si se va a permitir que los dispositivos móviles tener acceso a datos en Office 365. Por ejemplo, puede establecer una directiva que permite que sólo los dispositivos que cifrar contenido para tener acceso a datos de Office 365. Vea [crear e implementar directivas de seguridad de dispositivo](https://support.office.com/article/d310f556-8bfb-497b-9bd7-fe3c36ea2fd6).<br/> Para un control adicional sobre los dispositivos móviles cómo interactuar con Office 365, se puede considerar la adición [Intune de Microsoft](https://aka.ms/qzln04). Vea [elegir entre MDM para Office 365 y Microsoft Intune](https://support.office.com/article/c93d9ab9-efb2-4349-9b93-30c30562ee22).<br/> |
|Se necesita control sobre las claves de cifrado que se usa para cifrar los datos en los centros de datos de Microsoft  <br/> | Como administrador de Office 365, puede controlar las claves de cifrado de la organización y, a continuación, configurar Office 365 para usarlos para cifrar los datos en reposo en centros de datos de Microsoft.  <br/> [Controlar los datos en Office 365 con la clave de cliente](controlling-your-data-using-customer-key.md) <br/> [Clave de cliente de preguntas más frecuentes de Office 365](service-encryption-with-customer-key-faq.md) <br/> |
|Las personas se comunican a través de correo electrónico (Exchange Online)  <br/> | Como administrador de Exchange Online, dispone de varias opciones para configurar el correo electrónico cifrado. Entre estos se incluyen:<br/>  Uso de [cifrado de mensajes (OME) de Office 365](set-up-new-message-encryption-capabilities.md) con Azure Rights Management (RMS Azure) para que los usuarios enviar mensajes cifrados dentro o fuera de la organización  <br/>  Uso de [S/MIME para la firma y el cifrado](https://aka.ms/c6dozg) para cifrar y firmar digitalmente mensajes de correo electrónico  <br/>  Uso de TLS para [configurar conectores para el flujo de correo seguro con otra organización](https://aka.ms/hs809p) <br/>  Consulte [cifrado de correo electrónico en Office 365](https://aka.ms/hic3f7).  <br/> |
|Se obtiene acceso a los archivos de los sitios de grupo o las bibliotecas de documentos (OneDrive para la empresa o SharePoint Online)  <br/> |Cuando las personas se trabajan con los archivos guardados a OneDrive para empresa o de SharePoint Online, se usan las conexiones TLS. Esto se basa en Office 365 automáticamente. Vea [el cifrado de datos en OneDrive para empresas y SharePoint Online](https://go.microsoft.com/fwlink/?linkid=526379).<br/> |
|Los archivos se comparten en reuniones en línea y las conversaciones de mensajería instantánea (Skype para profesionales en línea)  <br/> |Cuando las personas se trabajan con archivos con Skype para profesionales en línea, se utiliza TLS para la conexión. Esto se basa en Office 365 automáticamente. Consulte [Security and Archiving (Skype para la empresa en línea)](https://aka.ms/nuq4ws).<br/> |
   
## <a name="additional-information"></a>Información adicional

Para obtener más información acerca de las soluciones de protección de archivos que se incluyen las opciones de cifrado, vea [Soluciones de protección de archivos en Office 365](https://www.microsoft.com/en-us/download/details.aspx?id=55523).
  


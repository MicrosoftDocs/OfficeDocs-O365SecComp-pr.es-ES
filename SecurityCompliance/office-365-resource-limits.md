---
title: Límites de recursos de Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: Información sobre recursos límites para las diferentes aplicaciones de Office 365.'
ms.openlocfilehash: a2e7ef42f9bf224363f3b10a5e450d6127f11585
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536861"
---
# <a name="resource-limits"></a>Límites de recursos

Uso de cuotas (límites) y limitación de peticiones, se aplican los límites de recursos. Azure Active Directory y los servicios de Office 365 individuales utilizan ambos. Los límites son específicos de servicio y cambien a través del tiempo tal y como se agregan nuevas capacidades. Para obtener información detallada acerca de los límites actuales para los distintos servicios, vea los temas siguientes:
- [Restricciones y límites del servicio Active Directory de Azure](https://msdn.microsoft.com/en-us/library/azure/dn764971.aspx)
- [Límites de Exchange Online](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)
- [Límites de Exchange Online Protection](https://technet.microsoft.com/en-us/library/exchange-online-protection-limits.aspx)
- [Límites y límites de software de SharePoint Online](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [Skype para conocer los límites de negocio](https://technet.microsoft.com/en-us/library/skype-for-business-online-limits.aspx)
- [API de REST de yammer y límites de frecuencia](https://developer.yammer.com/docs/rest-api-rate-limits)
- [Límites de tamaño de archivo en balanceo](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

Además de estos límites, se usan varios mecanismos de limitación en Active Directory de Azure y Office 365. Limitación de peticiones dentro del servicio es especialmente importante, dado que los recursos de red en centros de datos de Microsoft están optimizados para el amplio conjunto de clientes que utilizan los servicios. Mecanismos de limitación se incluyen:
- Azure Active Directory y limitación de nivel de usuario del característica de Office 365, lo que limita el número de transacciones o llamadas simultáneas (por secuencia de comandos o código) que se pueden realizar un único usuario.
- Un valor predeterminado PowerShell directiva de limitación se asigna a cada inquilino durante la creación del inquilino. Estas configuraciones afectan a otros elementos, como el número máximo de sesiones simultáneas de PowerShell que puede abrirse con un único administrador.
- Cada cliente de Exchange Online tiene una directiva de Exchange Web Services (EWS) predeterminado que está optimizada para las operaciones de cliente EWS y limitación de peticiones se aplica a todos los clientes de Outlook.

---
title: Cifrado de servicio de Office 365
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
description: 'Resumen: Conozca la resistencia de datos en Microsoft Office 365.'
ms.openlocfilehash: 1273cd5556bf51dcdac9bbde1b3e8003ab818811
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536199"
---
# <a name="office-365-service-encryption"></a>Cifrado de servicio de Office 365

Además de usar el cifrado de nivel de volumen, Exchange Online, Skype para la empresa, SharePoint Online y OneDrive para la empresa también usar servicio de cifrado para cifrar los datos de cliente. Servicio de cifrado permite dos opciones de administración de claves:
- Microsoft administra todas las claves criptográficas. (Esta opción está actualmente disponible en SharePoint Online, OneDrive para la empresa y Skype para la empresa. Se encuentra actualmente en la guía básica para Exchange Online.)
- El cliente proporciona claves raíz se utiliza con cifrado de servicio y el cliente administra estas claves con cámara de clave de Azure. Microsoft administra todas las demás claves. Esta opción se denomina clave de cliente, y está actualmente disponible para Exchange Online, SharePoint Online y OneDrive para la empresa. (Anteriormente denominado cifrado avanzada con BYOK. Vea [mejor transparencia y control para los clientes de Office 365](http://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) para el anuncio original).

Cifrado de servicio ofrece varias ventajas. Por ejemplo, si:
- proporciona características de protección y administración encima de protección de cifrado seguro de derechos.
- incluye una opción de clave de cliente que habilita los servicios de varios inquilinos proporcionar administración de claves por inquilino.
- proporciona la separación de los administradores de sistema operativo de Windows de acceso a datos de clientes almacenados o procesados por el sistema operativo.
- mejora la capacidad de Office 365 para satisfacer las demandas de los clientes que tienen requisitos de cumplimiento de normas referentes al cifrado.

## <a name="customer-key"></a>Clave del cliente
Usar clave de cliente, puede generar sus propio claves criptográficas mediante un HSM local o depósito de clave de Azure. Independientemente de cómo se genera la clave, los clientes usar Azure clave Vault para controlar y administrar las claves de cifrado utilizadas por Office 365. Una vez que las claves se almacenan en Azure clave Vault, puede asignados a las cargas de trabajo, como Exchange Online y SharePoint Online y usa para como la raíz de la cadena de clave que se usa para cifrar los archivos y datos de buzones de correo. Una de las otras ventajas de usar clave de cliente es controlar la capacidad de Microsoft procese los datos del cliente. Esta capacidad existe para que un cliente que desea quitar los datos de Office 365 (por ejemplo, cuando un cliente finaliza el servicio con Microsoft o quita una parte de los datos almacenados en la nube) puede hacerlo y usar clave de cliente como un control técnico para asegurarse de que nadie , incluido Microsoft, puede obtener acceso o procesar los datos. Este es el de adición (y un complemento) a la característica de caja de seguridad del cliente que se puede usar para controlar el acceso a los datos de cliente por el personal de Microsoft.

Para obtener información sobre cómo configurar la clave de cliente para Office 365 para Exchange Online, Skype para la empresa, SharePoint Online y OneDrive para la empresa, vea [controlar los datos de uso de la clave del cliente de Office 365](https://support.office.com/article/Controlling-your-data-in-Office-365-using-Customer-Key-f2cd475a-e592-46cf-80a3-1bfb0fa17697). Para obtener información adicional, vea la [Clave de cliente de preguntas más frecuentes de Office 365](https://support.office.com/article/Customer-Key-for-Office-365-FAQ-41ae293a-bd5c-4083-acd8-e1a2b4329da6)y [administrar y control necesita los datos para ayudar a satisfacer el cumplimiento con clave de cliente](https://techcommunity.microsoft.com/t5/Microsoft-Ignite-Content-2017/Manage-and-control-your-data-to-help-meet-compliance-needs-with/td-p/117580).

---
title: Cifrado de servicio de Office 365
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: comprenda la resistencia de los datos en Microsoft Office 365.'
ms.openlocfilehash: 385bb936de2c0cfcb478f0b20d2f7367d5b55ff4
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262392"
---
# <a name="office-365-service-encryption"></a>Cifrado de servicio de Office 365

Además de usar el cifrado de nivel de volumen, Exchange Online, Skype empresarial, SharePoint Online y OneDrive para la empresa también usan el cifrado de servicio para cifrar los datos de los clientes. El cifrado del servicio permite dos opciones de administración de claves:
- Microsoft administra todas las claves de cifrado. (Esta opción está disponible actualmente en SharePoint Online, OneDrive para la empresa y Skype empresarial. Actualmente se encuentra en el mapa de ruta de Exchange Online).
- El cliente suministra claves raíz que se usan con el cifrado de servicio y el cliente administra estas claves mediante Azure Key Vault. Microsoft administra todas las demás claves. Esta opción se denomina clave de cliente y actualmente está disponible para Exchange Online, SharePoint Online y OneDrive para la empresa. (Anteriormente denominado cifrado avanzado con BYOK. Consulte [mejorar la transparencia y el control para clientes de Office 365](http://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) para el anuncio original).

El cifrado de servicio ofrece varias ventajas. Por ejemplo,:
- proporciona características de protección y administración de derechos sobre la protección de cifrado de alta seguridad.
- incluye una opción de clave de cliente que permite que los servicios multiinquilinos proporcionen administración de claves por espacio empresarial.
- proporciona la separación de los administradores del sistema operativo Windows del acceso a los datos de clientes almacenados o procesados por el sistema operativo.
- mejora la capacidad de Office 365 para satisfacer las demandas de los clientes que tienen requisitos de cumplimiento relacionados con el cifrado.

## <a name="customer-key"></a>Clave del cliente
Mediante el uso de la clave de cliente, puede generar sus propias claves criptográficas mediante el uso de un HSM local o un almacén de claves de Azure. Independientemente de cómo se genere la clave, los clientes usan Azure Key Vault para controlar y administrar las claves criptográficas que usa Office 365. Una vez que las claves se almacenan en Azure Key Vault, se pueden asignar a cargas de trabajo como Exchange Online y SharePoint Online, y usarlas como la raíz de la cadena de claves que se usa para cifrar los archivos y los datos de los buzones.
Una de las otras ventajas de usar la clave de cliente es controlar la capacidad de Microsoft para procesar datos de clientes. Esta capacidad existe para que un cliente que quiera quitar datos de Office 365 (como cuando un cliente termina el servicio con Microsoft o quita una parte de los datos almacenados en la nube) puede hacerlo y usar la clave de cliente como control técnico para asegurarse de que no hay nadie , incluido Microsoft, puede tener acceso a los datos o procesarlos. Esto es adicional (y un complemento) a la característica de caja de caja del cliente que se puede usar para controlar el acceso a los datos de los clientes por parte del personal de Microsoft.

Para obtener información sobre cómo configurar la clave de cliente de Office 365 para Exchange Online, Skype empresarial, SharePoint Online y OneDrive para la empresa, vea [controlar los datos en Office 365 mediante la clave de cliente](https://support.office.com/article/Controlling-your-data-in-Office-365-using-Customer-Key-f2cd475a-e592-46cf-80a3-1bfb0fa17697). Para obtener más información, consulte la [clave de cliente de las preguntas más frecuentes de Office 365](https://support.office.com/article/Customer-Key-for-Office-365-FAQ-41ae293a-bd5c-4083-acd8-e1a2b4329da6)y [administrar y controlar los datos para satisfacer las necesidades de cumplimiento con la clave de cliente](https://techcommunity.microsoft.com/t5/Microsoft-Ignite-Content-2017/Manage-and-control-your-data-to-help-meet-compliance-needs-with/td-p/117580).

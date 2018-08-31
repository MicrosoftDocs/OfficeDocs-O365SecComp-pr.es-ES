---
title: Cifrado de Office 365 en Microsoft Dynamics 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 5/31/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: Conozca el cifrado en Microsoft Dynamics 365.'
ms.openlocfilehash: 181db1724f140c86fb1ac1dbf4a4bfb7063d25a3
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535596"
---
# <a name="office-365-encryption-in-microsoft-dynamics-365"></a>Cifrado de Office 365 en Microsoft Dynamics 365

Microsoft utiliza la tecnología de cifrado para proteger los datos de cliente en Dynamics 365 mientras en reposo en una base de datos de Microsoft y mientras está en tránsito entre los dispositivos de usuario y nuestros centros de datos. Las conexiones establecidas entre los clientes y centros de datos de Microsoft se cifran y todos los extremos públicos se protegen mediante TLS estándar del sector. TLS eficazmente establece una conexión de explorador a servidor con seguridad mejorada para ayudar a garantizar la confidencialidad de los datos y la integridad entre los equipos de sobremesa y centros de datos. Una vez activado el cifrado de datos, no se puede desactivar. Para obtener más información, consulte [cifrado de datos de nivel de campo](https://msdn.microsoft.com/en-us/library/dn481562.aspx).

Dynamics 365 usa el cifrado de nivel de celda de Microsoft SQL Server estándar para un conjunto predeterminado de atributos de entidades que contienen información confidencial, como los nombres de usuario y contraseñas de correo electrónico. Esta característica puede ayudar a las organizaciones a cumplir los requisitos de cumplimiento de normas asociados con FIPS 140-2. Cifrado de datos de nivel de campo es especialmente importante en escenarios que aprovechan el [Enrutador de correo electrónico de Microsoft Dynamics CRM](https://technet.microsoft.com/en-us/library/hh699800.aspx), que debe almacenar los nombres de usuario y contraseñas para habilitar la integración entre una instancia de Dynamics 365 y un servicio de correo electrónico. 

Todas las instancias de Dynamics 365 usan [Cifrado de datos transparente de Microsoft SQL Server](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption?view=sql-server-2017) (TDE) para realizar el cifrado en tiempo real de los datos cuando se escriben en el disco (en reposo). TDE cifra los archivos de datos de SQL Server, la base de datos de SQL Azure y el almacén de datos de SQL Azure. De forma predeterminada, Microsoft almacena y administra las claves de cifrado de la base de datos para las instancias de Dynamics 365. (Las claves que se usan por Dynamics 365 para Finanzas se generan mediante la API de protección de datos de .NET Framework). 

La característica de las claves de administrar en el centro de administración de Dynamics 365 ofrece a los administradores de la capacidad para administrar automáticamente las claves de cifrado de la base de datos que están asociadas a instancias de Dynamics 365. (Las claves de cifrado de administración automática de la base de datos sólo están disponibles en la actualización de enero de 2017 para Microsoft Dynamics 365 y no estar disponibles para las versiones posteriores. Para obtener más información, vea [administrar las claves de cifrado para la instancia (en línea) Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/admin/manage-encryption-keys-instance)). La característica de administración de claves admite PFX y BYOK cifrado archivos de clave, como los almacenados en un HSM. (Para obtener más información acerca de la generación y la transferencia de una clave protegida HSM a través de Internet, vea [cómo generar y transferir claves protegida HSM para Azure clave depósito](https://docs.microsoft.com/azure/key-vault/key-vault-hsm-protected-keys)). 

Para usar la opción de clave de cifrado de carga, necesita tanto la clave de cifrado pública y privada.

La característica de administración de claves tiene la complejidad de administración de claves de cifrado mediante depósito de clave de Azure para almacenar de forma segura las claves de cifrado. Cámara de clave de Azure ayuda a claves criptográficas protegen y secretos utilizados por los servicios y las aplicaciones en la nube. La característica de administración de claves no requiere que tiene una suscripción de Azure clave cámara y para la mayoría de las situaciones, no es necesario para tener acceso a las claves de cifrado utilizadas para Dynamics 365 dentro de la cámara.

---
title: Office 365 cifrado en Microsoft Dynamics 365
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: comprenda el cifrado en Microsoft Dynamics 365.'
ms.openlocfilehash: faf9df09b8dcd8a76a38671e4f5d5145094eec88
ms.sourcegitcommit: 24659bdb09f49d0ffed180a4b80bbb7c45c2d301
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2019
ms.locfileid: "29664076"
---
# <a name="office-365-encryption-in-microsoft-dynamics-365"></a>Office 365 cifrado en Microsoft Dynamics 365

Microsoft usa la tecnología de cifrado para proteger los datos de los clientes en Dynamics 365 mientras está en reposo en una base de datos de Microsoft y mientras está en tránsito entre los dispositivos de usuario y nuestros centros de datos. Las conexiones establecidas entre los clientes y los centros de usuarios de Microsoft están cifradas, y todos los puntos de conexión públicos se protegen con TLS estándar del sector. TLS establece efectivamente una conexión de explorador a servidor de seguridad mejorada para garantizar la confidencialidad y la integridad de los datos entre los equipos de escritorio y los centros de datos. Una vez activado el cifrado de datos, no se puede desactivar. Para obtener más información, consulte [cifrado de datos en el nivel de campo](https://msdn.microsoft.com/en-us/library/dn481562.aspx).

Dynamics 365 usa el cifrado de nivel de celda estándar de Microsoft SQL Server para un conjunto de atributos de entidad predeterminados que contienen información confidencial, como nombres de usuario y contraseñas de correo electrónico. Esta característica puede ayudar a las organizaciones a cumplir los requisitos de cumplimiento asociados con FIPS 140-2. El cifrado de datos en el nivel de campo es especialmente importante en los escenarios que aprovechan el [Microsoft Dynamics CRM email router](https://technet.microsoft.com/en-us/library/hh699800.aspx), que deben almacenar los nombres de usuario y las contraseñas para habilitar la integración entre una instancia de Dynamics 365 y un servicio de correo electrónico. 

Todas las instancias de Dynamics 365 usan el cifrado de datos transparente (TDE) de [Microsoft SQL Server](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption?view=sql-server-2017) para realizar el cifrado de datos en tiempo real cuando se escriben en el disco (en reposo). TDE cifra SQL Server, Azure SQL Database y los archivos de datos de Azure SQL Data Warehouse. De forma predeterminada, Microsoft almacena y administra las claves de cifrado de base de datos para las instancias de Dynamics 365. (Las claves que usan Dynamics 365 para operaciones financieras se generan mediante la API de protección de datos de .NET Framework.) 

La característica administrar claves del centro de administración de Dynamics 365 ofrece a los administradores la capacidad de administrar automáticamente las claves de cifrado de base de datos que están asociadas con instancias de Dynamics 365. (Las claves de cifrado de base de datos autoadministradas solo están disponibles en la actualización de enero de 2017 para Microsoft Dynamics 365 y pueden no estar disponibles para versiones posteriores. Para obtener más información, consulte [administrar las claves de cifrado para la instancia de Dynamics 365 (en línea)](https://docs.microsoft.com/dynamics365/customer-engagement/admin/manage-encryption-keys-instance)). La característica de administración de claves admite archivos de claves de cifrado de PFX y BYOK, como los que se almacenan en un HSM. (Para obtener más información acerca de cómo generar y transferir una clave protegida por HSM a través de Internet, consulte [How to generaTE HSM-Protected Keys for Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-hsm-protected-keys)). 

Para usar la opción cargar clave de cifrado, necesita tanto la clave de cifrado pública como la privada.

La característica de administración de claves elimina la complejidad de la administración de claves de cifrado al usar Azure Key Vault para almacenar las claves de cifrado de forma segura. Azure Key Vault ayuda a proteger las claves criptográficas y los secretos que usan las aplicaciones y los servicios en la nube. La característica de administración de claves no requiere que tenga una suscripción de Azure Key Vault y, en la mayoría de las situaciones, no es necesario tener acceso a las claves de cifrado usadas para Dynamics 365 en el almacén.

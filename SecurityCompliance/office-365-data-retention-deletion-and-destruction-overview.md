---
title: Retención, eliminación y destrucción de datos en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Información general sobre las directivas de Microsoft para Office 365 relacionadas con la retención, eliminación y destrucción de datos.
ms.openlocfilehash: 6aa272ece723aa83e15581062fd2348c508b04d5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219960"
---
# <a name="data-retention-deletion-and-destruction-in-office-365"></a>Retención, eliminación y destrucción de datos en Office 365

Microsoft tiene una directiva estándar de tratamiento de datos para Office 365 que especifica cuánto tiempo se conservarán los datos de los clientes después de eliminarlos. Normalmente, hay dos escenarios en los que se eliminan los datos de los clientes:

- **Eliminación activa** : el inquilino tiene una suscripción activa y un usuario elimina datos, o bien el administrador elimina los datos proporcionados por un usuario.
- **Eliminación pasiva** : finaliza la suscripción de inquilino.

## <a name="data-retention"></a>Retención de datos

Para cada uno de estos escenarios de eliminación, en la tabla siguiente se muestra el período de retención de datos máximo, por categoría de datos y clasificación:

| Categoría de datos | Clasificación de datos | Descripción | Ejemplos | Período de retención |
|-----------------|-----------------|-----------------|----------------------------------|-------------------------------|
| Datos de cliente | Contenido del cliente| Contenido proporcionado directamente/creado por administradores y usuarios <br><br> Esto incluye todo el texto, sonido, vídeo, archivos de imagen y software creado y almacenado en centros de datos de Microsoft cuando se usan los servicios de Office 365 | Algunos ejemplos de las aplicaciones de Office 365 más usadas que permiten a los usuarios crear datos son Word, Excel, PowerPoint, Outlook y OneNote <br><br> El contenido del cliente también incluye secretos de propiedad del cliente o proporcionados (contraseñas, certificados, claves de cifrado, claves de almacenamiento) | **Escenario de eliminación activa:** como máximo 30 días <br><br> **Escenario de eliminación pasiva:** como máximo 180 días |
| Datos de cliente | Información de identificación del usuario final (EUII) | Datos que identifican o pueden usarse para identificar al usuario de un servicio de Microsoft. EUII no incluye contenido del cliente | Nombre de usuario o nombre para mostrar (Dominio\nombre de usuario) <br><br> Nombre principal de usuario (nombre @ dominio) <br><br>  Direcciones IP específicas del usuario | **Escenario de eliminación activa:** como máximo de 180 días (solo una acción de administrador de inquilinos) <br><br> **Escenario de eliminación pasiva:** como máximo 180 días |
| Datos personales <br> (datos no incluidos en los datos del cliente) | Identificadores de seudónimos de usuario final (EUPI) | Identificador creado por Microsoft ligado al usuario de un servicio de Microsoft. Cuando EUPI se combina con otra información, como una tabla de asignación, identifica al usuario final. <br><br> EUPI no contiene información que el cliente ha cargado o creado | GUID de usuario, PUIDs o SID <br><br> Identificadores de sesión | **Escenario de eliminación activa:** como máximo 30 días <br><br> **Escenario de eliminación pasiva:** como máximo 180 días |

## <a name="subscription-retention"></a>Retención de suscripción

En todo momento durante el período de una suscripción activa, un suscriptor puede obtener acceso, extraer o eliminar los datos de los clientes almacenados en Office 365. Si una suscripción de pago finaliza o finaliza, Microsoft conservará los datos de los clientes almacenados en Office 365 en una cuenta de funciones limitadas durante 90 días para permitir que el suscriptor Extraiga los datos. Una vez finalizado el período de retención de 90 días, Microsoft deshabilitará la cuenta y eliminará los datos del cliente. No más de 180 días tras la expiración o cancelación de una suscripción a Office 365, Microsoft deshabilitará la cuenta y eliminará todos los datos de los clientes de la cuenta. Una vez que ha transcurrido el período de retención máximo de los datos, los datos se representan comercialmente no recuperables.

En el caso de una prueba gratuita, su cuenta pasará a un estado de gracia durante 30 días en la mayoría de países y regiones. Durante este período de gracia, tiene la opción de comprar Office 365. Si decide no comprar Office 365, puede cancelar la versión de prueba o dejar que expire el período de gracia y se eliminarán los datos y la información de la cuenta de prueba.

## <a name="expedited-deletion"></a>Eliminación urgente
En todo momento, durante el período de una suscripción, un suscriptor puede ponerse en contacto con el soporte técnico de Microsoft y solicitar la anulación de la suscripción de la suscripción. En este proceso, todos los datos de usuario, incluidos los datos de SharePoint Online, Exchange online que pueden estar en retención o almacenados en buzones inactivos, se eliminan tres días después de que el administrador escriba el código de bloqueo proporcionado por Microsoft. Para obtener más información sobre la anulación de aprovisionamiento urgente, vea [Cancelar Office 365](https://support.office.com/article/Cancel-Office-365-for-business-b1bc0bef-4608-4601-813a-cdd9f746709a).

## <a name="related-links"></a>Vínculos relacionados
- [Destrucción de datos](office-365-data-destruction.md)
- [Inmutabilidad en Office 365](office-365-data-immutability.md)
- [Eliminación de datos en Exchange Online](office-365-exchange-online-data-deletion.md)
- [Eliminación de datos en SharePoint Online](office-365-sharepoint-online-data-deletion.md)
- [Eliminación de datos en Skype Empresarial](office-365-skype-data-deletion.md)
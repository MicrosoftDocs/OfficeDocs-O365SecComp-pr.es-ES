---
title: Retención, eliminación y destrucción de datos en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Información general sobre las directivas de Microsoft para Office 365 relativas a la retención, eliminación y destrucción de datos.
ms.openlocfilehash: 79a58381892cfcb773f6e83f129075d6f2037304
ms.sourcegitcommit: aa60a6cdf83c67576e858668d1182cd4fffeb5e0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "33622490"
---
# <a name="data-retention-deletion-and-destruction-in-office-365"></a>Retención, eliminación y destrucción de datos en Office 365

Microsoft tiene una directiva estándar de tratamiento de datos para Office 365 que especifica cuánto tiempo se conservan los datos de los clientes tras la eliminación. Normalmente, hay dos escenarios en los que se eliminan los datos de los clientes:

- **Eliminación activa:** El inquilino tiene una suscripción activa y un usuario elimina datos o los administradores eliminan los datos proporcionados por un usuario.
- **Eliminación pasiva:** Finaliza la suscripción de inquilino.

## <a name="data-retention"></a>Retención de datos

Para cada uno de estos escenarios de eliminación, en la tabla siguiente se muestra el período de retención de datos máximo, por categoría de datos y clasificación:

| Categoría de datos | Clasificación de datos | Descripción | Ejemplos | Período de retención |
|-----------------|-----------------|-----------------|----------------------------------|-------------------------------|
| Datos de cliente | Contenido del cliente| Contenido proporcionado directamente/creado por administradores y usuarios <br><br> Incluye todo el texto, sonido, vídeo, archivos de imagen y software creado y almacenado en centros de datos de Microsoft cuando se usan los servicios de Office 365 | Algunos ejemplos de las aplicaciones de Office 365 más usadas que permiten a los usuarios crear datos son Word, Excel, PowerPoint, Outlook y OneNote <br><br> El contenido del cliente también incluye secretos de propiedad del cliente o proporcionados (contraseñas, certificados, claves de cifrado, claves de almacenamiento) | **Escenario de eliminación activa:** como máximo 30 días <br><br> **Escenario de eliminación pasiva:** como máximo 180 días |
| Datos de cliente | Información de identificación del usuario final (EUII) | Datos que identifican o pueden usarse para identificar al usuario de un servicio de Microsoft. EUII no incluye contenido del cliente | Nombre de usuario o nombre para mostrar (Dominio\nombre de usuario) <br><br> Nombre principal de usuario (nombre @ dominio) <br><br>  Direcciones IP específicas del usuario | **Escenario de eliminación activa:** como máximo de 180 días (solo una acción de administrador de inquilinos) <br><br> **Escenario de eliminación pasiva:** como máximo 180 días |
| Datos personales <br> (datos no incluidos en los datos del cliente) | Identificadores de seudónimos de usuario final (EUPI) | Identificador creado por Microsoft ligado al usuario de un servicio de Microsoft. Cuando se combina con otra información, como una tabla de asignación, EUPI identifica al usuario final <br><br> EUPI no contiene información que el cliente ha cargado o creado | GUID de usuario, PUIDs o SID <br><br> Identificadores de sesión | **Escenario de eliminación activa:** como máximo 30 días <br><br> **Escenario de eliminación pasiva:** como máximo 180 días |

## <a name="subscription-retention"></a>Retención de suscripción

En el término de una suscripción activa, un suscriptor puede obtener acceso, extraer o eliminar los datos de los clientes almacenados en Office 365. Si una suscripción de pago finaliza o se termina, Microsoft conserva los datos del cliente almacenados en Office 365 en una cuenta de funciones limitadas durante 90 días para permitir que el suscriptor Extraiga los datos. Una vez finalizado el período de retención de 90 días, Microsoft deshabilita la cuenta y elimina los datos del cliente. No más de 180 días tras la expiración o cancelación de una suscripción a Office 365, Microsoft deshabilita la cuenta y elimina todos los datos del cliente de la cuenta. Una vez que ha transcurrido el período de retención máximo de los datos, los datos se representan comercialmente no recuperables.

Para una prueba gratuita, la cuenta pasa a un estado de gracia durante 30 días en la mayoría de países y regiones. Durante este período de gracia, puede comprar Office 365. Si decide no comprar Office 365, puede cancelar la versión de prueba o dejar que expire el período de gracia y se elimine la información y los datos de la cuenta de prueba.

## <a name="expedited-deletion"></a>Eliminación urgente

Para cualquier suscripción, un suscriptor puede ponerse en contacto con el soporte técnico de Microsoft y solicitar el aprovisionamiento de suscripciones urgentes. En este proceso, todos los datos de usuario se eliminan tres días después de que el administrador escriba el código de bloqueo proporcionado por Microsoft. Esto incluye datos en SharePoint Online y Exchange Online suspendidos o almacenados en buzones inactivos.

Para obtener más información acerca de la deshabilitación de aprovisionamiento rápido, consulte [Cancelar Office 365](https://support.office.com/article/Cancel-Office-365-for-business-b1bc0bef-4608-4601-813a-cdd9f746709a).

## <a name="related-links"></a>Vínculos relacionados
- [Destrucción de datos](office-365-data-destruction.md)
- [Inmutabilidad en Office 365](office-365-data-immutability.md)
- [Eliminación de datos en Exchange Online](office-365-exchange-online-data-deletion.md)
- [Eliminación de datos en SharePoint Online](office-365-sharepoint-online-data-deletion.md)
- [Eliminación de datos en Skype Empresarial](office-365-skype-data-deletion.md)
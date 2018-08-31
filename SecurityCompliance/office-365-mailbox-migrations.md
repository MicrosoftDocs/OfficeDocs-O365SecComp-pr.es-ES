---
title: Migraciones de buzones de Office 365
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
description: Un breve resumen de los cmdlets usados para las migraciones de buzón de correo de Office 365.
ms.openlocfilehash: 86896d956072b5c11e3b3292363bb32312ff1187
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536450"
---
# <a name="office-365-mailbox-migrations"></a>Migraciones de buzones de Office 365
Con una implementación híbrida basada en Exchange, los clientes pueden elegir mover los buzones de Exchange local a una organización de [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) o mover buzones de Exchange Online a una organización de [Exchange local](https://docs.microsoft.com/Exchange/exchange-server) . Lotes de migración se utilizan cuando mueva buzones entre organizaciones de Exchange Online y local. Los clientes pueden revisar estadísticas y otra información acerca de las migraciones de buzones de correo con los siguientes cmdlets:

- [Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps) - proporciona las estadísticas predeterminadas de un buzón de usuario, que incluye el estado, el tamaño del buzón, archivar el tamaño del buzón y completar de porcentaje.
- [Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
) - proporciona una lista resumida de los atributos de la organización y objetos de buzón de correo.
- [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps) - proporciona una lista de los objetos existentes, como los buzones de correo, los usuarios de correo, contactos y grupos de distribución habilitados para correo.
- [Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps) - proporciona un estado detallado de una migración de buzones.
- [Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps) - proporciona información acerca del buzón de movimiento y migración de los usuarios.
- [Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps) - proporciona información sobre el estado actual del lote de migración.
- [Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps) - proporciona información detallada sobre el estado de la migración para un usuario específico.
- [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps) - proporciona información acerca de los buzones de correo, como el tamaño, el número de mensajes y el acceso por última vez.

Para obtener más información sobre los cmdlets adicionales, vea [cmdlets de movimiento y migración en Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).

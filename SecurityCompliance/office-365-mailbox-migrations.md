---
title: Migraciones de buzones de Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Un breve resumen de los cmdlets que se usan para las migraciones de buzones de Office 365.
ms.openlocfilehash: 8e0f23a3efbbcf6f84364c09e667678972120e18
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219150"
---
# <a name="office-365-mailbox-migrations"></a>Migraciones de buzones de Office 365
Con una implementación híbrida basada en Exchange, los clientes pueden elegir entre mover buzones de Exchange locales a una organización de [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) o mover buzones de correo de Exchange Online a una organización [local de Exchange](https://docs.microsoft.com/Exchange/exchange-server) . Los lotes de migración se usan cuando se mueven buzones de correo entre organizaciones locales y de Exchange Online. Los clientes pueden revisar las estadísticas y otra información sobre las migraciones de buzones de correo con los siguientes cmdlets:

- [Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps) : proporciona estadísticas predeterminadas para un buzón de usuario, que incluye el estado, el tamaño del buzón, el tamaño del buzón de archivo y el porcentaje completado.
- [Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
) -proporciona una lista resumida de los objetos de buzón y los atributos de la organización.
- [Get-recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps) : proporciona una lista de objetos existentes habilitados para correo, como buzones de correo, usuarios de correo, contactos y grupos de distribución.
- [Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps) : proporciona un estado detallado de una migración de buzones de correo en curso.
- [Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps) : proporciona información sobre los usuarios de migración y movimiento de buzones.
- [Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps) : proporciona información sobre el estado del lote de migración actual.
- [Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps) : proporciona información detallada sobre el estado de la migración de un usuario específico.
- [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps) : proporciona información acerca de los buzones de correo, como el tamaño, el número de mensajes y la hora del último acceso.

Para obtener más información acerca de los cmdlets adicionales, vea [Move and Migration cmdlets in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).

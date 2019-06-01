---
title: Atributos para directivas de barrera de información
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/31/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Use este artículo como referencia para los diversos atributos que puede usar en las directivas de barrera de información.
ms.openlocfilehash: e72e37950442974897de479c7c11f0053a578d1c
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668344"
---
# <a name="attributes-for-information-barrier-policies-preview"></a>Atributos de las directivas de barrera de información (vista previa)

Algunos atributos de Azure Active Directory pueden usarse para segmentar usuarios. A continuación, los segmentos se usan como filtros para las directivas de barrera de información. Por ejemplo, puede usar **Department** para definir segmentos de usuarios por departamento dentro de la organización (suponiendo que no hay empleados que trabajen en dos departamentos al mismo tiempo). 

En este artículo se proporciona una lista de atributos que se pueden usar. Para obtener más información acerca de las barreras de información, vea los siguientes recursos:
- [Barreras de la información (versión preliminar)](information-barriers.md)
- [Definir directivas para las barreras de información en Microsoft Teams (versión preliminar)](information-barriers-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>Cómo usar atributos en las directivas de barrera de información

Los atributos que se enumeran en este artículo pueden usarse para definir (o editar) segmentos de usuarios. Los segmentos se usan como parámetros (UserGroupFilter) en las directivas de barrera de información, como se muestra en los siguientes ejemplos:

|Ejemplo  |Cmdlet  |
|---------|---------|
|Definir un segmento denominado Segment1 con el atributo Department     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
|Defina un segmento denominado segmenta mediante el atributo memberOf (suponga que este atributo contiene nombres de grupo, como "BlueGroup")     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
|Definir un segmento denominado DayTraders mediante ExtensionAttribute1 (suponga que este atributo contiene cargos, como "DayTrader")|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

Al definir segmentos, use el mismo atributo para todos los segmentos. Por ejemplo, si define algunos segmentos usando *Departamento*, defina todos los segmentos mediante *Departamento*. No defina algunos segmentos con *Department* y otros con *memberOf*. Asegúrese de que los segmentos no se superponen; cada usuario debe asignarse exactamente a un segmento. 

Para obtener más información, vea [definir segmentos con PowerShell](information-barriers-policies.md#define-segments-using-powershell).

## <a name="reference"></a>Referencia

En la tabla siguiente se enumeran los atributos que puede usar con barreras de la información.

|Nombre de propiedad de Azure Active Directory (nombre para mostrar LDAP)  |Nombre de la propiedad de Exchange  |
|---------|---------|
|Patrocina       | Patrocina        |
|Company     |Company         |
|Departamento     |Departamento         |
|ExtensionAttribute1 |CustomAttribute1  |
|ExtensionAttribute2 |CustomAttribute2  |
|ExtensionAttribute3 |CustomAttribute3  |
|ExtensionAttribute4 |CustomAttribute4  |
|ExtensionAttribute5 |CustomAttribute5  |
|ExtensionAttribute6 |CustomAttribute6  |
|ExtensionAttribute7 |CustomAttribute7  |
|ExtensionAttribute8 |CustomAttribute8  |
|ExtensionAttribute9 |CustomAttribute9  |
|ExtensionAttribute10 |CustomAttribute10  |
|ExtensionAttribute11 |CustomAttribute11  |
|ExtensionAttribute12 |CustomAttribute12  |
|ExtensionAttribute13 |CustomAttribute13  |
|ExtensionAttribute14 |CustomAttribute14  |
|ExtensionAttribute15 |CustomAttribute15  |
|MSExchExtensionCustomAttribute1 |ExtensionCustomAttribute1 |
|MSExchExtensionCustomAttribute2 |ExtensionCustomAttribute2 |
|MSExchExtensionCustomAttribute3 |ExtensionCustomAttribute3 |
|MSExchExtensionCustomAttribute4 |ExtensionCustomAttribute4 |
|MSExchExtensionCustomAttribute5 |ExtensionCustomAttribute5 |
|MailNickname |Alias |
|PhysicalDeliveryOfficeName |Office |
|PostalCode |PostalCode |
|ProxyAddresses |EmailAddresses |
|StreetAddress |StreetAddress |
|TargetAddress |ExternalEmailAddress |
|UsageLocation |UsageLocation |
|UserPrincipalName  |UserPrincipalName  |
|Correo   |WindowsEmailAddress    |
|Descripción    |Descripción    |
|MemberOf   |MemberOfGroup  |

## <a name="related-topics"></a>Temas relacionados

[Definir directivas para las barreras de información en Microsoft Teams (versión preliminar)](information-barriers-policies.md)

[Solución de problemas de las barreras de la información (versión preliminar)](information-barriers-troubleshooting.md)

[Barreras de la información (versión preliminar)](information-barriers.md)




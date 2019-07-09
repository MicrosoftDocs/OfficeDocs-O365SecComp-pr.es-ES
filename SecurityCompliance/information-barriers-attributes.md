---
title: Atributos para directivas de barrera de información
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Use este artículo como referencia para los diversos atributos que puede usar en las directivas de barrera de información.
ms.openlocfilehash: 1e2e183da350308a57fa5d627b4867b9b3d30cee
ms.sourcegitcommit: a6f046f1529b0515f4f0e918a19ec83f4138b871
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2019
ms.locfileid: "35587069"
---
# <a name="attributes-for-information-barrier-policies"></a>Atributos para directivas de barrera de información

Algunos atributos de Azure Active Directory pueden usarse para segmentar usuarios. Una vez que se han definido los segmentos, estos segmentos se pueden usar como filtros para las directivas de barrera de información. Por ejemplo, puede usar **Department** para definir segmentos de usuarios por departamento dentro de la organización (suponiendo que no hay empleados que trabajen en dos departamentos al mismo tiempo). 

En este artículo se describe cómo usar atributos con barreras de información y se proporciona una lista de atributos que se pueden usar. Para obtener más información acerca de las barreras de información, vea los siguientes recursos:
- [Barreras de la información](information-barriers.md)
- [Definir directivas para las barreras de información en Microsoft Teams](information-barriers-policies.md)
- [Editar (o quitar) directivas de barrera de información](information-barriers-edit-segments-policies.md.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>Cómo usar atributos en las directivas de barrera de información

Los atributos que se enumeran en este artículo pueden usarse para definir o editar segmentos de usuarios. Los segmentos definidos actúan como parámetros (denominados valores *UserGroupFilter* ) en [las directivas de barrera de información](information-barriers-policies.md).

1. Determine qué atributo desea usar para definir segmentos. (Consulte la sección [referencia](#reference) de este artículo).

2. Asegúrese de que las cuentas de usuario tengan valores rellenados para los atributos que seleccionó en el paso 1. Ver los detalles de la cuenta de usuario y, si es necesario, editar cuentas de usuario para incluir valores de atributo. 

    - Para editar varias cuentas (o usar PowerShell para editar una sola cuenta), vea [Configure User Account Properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).

    - Para editar una sola cuenta, vea [Agregar o actualizar la información de Perfil de un usuario con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

3. [Defina segmentos con PowerShell](information-barriers-policies.md#define-segments-using-powershell), de manera similar a los siguientes ejemplos:

    |Ejemplo  |Cmdlet  |
    |---------|---------|
    |Definir un segmento denominado Segment1 con el atributo Department     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
    |Defina un segmento denominado segmenta mediante el atributo memberOf (suponga que este atributo contiene nombres de grupo, como "BlueGroup")     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
    |Definir un segmento denominado DayTraders mediante ExtensionAttribute1 (suponga que este atributo contiene cargos, como "DayTrader")|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > Al definir segmentos, use el mismo atributo para todos los segmentos. Por ejemplo, si define algunos segmentos usando *Departamento*, defina todos los segmentos mediante *Departamento*. No defina algunos segmentos con *Department* y otros con *memberOf*. Asegúrese de que los segmentos no se superponen; cada usuario debe asignarse exactamente a un segmento. 

## <a name="reference"></a>Referencia

En la tabla siguiente se enumeran los atributos que puede usar con barreras de la información.

|Nombre de propiedad de Azure Active Directory<br/>(Nombre para mostrar LDAP)  |Nombre de la propiedad de Exchange  |
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

[Definir directivas para las barreras de información en Microsoft Teams](information-barriers-policies.md)

[Solución de problemas de obstáculos para la información](information-barriers-troubleshooting.md)

[Barreras de la información](information-barriers.md)




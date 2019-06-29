---
title: Editar directivas de barrera de información
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Obtenga información sobre cómo editar o quitar directivas para las barreras de información.
ms.openlocfilehash: c3dca18ad217b89d9f9ae78b590cfb07f4631f37
ms.sourcegitcommit: 011bfa60cafdf47900aadf96a17eb275efa877c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394335"
---
# <a name="edit-or-remove-information-barrier-policies-preview"></a>Edición (o eliminación) de directivas de barrera de información (versión preliminar)

Una vez que haya [definido las directivas de barrera de información](information-barriers-policies.md), es posible que deba realizar cambios en dichas directivas o en sus segmentos de usuario, como parte de la solución de [problemas](information-barriers-troubleshooting.md) o del mantenimiento regular. Use este artículo como guía.

## <a name="what-do-you-want-to-do"></a>¿Qué quiere hacer?

|Acción  |Descripción |
|---------|---------|
|[Editar atributos de cuenta de usuario](#edit-user-account-attributes)     |Rellene los atributos de Azure Active Directory que se pueden usar para definir segmentos.<br/>Edite los atributos de la cuenta de usuario cuando los usuarios no están incluidos en los segmentos que deben ser, para cambiar los segmentos en los que están los usuarios o para definir segmentos con atributos diferentes.         |
|[Edición de un segmento](#edit-a-segment)     |Modifique segmentos cuando desee cambiar la forma en que se define un segmento. <br/>Por ejemplo, puede que haya definido originalmente segmentos con el *Departamento* y ahora desee usar otro atributo, como *memberOf*.         |
|[Editar una directiva](#edit-a-policy)     |Edite una directiva de barrera de información cuando desee cambiar el funcionamiento de una directiva.<br/>Por ejemplo, en lugar de bloquear las comunicaciones entre dos segmentos, es posible que decida que desea permitir que las comunicaciones se produzcan solo entre determinados segmentos.         |
|[Definir un estado inactivo de una directiva](#set-a-policy-to-inactive-status)     |Establezca un estado inactivo para una Directiva cuando desee realizar cambios en una directiva o cuando no desee que una directiva esté en vigor.         |
|[Quitar una directiva](#remove-a-policy)     |Quite una directiva de barrera de información cuando ya no necesite una Directiva concreta en su ubicación.         |
|[Detención de una aplicación de Directiva](#stop-a-policy-application)     |Haga esto cuando quiera detener el proceso de aplicación de directivas de barrera de información.<br/>Tenga en cuenta que la detención de una aplicación de Directiva no es instantánea y no deshace las directivas que ya se han aplicado a los usuarios.         |
|[Definir directivas para las barreras de información (vista previa)](information-barriers-policies.md)     |Defina una directiva de barrera de información cuando no tenga ya dichas directivas y deba restringir o limitar las comunicaciones entre grupos de usuarios específicos.         |
|[Solución de problemas de las barreras de la información (versión preliminar)](information-barriers-troubleshooting.md)     |Consulte este artículo cuando surgen problemas inesperados con barreras de información.         |

> [!IMPORTANT]
> Para llevar a cabo las tareas descritas en este artículo, debe tener asignada una función adecuada, como una de las siguientes:<br/>-Administrador global de Microsoft 365 Enterprise<br/>-Office 365 administrador global<br/>-Administrador de cumplimiento<br/>-IB Compliance Management (este es un nuevo rol).<p>Para obtener más información sobre los requisitos previos para las barreras de información, vea [requisitos previos (para las directivas de barrera de información)](information-barriers-policies.md#prerequisites).<p>Asegúrese de [conectarse a PowerShell del centro de seguridad & cumplimiento de Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

## <a name="edit-user-account-attributes"></a>Editar atributos de cuenta de usuario

Use este procedimiento para editar los atributos que se usan para segmentar usuarios. 

Por ejemplo, si está usando un atributo de departamento y una o más cuentas de usuario no tienen actualmente ningún valor en la lista de departamento, debe editar esas cuentas de usuario para incluir la información del Departamento. 

Los atributos de cuenta de usuario se usan para definir segmentos para que se puedan asignar directivas de barrera de información.

1. Para ver los detalles de una cuenta de usuario específica, como los valores de atributo y los segmentos asignados, use el cmdlet **Get-InformationBarrierRecipientStatus** con parámetros Identity. 

    |Sintaxis  |Ejemplo  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>   Puede usar cualquier valor que identifique de forma exclusiva a cada usuario, como el nombre, el alias, el nombre distintivo, el nombre de dominio canónico, la dirección de correo electrónico o el GUID. <p>   (También puede usar este cmdlet para un solo usuario: `Get-InformationBarrierRecipientStatus -Identity <value>`)      |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`  <p>   En este ejemplo, se hace referencia a dos cuentas de usuario en Office 365: *meganb* para *Nuria*y *alexw* para *Alex*.         |

2. Determine qué atributo desea editar para los perfiles de cuenta de usuario. Consulte [atributos para las directivas de barrera de información (vista previa)](information-barriers-attributes.md) para obtener más información. 

3. Edite una o más cuentas de usuario para incluir valores para el atributo que seleccionó en el paso anterior. Para ello, use uno de los procedimientos siguientes:

    - Para editar una sola cuenta, vea [Agregar o actualizar la información de Perfil de un usuario con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

    - Para editar varias cuentas (o usar PowerShell para editar una sola cuenta), vea [Configure User Account Properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).

## <a name="edit-a-segment"></a>Edición de un segmento

Use este procedimiento para editar la definición de un segmento de usuario. Por ejemplo, puede cambiar el nombre de un segmento o el filtro que se usa para determinar quién está incluido en el segmento.

1. Para ver todos los segmentos existentes, use el cmdlet **Get-OrganizationSegment** .
    
    Consta`Get-OrganizationSegment`

    Verá una lista de segmentos y detalles para cada uno, como tipo de segmento, su valor UserGroupFilter, que lo creó o modificó por última vez, GUID, etc.

    > [!TIP]
    > Imprime o guarda la lista de segmentos para hacer referencia a ellos más adelante. Por ejemplo, si desea editar un segmento, necesitará conocer su nombre o identificar el valor (que se usa con el parámetro Identity).

2. Para editar un segmento, use el cmdlet **set-OrganizationSegment** con el parámetro **Identity** y los detalles pertinentes. 

    |Sintaxis  |Ejemplo  |
    |---------|---------|
    |`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`     |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p>En este ejemplo, para el segmento que tiene el GUID *c96e0837-c232-4a8a-841E-ef45787d8fcd*, se actualizó el nombre del Departamento a "HRDept".         |

Una vez finalizada la edición de segmentos de la organización, puede [definir](information-barriers-policies.md#part-2-define-information-barrier-policies) o [Editar](#edit-a-policy) las directivas de barrera de información.

## <a name="edit-a-policy"></a>Editar una directiva

1. Para ver una lista de las directivas de barrera de información actuales, use el cmdlet **Get-InformationBarrierPolicy** .

    Consta`Get-InformationBarrierPolicy`

    En la lista de resultados, identifique la Directiva que desea cambiar. Anote el GUID y el nombre de la Directiva.

2. Use el cmdlet **set-InformationBarrierPolicy** con un parámetro **Identity** y especifique los cambios que desea realizar.

    Ejemplo: Supongamos que se ha definido una directiva para bloquear el segmento de *investigación* para que no pueda comunicarse con los segmentos de *ventas* y *marketing* . La Directiva se definió mediante este cmdlet:`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`
    
    Supongamos que queremos cambiarla para que las personas del segmento de *investigación* solo puedan comunicarse con los usuarios del segmento de *recursos humanos* . Para realizar este cambio, usamos este cmdlet:`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    En este ejemplo, hemos cambiado "SegmentsBlocked" por "SegmentsAllowed" y hemos especificado el segmento de *recursos humanos* .

3. Cuando termine de editar una directiva, asegúrese de aplicar los cambios. (Consulte [aplicar directivas de barrera de información](information-barriers-policies.md#part-3-apply-information-barrier-policies)).

## <a name="set-a-policy-to-inactive-status"></a>Definir un estado inactivo de una directiva

1. Para ver una lista de las directivas de barrera de información actuales, use el cmdlet **Get-InformationBarrierPolicy** .

    Consta`Get-InformationBarrierPolicy`

    En la lista de resultados, identifique la Directiva que desea cambiar (o quitar). Anote el GUID y el nombre de la Directiva.

2. Para establecer el estado de la Directiva como inactivo, use el cmdlet **set-InformationBarrierPolicy** con un parámetro Identity y el parámetro State establecido en INACTIVE.

    |Sintaxis  |Ejemplo  |
    |---------|---------|
    |`Set-InformationBarrierPolicy -Identity GUID -State Inactive`     |`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p>En este ejemplo, se establece una directiva de barrera de información que tiene un GUID *43c37853-ea10-4b90-a23d-ab8c9377247* en un estado inactivo.         |

3. Para aplicar los cambios, use el cmdlet **Start-InformationBarrierPoliciesApplication** .

    Consta`Start-InformationBarrierPoliciesApplication`

    Se aplican los cambios, usuario por usuario, para la organización. Si su organización es grande, puede tardar 24 horas (o más) en completarse este proceso. (Como regla general, tarda aproximadamente una hora en procesar las cuentas de usuario de 5.000).

En este punto, se establecen una o varias directivas de barrera de información en estado inactivo. Desde aquí, puede realizar una de las siguientes acciones:
- Mantenlo tal cual (el estado de una directiva establecida en inactivo no tiene efecto sobre los usuarios)
- [Editar una directiva](#edit-a-policy) 
- [Quitar una directiva](#remove-a-policy)

## <a name="remove-a-policy"></a>Quitar una directiva

1. Para ver una lista de las directivas de barrera de información actuales, use el cmdlet **Get-InformationBarrierPolicy** .

    Consta`Get-InformationBarrierPolicy`

    En la lista de resultados, identifique la Directiva que desea quitar. Anote el GUID y el nombre de la Directiva. Asegúrese de que la Directiva está establecida en estado inactivo.

2. Use el cmdlet **Remove-InformationBarrierPolicy** con un parámetro Identity.

    |Sintaxis  |Ejemplo  |
    |---------|---------|
    |`Remove-InformationBarrierPolicy -Identity GUID`     |`Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p>En este ejemplo, se quita la Directiva que tiene el GUID *43c37853-ea10-4b90-a23d-ab8c93772471*.          |

    Cuando se le pida, confirme el cambio.

3. Repita los pasos 1-2 para cada directiva que desee quitar.

4. Cuando haya terminado de quitar directivas, aplique los cambios. Para ello, use el cmdlet **Start-InformationBarrierPoliciesApplication** .

    Consta`Start-InformationBarrierPoliciesApplication`

    Se aplican los cambios, usuario por usuario, para la organización. Si su organización es grande, puede tardar 24 horas (o más) en completarse este proceso.

## <a name="stop-a-policy-application"></a>Detención de una aplicación de Directiva

Si, después de empezar a aplicar directivas de barrera de información, desea detener la aplicación de estas directivas, use el siguiente procedimiento. Tenga en cuenta que el proceso tardará aproximadamente 30-35 minutos en comenzar.

1. Para ver el estado de la aplicación de directiva de barrera de información más reciente, use el cmdlet **Get-InformationBarrierPoliciesApplicationStatus** .

    Consta`Get-InformationBarrierPoliciesApplicationStatus`

    Anote el GUID de la aplicación.

2. Use el cmdlet **Stop-InformationBarrierPoliciesApplication** con un parámetro Identity.

    |Sintaxis  |Ejemplo  |
    |---------|---------|
    |`Stop-InformationBarrierPoliciesApplication -Identity GUID`     |`Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p>En este ejemplo, estamos deteniendo que se apliquen las directivas de barrera de información.         |

## <a name="related-articles"></a>Artículos relacionados

[Obtener información general sobre las barreras de la información](information-barriers.md)

[Definir directivas para las barreras de información (vista previa)](information-barriers-policies.md)

[Obtenga más información sobre las barreras de la información en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[Atributos de las directivas de barrera de información (vista previa)](information-barriers-attributes.md)

[Solución de problemas de las barreras de la información (versión preliminar)](information-barriers-troubleshooting.md)

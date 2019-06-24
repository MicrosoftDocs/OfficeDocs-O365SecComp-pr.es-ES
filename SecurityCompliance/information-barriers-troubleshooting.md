---
title: Solución de problemas de obstáculos para la información
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/21/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Use este artículo como guía para solucionar problemas con las barreras de la información.
ms.openlocfilehash: b88f97cd872d4ea3b95bfac049f47cd71dfb2cb2
ms.sourcegitcommit: c603a07d24c4c764bdcf13f9354b3b4b7a76f656
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2019
ms.locfileid: "35131354"
---
# <a name="troubleshooting-information-barriers-preview"></a>Solución de problemas de las barreras de la información (versión preliminar)

Las barreras de la [información (versión preliminar)](information-barriers.md) pueden ayudar a su organización a permanecer conforme con los requisitos legales y las regulaciones del sector. Por ejemplo, con barreras de información, puede restringir la comunicación entre grupos de usuarios específicos para evitar un conflicto de intereses u otros problemas. (Para obtener más información sobre cómo configurar las barreras de la información, vea [definir directivas para las barreras de información (vista previa)](information-barriers-policies.md)).

En el caso de que los usuarios se encuentren en problemas inesperados después de que entren en vigor las barreras de la información, hay algunos pasos que puede seguir para resolverlos. Use este artículo como guía.


## <a name="before-you-begin"></a>Antes de comenzar...

Para llevar a cabo las tareas descritas en este artículo, debe tener asignada una función adecuada, como una de las siguientes:
- Administrador global de Microsoft 365 Enterprise
- Administrador global de Office 365
- Administrador de cumplimiento
- IB Compliance Management (este es un nuevo rol)

Para obtener más información sobre los requisitos previos para las barreras de información, vea [requisitos previos (para las directivas de barrera de información)](information-barriers-policies.md#prerequisites).

Asegúrese de [conectarse a PowerShell del centro de seguridad & cumplimiento de Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

## <a name="issue-communications-are-still-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>Problema: las comunicaciones todavía se permiten entre los usuarios que deben estar bloqueados en Microsoft Teams

En este caso, a pesar de que las barreras de la información están definidas, activas y aplicadas, los usuarios a los que se les debe impedir comunicarse entre sí todavía pueden hacerlo en Microsoft Teams.

### <a name="what-to-do"></a>Qué hacer

Compruebe que los usuarios en cuestión se incluyen en una directiva de barrera de información. Use el cmdlet **Get-InformationBarrierRecipientStatus** con parámetros Identity.

Consta`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` 

Puede usar cualquier valor que identifique de forma exclusiva a cada usuario, como el nombre, el alias, el nombre distintivo, el nombre de dominio canónico, la dirección de correo electrónico o el GUID. 

Ejemplo: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` 

En este ejemplo, se hace referencia a dos cuentas de usuario en Office 365: *meganb* para *Nuria*y *alexw* para *Alex*. 

(También puede usar este cmdlet para un solo usuario: `Get-InformationBarrierRecipientStatus -Identity <value>`) este cmdlet devuelve información sobre los usuarios, como los valores de atributo y las directivas de barrera de información que se aplican.


|Resultados  |Pasos siguientes  |
|---------|---------|
|No se enumeran segmentos para el usuario o usuarios seleccionados     |Realice una de las acciones siguientes:<br/>-Asignar usuarios a un segmento existente editando sus perfiles de usuario en Azure Active Directory<br/>-Definir un segmento mediante un [atributo compatible con barreras de información](information-barriers-attributes.md)         |
|Se enumeran los segmentos pero no se asigna ninguna directiva de barrera de información a dichos segmentos.     |Realice una de las acciones siguientes:<br/>- [Definir una directiva de barrera de información](information-barriers-policies.md#part-2-define-information-barrier-policies) para cada segmento en cuestión<br/>- [Editar una directiva de barrera de información](information-barriers-policies.md#edit-a-policy) y asignarla al segmento correcto         |
|Se enumeran los segmentos y cada uno de ellos se incluye en una directiva de barrera de información     |-Ejecute el `Get-InformationBarrierPolicy` cmdlet para comprobar que las directivas de barrera de información están activas<br/>-Ejecute el `Get-InformationBarrierPoliciesApplicationStatus` cmdlet para confirmar que se aplican las directivas.<br/>-Ejecute el `Start-InformationBarrierPoliciesApplication` cmdlet para aplicar todas las directivas activas de barrera de información          |


## <a name="issue-people-are-unexpectedly-blocked-from-communicating-in-microsoft-teams"></a>Problema: se impide que los usuarios se comuniquen de forma inesperada en Microsoft Teams 

En este caso, los usuarios están notificando problemas inesperados que se comunican en Microsoft Teams. Ejemplos:
- Un usuario no puede encontrar o comunicarse con otro usuario en Microsoft Teams.
- Un usuario no puede ver ni seleccionar A otro usuario en Microsoft Teams.
- Un usuario puede ver a otro usuario, pero no puede seleccionar ni enviar mensajes a ese otro usuario en Microsoft Teams.

### <a name="what-to-do"></a>Qué hacer

1. Determinar si los usuarios están afectados por una directiva de barrera de información. Para ello, use el cmdlet **Get-InformationBarrierRecipientStatus** con el parámetro Identity. 

    La sintaxis es`Get-InformationBarrierRecipientStatus -Identity`

    Puede usar cualquier valor de identidad que identifique de forma exclusiva a cada destinatario, como el nombre, el alias, el nombre distintivo (DN), el DN canónico, la dirección de correo electrónico o el GUID.

    Ejemplo: `Get-InformationBarrierRecipientStatus -Identity meganb`

    En este ejemplo, se usa un alias (*meganb*) para el parámetro Identity. Este cmdlet devolverá información que indica si el usuario está afectado por una directiva de barrera de información. (Busque * ExoPolicyId: \<guid>).

    Si los usuarios no se incluyen en las directivas de barrera de información, póngase en contacto con el soporte técnico. En caso contrario, continúe con el paso siguiente.

2. Averigüe qué segmentos se incluyen en una directiva de barrera de información. Para ello, use el `Get-InformationBarrierPolicy` cmdlet con el parámetro Identity. Use los detalles, como el GUID de directiva (ExoPolicyId) que ha recibido durante el paso anterior, como un valor de identidad.

    Ejemplo: `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f`

    En este ejemplo, se obtiene información detallada sobre la Directiva de barrera de información que tiene ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*.
    
    Después de ejecutar el cmdlet, en los resultados, busque los valores de **AssignedSegment**, **SegmentsAllowed**y **SegmentsBlocked** .

    Ejemplo: después de ejecutar `Get-InformationBarrierPolicy` el cmdlet, vimos lo siguiente en nuestra lista de resultados:

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    En este caso, podemos ver que una directiva de barrera de información afecta a las personas que están en los segmentos de ventas y de investigación. En este caso, se impide que las personas de ventas se comuniquen con personas en investigación. Si esto parece correcto, las barreras de la información funcionan como se esperaba. Si no es así, continúe con el paso siguiente.

4. Asegúrese de que los segmentos se han definido correctamente. Para ello, use el `Get-OrganizationSegment` cmdlet y revise la lista de resultados. 

    Para ver los detalles de un segmento específico, use `Get-OrganizationSegment` el cmdlet con un parámetro Identity. 

    Ejemplo: `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd`

    En este ejemplo, se obtiene información acerca del segmento que tiene el GUID *c96e0837-c232-4a8a-841E-ef45787d8fcd*.

    Revise los detalles del segmento. Si es necesario, [edite un segmento](information-barriers-policies.md#edit-a-segment)y, a continuación, `Start-InformationBarrierPoliciesApplication` vuelva a usar el cmdlet.

    Si sigue teniendo problemas con la Directiva de barrera de información, póngase en contacto con el soporte técnico.
    
## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>Problema: el proceso de aplicación de la barrera de información está tardando mucho

Después de ejecutar el cmdlet **Start-InformationBarrierPoliciesApplication** , el proceso toma un tiempo muy largo para finalizar.

### <a name="what-to-do"></a>Qué hacer

Tenga en cuenta que, al ejecutar el cmdlet de aplicación de Directiva, se aplican (o quitan) directivas de barrera de información, usuario por usuario, para todas las cuentas de la organización. Si tiene muchos usuarios, tardará un rato en procesarse. (Como regla general, tarda aproximadamente una hora en procesar las cuentas de usuario de 5.000).

1. Use el cmdlet **Get-InformationBarrierPoliciesApplicationStatus** para comprobar el estado de la aplicación de directivas más reciente.

    Consta`Get-InformationBarrierPoliciesApplicationStatus`

    (Para mostrar el estado de *todas* las aplicaciones de directiva de barrera de información, use este cmdlet:<br/>
    `Get-InformationBarrierPoliciesApplicationStatus -All $true`)

    Esto mostrará información sobre si la aplicación de la Directiva se completó, produjo un error o está en curso.

2. Según los resultados del paso anterior, realice uno de los siguientes pasos:
  
    |Estado  |Siguiente paso  |
    |---------|---------|
    |**No iniciado**     |Si ha transcurrido más de 45 minutos desde que se ejecutó el cmdlet **Start-InformationBarrierPoliciesApplication** , revise el registro de auditoría para ver si hay errores en las definiciones de directiva o alguna otra razón por la que la aplicación no se ha iniciado. |
    |**Failed**     |Si se ha producido un error en la aplicación, revise el registro de auditoría. Revise también sus segmentos y directivas. ¿Hay algún usuario asignado a más de un segmento? ¿Hay algún segmento asignado a más de un poliicy? Si es necesario, [modifique los segmentos](information-barriers-policies.md#edit-a-segment) o [edite las directivas](information-barriers-policies.md#edit-a-policy)y, a continuación, vuelva a ejecutar el cmdlet **Start-InformationBarrierPoliciesApplication** .  |
    |**En curso**     |Si la aplicación sigue en curso, permita más tiempo para completarse. Si ha transcurrido varios días, reúna los registros de auditoría y, a continuación, póngase en contacto con el soporte técnico. |

## <a name="related-topics"></a>Temas relacionados

[Definir directivas para las barreras de información en Microsoft Teams (versión preliminar)](information-barriers-policies.md)

[Barreras de la información (versión preliminar)](information-barriers.md)




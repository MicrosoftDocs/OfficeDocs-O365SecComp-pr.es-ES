---
title: Solución de problemas de obstáculos para la información
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
description: Use este artículo como guía para solucionar problemas con las barreras de la información.
ms.openlocfilehash: b37585469ec8bb299b7976f8a330f4c6b29e3f95
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668341"
---
# <a name="troubleshooting-information-barriers-preview"></a>Solución de problemas de las barreras de la información (versión preliminar)

Las barreras de información pueden ayudar a su organización a permanecer conforme con los requisitos legales y las regulaciones del sector. Por ejemplo, con barreras de información, puede restringir la comunicación entre grupos de usuarios específicos para evitar un conflicto de intereses u otros problemas. Para obtener más información, consulte barreras de la [información (vista previa)](information-barriers.md).

En este artículo se proporcionan instrucciones que puede usar para obtener respuestas a preguntas o resolver problemas que pueden surgir debido a las barreras de la información.  

## <a name="before-you-begin"></a>Antes de comenzar...

Para llevar a cabo las tareas descritas en este artículo, debe tener asignada una función adecuada, como una de las siguientes:
- Administrador global de Microsoft 365 Enterprise
- Administrador global de Office 365
- Administrador de cumplimiento
- IB Compliance Management (este es un nuevo rol)

Para obtener más información acerca de los roles y los permisos, consulte Permissions [in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

Para obtener más información sobre los requisitos previos para las barreras de información, vea [requisitos previos (para las directivas de barrera de información)](information-barriers-policies.md#prerequisites).

Además, asegúrese de [conectarse a PowerShell del centro de seguridad & cumplimiento de Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

## <a name="issue-people-are-unexpectedly-blocked-from-communicating-in-microsoft-teams"></a>Problema: se impide que los usuarios se comuniquen de forma inesperada en Microsoft Teams 

En este caso, los usuarios están notificando problemas inesperados que se comunican en Microsoft Teams. Ejemplos:
- Un usuario no puede encontrar o comunicarse con otro usuario en Microsoft Teams.
- Un usuario no puede ver ni seleccionar A otro usuario en Microsoft Teams.
- Un usuario puede ver, pero no puede enviar mensajes a otro usuario en Microsoft Teams.

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

1. Tenga en cuenta que, al ejecutar el cmdlet de aplicación de Directiva, se aplican (o quitan) directivas de barrera de información, usuario por usuario, para todas las cuentas de la organización. Si tiene muchos usuarios, tardará un rato en procesarse. (Como regla general, tarda aproximadamente una hora en procesar las cuentas de usuario de 5.000). 

2. Use el cmdlet **Get-InformationBarrierPoliciesApplicationStatus** para comprobar el estado.

    Consta`Get-InformationBarrierPoliciesApplicationStatus`

    Para mostrar el estado de todas las aplicaciones de directiva de barrera de información, use`Get-InformationBarrierPoliciesApplicationStatus -All $true`

    Esto mostrará información sobre si la aplicación de la Directiva se completó, produjo un error o está en curso.

3. Según los resultados del paso 2, realice uno de los siguientes pasos:

    - Si la aplicación no se ha iniciado y ha transcurrido más de 45 minutos desde que se ejecutó el cmdlet **Start-InformationBarrierPoliciesApplication** , revise el registro de auditoría para ver si hay errores en las definiciones de directiva o algún otro motivo por el que el la aplicación no se ha iniciado.

    - Si se ha producido un error en la aplicación, revise los segmentos y las directivas. Si es necesario, [modifique los segmentos](information-barriers-policies.md#edit-a-segment) o [edite las directivas](information-barriers-policies.md#edit-a-policy)y, a continuación, vuelva a ejecutar el cmdlet **Start-InformationBarrierPoliciesApplication** .

    - Si la aplicación sigue en curso, permita más tiempo para completarse. Si ha sido varios días, póngase en contacto con el soporte técnico.

## <a name="related-topics"></a>Temas relacionados

[Definir directivas para las barreras de información en Microsoft Teams (versión preliminar)](information-barriers-policies.md)

[Barreras de la información (versión preliminar)](information-barriers.md)




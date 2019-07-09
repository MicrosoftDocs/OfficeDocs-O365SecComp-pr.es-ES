---
title: Definir directivas de barrera de información
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
description: Obtenga información sobre cómo definir directivas para las barreras de la información en Microsoft Teams.
ms.openlocfilehash: 527f059eb0bccb97429c649d055496c06710c2a9
ms.sourcegitcommit: a6f046f1529b0515f4f0e918a19ec83f4138b871
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2019
ms.locfileid: "35587089"
---
# <a name="define-policies-for-information-barriers"></a>Definir políticas para las barreras de la información

## <a name="overview"></a>Información general

Con las barreras de la información, puede definir directivas diseñadas para evitar que determinados segmentos de usuarios se comuniquen entre sí o permitir que segmentos específicos solo se comuniquen con determinados segmentos. Las directivas de barrera de información pueden ayudar a su organización a mantener el cumplimiento de las normas y regulaciones de la industria pertinentes y evitar posibles conflictos de intereses. Para obtener más información, consulte barreras de la [información](information-barriers.md). 

En este artículo se describe cómo planear, definir, implementar y administrar directivas de barrera de información. Hay varios pasos implicados y el flujo de trabajo se divide en varias partes. Asegúrese de leer los [requisitos previos](#prerequisites) y el proceso completo antes de empezar a definir (o editar) directivas de barrera de información.

> [!TIP]
> En este artículo se incluye un [escenario de ejemplo](#example-contosos-departments-segments-and-policies) y un libro de [Excel](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx) descargable para ayudarle a planear y definir las directivas de barrera de información.

## <a name="concepts-of-information-barrier-policies"></a>Conceptos de las directivas de barrera de información

Al definir directivas para barreras de información, trabajará con los atributos de la cuenta de usuario, los segmentos, las directivas "bloquear" o "permitir" y la aplicación de directivas.

- **Los atributos** de la cuenta de usuario se definen en Azure Active Directory (o Exchange Online). Estos atributos pueden incluir Departamento, puesto, ubicación, nombre del equipo y otros detalles del perfil del trabajo. 

- Los **segmentos** son conjuntos de usuarios que se definen en el centro de seguridad & cumplimiento de Office 365 con un **atributo de cuenta de usuario**seleccionado. (Consulte la [lista de atributos admitidos](information-barriers-attributes.md)). 

- **Las directivas de barrera de información** determinan límites de comunicación o restricciones. Al definir directivas de barrera de información, puede elegir entre dos tipos de directivas:
    - Las directivas "bloquear" impiden que un segmento se comunique con otro segmento.
    - Las directivas "permitir" permiten que un segmento se comunique con determinados otros segmentos.

- La **aplicación de directivas** se realiza una vez que se han definido todas las directivas de barrera de información y está listo para aplicarlas a la organización.

## <a name="the-work-flow-at-a-glance"></a>El flujo de trabajo de un vistazo

|Fase    |Qué implica  |
|---------|---------|
|[Asegurarse de que se cumplen los requisitos previos](#prerequisites)     |-Compruebe que tiene las [licencias y permisos necesarios](information-barriers.md#required-licenses-and-permissions)<br/>-Compruebe que el directorio incluye datos para segmentar usuarios<br/>-Habilitar la búsqueda de directorio en el ámbito de Microsoft Teams<br/>-Asegúrese de que el registro de auditoría esté activado<br/>-Asegúrese de que no hay directivas de libreta de direcciones de Exchange en su ubicación<br/>-Usar PowerShell (se proporcionan ejemplos)<br/>-Proporcionar consentimiento de administrador para Microsoft Teams (se incluyen los pasos)          |
|[Parte 1: segmentar usuarios en la organización](#part-1-segment-users)     |-Determine qué directivas se necesitan<br/>-Hacer una lista de segmentos para definir<br/>-Identificación de los atributos que se van a usar<br/>-Definir segmentos en términos de filtros de Directiva        |
|[Parte 2: definir las directivas de la barrera de información](#part-2-define-information-barrier-policies)     |-Definir las directivas (no aplicar todavía)<br/>-Elegir entre dos tipos (bloquear o permitir) |
|[Parte 3: aplicar directivas de barrera de información](#part-3-apply-information-barrier-policies)     |-Establecer directivas en el estado activo<br/>-Ejecutar la aplicación de la Directiva<br/>-Ver estado de la Directiva         |
|(Según sea necesario) [Edición de un segmento o una directiva](information-barriers-edit-segments-policies.md.md)    |-Editar un segmento<br/>-Editar o quitar una directiva<br/>-Volver a ejecutar la aplicación de Directiva<br/>-Ver estado de la Directiva         |
|(Según sea necesario) [Solución de problemas](information-barriers-troubleshooting.md)|-Realizar una acción cuando las cosas no funcionan como se esperaba|

## <a name="prerequisites"></a>Requisitos previos

Además de las [licencias y permisos necesarios](information-barriers.md#required-licenses-and-permissions), asegúrese de que se cumplen los siguientes requisitos: 
     
- **Datos del directorio**. Asegúrese de que la estructura de la organización se refleja en los datos del directorio. Para ello, asegúrese de que los atributos de la cuenta de usuario, como la pertenencia a grupos, el nombre del Departamento, etc., se rellenan correctamente en Azure Active Directory (o Exchange Online). Para obtener más información, vea los siguientes recursos:
  - [Atributos para directivas de barrera de información](information-barriers-attributes.md)
  - [Agregar o actualizar la información de Perfil de un usuario con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [Configurar las propiedades de la cuenta de usuario con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)

- **Búsqueda de directorio**en el ámbito. Antes de definir la Directiva de barrera de la primera información de su organización, debe [Habilitar la búsqueda de directorios de ámbito en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search). Espere al menos 24 horas después de habilitar la búsqueda de directorios de ámbito antes de configurar o definir directivas de barrera de información.

- **Registro de auditoría**. Para buscar el estado de una aplicación de Directiva, el registro de auditoría debe estar activado. Le recomendamos hacer esto antes de empezar a definir segmentos o directivas. Para obtener más información, consulte [activar o desactivar la búsqueda de registros de auditoría de Office 365](turn-audit-log-search-on-or-off.md).

- **No hay directivas de libreta de direcciones**. Antes de definir y aplicar directivas de barrera de información, asegúrese de que no hay directivas de libreta de direcciones de Exchange en su ubicación. (Las barreras de información se basan en las directivas de la libreta de direcciones, pero los dos tipos de directivas no son intercambiables). Si tiene estas directivas, asegúrese de [quitar las directivas de la libreta de direcciones](https://docs.microsoft.com/exchange/address-books/address-book-policies/remove-an-address-book-policy) en primer lugar.

- **PowerShell**. Actualmente, las directivas de barrera de información se definen y administran en el centro de cumplimiento de & de seguridad de Office 365 con cmdlets de PowerShell. Aunque se proporcionan varios ejemplos en este artículo, deberá estar familiarizado con los cmdlets y los parámetros de PowerShell. También necesitará el módulo AzureRM.
    - [Conectarse a PowerShell del Centro de seguridad y cumplimiento de Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)
    - [Instalar el módulo de Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-2.3.2)

- **Consentimiento del administrador para las barreras de la información en Microsoft Teams**. Cuando las directivas están en su lugar, las barreras de la información pueden quitar a las personas de las sesiones de chat en las que no se supone que se encuentren. Esto ayuda a garantizar que su organización siga cumpliendo con las directivas y las regulaciones. Use el siguiente procedimiento para habilitar las directivas de barrera de información para que funcionen según lo previsto en Microsoft Teams. 

   1. Ejecute los siguientes cmdlets de PowerShell:

      ```
      Login-AzureRmAccount 
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzureRmADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzureRmADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   2. Cuando se le solicite, inicie sesión con su cuenta profesional o educativa para Office 365.

   3. En el cuadro de diálogo **permisos solicitados** , revise la información y, a continuación, elija **Aceptar**.

Cuando se cumplan todos los requisitos previos, continúe con la siguiente sección.

> [!TIP]
> Para ayudarle a preparar su plan, en este artículo se incluye un escenario de ejemplo. [Consulte departamentos, segmentos y directivas de Contoso](#example-contosos-departments-segments-and-policies).<p>Además, hay disponible un libro de Excel descargable para ayudarle a planear y definir los segmentos y las directivas (y a crear los cmdlets de PowerShell). [Obtener el libro](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx). 

## <a name="part-1-segment-users"></a>Parte 1: segmentar usuarios

Durante esta fase, debe determinar qué directivas de barrera de información son necesarias, realizar una lista de segmentos para definirlos y, a continuación, definir los segmentos.

### <a name="determine-what-policies-are-needed"></a>Determinación de las directivas necesarias

¿Está teniendo en cuenta las regulaciones legales y de la industria, que son los grupos dentro de la organización que necesitarán directivas de barrera de información? Crear una lista. ¿Hay algún grupo que deba impedir la comunicación con otro grupo? ¿Hay grupos a los que se debe permitir comunicarse solo con uno o dos grupos? Piense en las directivas que necesita como perteneciente a uno de estos dos grupos:
- Las directivas "bloquear" impiden que un grupo se comunique con otro grupo.
- Las directivas "permitir" permiten a un grupo comunicarse solo con determinados grupos específicos.

Cuando tenga la lista inicial de grupos y directivas, continúe para identificar los segmentos que necesitará. 

### <a name="identify-segments"></a>Identificación de segmentos

Además de la lista inicial de directivas, haga una lista de los segmentos de su organización. Los usuarios que se incluirán en las directivas de barrera de información deben pertenecer a un segmento y ningún usuario debe pertenecer a dos o más segmentos. Cada segmento solo puede tener una directiva de barrera de información aplicada. 

Determine qué atributos de los datos del directorio de la organización va a usar para definir los segmentos. Puede usar *Department*, *memberOf*o cualquiera de los atributos admitidos. Asegúrese de que tiene valores en el atributo que ha seleccionado para los usuarios. [Vea la lista de atributos admitidos para las barreras de información](information-barriers-attributes.md).

> [!IMPORTANT]
> **Antes de continuar con la siguiente sección, asegúrese de que los datos del directorio tengan valores para atributos que puede usar para definir segmentos**. Si los datos del directorio no tienen valores para los atributos que desea usar, las cuentas de usuario deben actualizarse para incluir esta información antes de continuar con las barreras de la información. Para obtener ayuda, vea los siguientes recursos:<br/>- [Configurar las propiedades de la cuenta de usuario con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)<br/>- [Agregar o actualizar la información de Perfil de un usuario con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>Definir segmentos con PowerShell

La definición de segmentos no afecta a los usuarios; solo establece la etapa de las directivas de barrera de información que se van a definir y aplicar.

1. Use el cmdlet **New-OrganizationSegment** con el parámetro **UserGroupFilter** que corresponda al [atributo](information-barriers-attributes.md) que desee usar.

    |Sintaxis   |Ejemplo  |
    |---------|---------|
    |`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`     |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>En este ejemplo, un segmento denominado *HR* se define con *HR*, un valor en el atributo *Department* . La parte del cmdlet **-EQ** hace referencia a "es igual a". (Alternativamente, puede usar **-ne** para que signifique "no es igual a". Consulte [uso de "igual" y "no es igual a" en definiciones de segmentos](#using-equals-and-not-equals-in-segment-definitions).)        |

    Después de ejecutar cada cmdlet, debe ver una lista de detalles sobre el nuevo segmento. Los detalles incluyen el tipo de segmento, quién lo creó o modificó por última vez, etc. 

2. Repita este proceso para cada segmento que desee definir.

    > [!IMPORTANT]
    > Asegúrese de **que los segmentos no**se superponen. Cada usuario que se verá afectado por obstáculos en cuanto a la información debe pertenecer a un único segmento (y solo uno). Ningún usuario debe pertenecer a dos o más segmentos. (Vea [ejemplo: segmentos definidos por contoso](#contosos-defined-segments) en este artículo).


Una vez que haya definido los segmentos, continúe con la [definición de las directivas de barrera de información](#part-2-define-information-barrier-policies).

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>Usar "igual" y "no es igual" en definiciones de segmentos

En el siguiente ejemplo, se define un segmento para que "Department Equals HR". 

|Ejemplo  |
|---------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>Observe que en este ejemplo, la definición de segmento incluye un parámetro "equivale a" denotado como **-EQ**. 
  |

También puede definir segmentos con el parámetro "no es igual a", que se indica como **-ne**, como se muestra en la siguiente tabla:

|Sintaxis  |Ejemplo  |
|---------|---------|
|`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -ne 'attributevalue'"`    |`New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"` <p>En este ejemplo, se ha definido un segmento denominado *NotSales* que incluye a todos los usuarios que no están en *ventas*. La parte **-ne** del cmdlet hace referencia a "no es igual a".  |

Además de definir los segmentos con "igual" o "no es igual a", puede definir un segmento con los parámetros "igual" y "no es igual a".

|Ejemplo  |
|---------|
|`New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" and "Position -ne 'Temporary'"` <p>En este ejemplo, se ha definido un segmento denominado *LocalFTE* que incluye personas que se encuentran de forma local y cuyas posiciones no aparecen como *temporales*.    |

> [!TIP]
> Si es posible, use definiciones de segmento que incluyan "-EQ" o "-NE". Intente no definir definiciones de segmentos complejos. 

## <a name="part-2-define-information-barrier-policies"></a>Parte 2: definir las directivas de la barrera de información

Determine si necesita impedir las comunicaciones entre determinados segmentos o limitar las comunicaciones a determinados segmentos. Lo ideal es que use el número mínimo de directivas para asegurarse de que su organización cumple con los requisitos legales y del sector.

Con la lista de segmentos de usuario y las directivas de barrera de información que desea definir, seleccione un escenario y, a continuación, siga los pasos. 

- [Escenario 1: bloquear las comunicaciones entre segmentos](#scenario-1-block-communications-between-segments)
- [Escenario 2: permitir que un segmento se comunique solo con otro segmento](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> Asegúrese de **que, al definir las directivas, no asigne más de una directiva a un segmento**. Por ejemplo, si define una directiva para un segmento denominado *ventas*, no defina una directiva adicional para *ventas*.<p>Además, al definir las directivas de barrera de información, asegúrese de establecer las directivas en estado inactivo hasta que esté listo para aplicarlas. Las directivas de definición (o edición) no afectan a los usuarios hasta que esas directivas se establecen en estado activo y, a continuación, se aplican.

(Vea [ejemplo: directivas de la barrera de información de Contoso](#contosos-information-barrier-policies) en este artículo).

### <a name="scenario-1-block-communications-between-segments"></a>Escenario 1: bloquear las comunicaciones entre segmentos

Cuando desee bloquear a los segmentos para que no se comuniquen entre sí, defina dos directivas: una para cada dirección. Cada directiva bloquea la comunicación solo de una forma.

Por ejemplo, supongamos que desea bloquear las comunicaciones entre el segmento A y el segmento B. En este caso, se define una directiva que impide que el segmento A se comunique con el segmento B y, a continuación, se define una segunda Directiva para evitar que el segmento B se comunique con el segmento A.

1. Para definir la primera Directiva de bloqueo, use el cmdlet **New-InformationBarrierPolicy** con el parámetro **SegmentsBlocked** . 

    |Sintaxis  |Ejemplo  |
    |---------|---------|
    |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"`     |`New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p>    En este ejemplo, se ha definido una directiva denominada *sales-Research* para un segmento denominado *sales*. Cuando se activa y se aplica, esta directiva impide que los usuarios de *ventas* se comuniquen con los usuarios de un segmento denominado *investigación*.         |

2. Para definir su segundo segmento de bloqueo, use el cmdlet **New-InformationBarrierPolicy** con el parámetro **SegmentsBlocked** de nuevo, esta vez con los segmentos invertidos.

    |Ejemplo  |
    |---------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p>    En este ejemplo, se ha definido una directiva denominada *Research-sales* para evitar que la *investigación* se comunique con las *ventas*.     |

2. Proceda con una de las siguientes opciones:

   - (Si es necesario) [Definir una directiva para permitir que un segmento se comunique solo con otro segmento](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   - (Una vez definidas todas las directivas) [Aplicar directivas de barrera de información](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>Escenario 2: permitir que un segmento se comunique solo con otro segmento

1. Para permitir que un segmento se comunique con un solo segmento, use el cmdlet **New-InformationBarrierPolicy** con el parámetro **SegmentsAllowed** . 

    |Sintaxis  |Ejemplo  |
    |---------|---------|
    |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name"`     |`New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR" -State Inactive` <p>    En este ejemplo, se ha definido una directiva denominada *Manufacturing-HR* para un segmento denominado *Manufacturing*. Cuando se activa y se aplica, esta directiva permite que los usuarios en *producción* se comuniquen solo con las personas de un segmento denominado *HR*. (En este caso, la *fabricación* no puede comunicarse con los usuarios que no forman parte de *RH*.)         |

    **Si es necesario, puede especificar varios segmentos con este cmdlet, como se muestra en el ejemplo siguiente.**

    |Sintaxis  |Ejemplo  |
    |---------|---------|
    |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name"`     |`New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p>En este ejemplo, se ha definido una directiva que permite al segmento de *investigación* comunicarse solo con *recursos humanos* y en *producción*.        |

    Repita este paso para cada directiva que desee definir para permitir que determinados segmentos se comuniquen con determinados segmentos específicos.

2. Proceda con una de las siguientes opciones:

   - (Si es necesario) [Definir una directiva para bloquear las comunicaciones entre segmentos](#scenario-1-block-communications-between-segments) 
   - (Una vez definidas todas las directivas) [Aplicar directivas de barrera de información](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>Parte 3: aplicar directivas de barrera de información

Las directivas de barrera de información no surten efecto hasta que las establece en el estado activo y, a continuación, aplican las directivas.

1. Use el cmdlet **Get-InformationBarrierPolicy** para ver una lista de las directivas que se han definido. Anote el estado y la identidad (GUID) de cada Directiva.

    Consta`Get-InformationBarrierPolicy`

2. Para establecer una directiva en estado activo, use el cmdlet **set-InformationBarrierPolicy** con un parámetro **Identity** y el parámetro **State** establecido en **activo**. 

    |Sintaxis  |Ejemplo  |
    |---------|---------|
    |`Set-InformationBarrierPolicy -Identity GUID -State Active`     |`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p>    En este ejemplo, se establece una directiva de barrera de información que tiene el GUID *43c37853-ea10-4b90-a23d-ab8c93772471* en el estado activo.   |

    Repita este paso según corresponda para cada Directiva.

3. Cuando haya terminado de configurar las directivas de barrera de información para el estado activo, use el cmdlet **Start-InformationBarrierPoliciesApplication** en el centro de seguridad & cumplimiento de Office 365.

    Consta`Start-InformationBarrierPoliciesApplication`

    Después de media hora aproximadamente, se aplican directivas, usuario por usuario, para su organización. Si su organización es grande, puede tardar 24 horas (o más) en completarse este proceso. (Como regla general, tarda aproximadamente una hora en procesar las cuentas de usuario de 5.000).

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>Ver el estado de las cuentas de usuario, los segmentos, las directivas o la aplicación de Directiva

Con PowerShell, puede ver el estado de las cuentas de usuario, los segmentos, las directivas y la aplicación de directivas, tal como se muestra en la siguiente tabla.

|Para ver este  |Haga esto  |
|---------|---------|
|Cuentas de usuario     |Use el cmdlet **Get-InformationBarrierRecipientStatus** con parámetros Identity. <p>Consta`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>Puede usar cualquier valor que identifique de forma exclusiva a cada usuario, como el nombre, el alias, el nombre distintivo, el nombre de dominio canónico, la dirección de correo electrónico o el GUID. <p>Ejemplo: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>En este ejemplo, se hace referencia a dos cuentas de usuario en Office 365: *meganb* para *Nuria*y *alexw* para *Alex*. <p>(También puede usar este cmdlet para un solo usuario: `Get-InformationBarrierRecipientStatus -Identity <value>`) <p>Este cmdlet devuelve información sobre los usuarios, como los valores de atributo y las directivas de barrera de información que se aplican.|
|Mismos     |Use el cmdlet **Get-OrganizationSegment** .<p>Consta`Get-OrganizationSegment` <p>Se mostrará una lista de todos los segmentos definidos para la organización.         |
|Directivas de barrera de información     |Use el cmdlet **Get-InformationBarrierPolicy** . <p> Consta`Get-InformationBarrierPolicy` <p>Se mostrará una lista de las directivas de barrera de información definidas y su estado.       |
|La aplicación de directiva de barrera de información más reciente     | Use el cmdlet **Get-InformationBarrierPoliciesApplicationStatus** . <p>Consta`Get-InformationBarrierPoliciesApplicationStatus`<p>    Esto mostrará información sobre si la aplicación de la Directiva se completó, produjo un error o está en curso.       |
|Todas las aplicaciones de directiva de barrera de información|Utilizados`Get-InformationBarrierPoliciesApplicationStatus -All $true`<p>Esto mostrará información sobre si la aplicación de la Directiva se completó, produjo un error o está en curso.|

## <a name="what-if-i-need-to-remove-or-change-policies"></a>¿Qué ocurre si necesito quitar o cambiar directivas?

Hay disponibles recursos para ayudarle a administrar las directivas de barrera de información.

- Si algo va mal con barreras de la información, consulte [solución de problemas](information-barriers-troubleshooting.md)con la información.

- Para evitar que se apliquen las directivas, consulte [detener una aplicación de directiva](information-barriers-edit-segments-policies.md.md#stop-a-policy-application).

- Para quitar una directiva de barrera de información, vea [quitar una directiva](information-barriers-edit-segments-policies.md.md#remove-a-policy).

- Para realizar cambios en los segmentos o las directivas, consulte [Editar (o quitar) directivas de barrera de información](information-barriers-edit-segments-policies.md.md).

## <a name="example-contosos-departments-segments-and-policies"></a>Ejemplo: departamentos, segmentos y directivas de Contoso

Para ver cómo una organización puede enfocar la definición de segmentos y directivas, tenga en cuenta el siguiente ejemplo.

### <a name="contosos-departments-and-plan"></a>Los departamentos y el plan de Contoso

Contoso tiene cinco departamentos: recursos humanos, ventas, marketing, investigación y fabricación. Para mantener la compatibilidad con las regulaciones de la industria, no se supone que los usuarios de algunos departamentos se comuniquen con otros departamentos, tal como se muestra en la tabla siguiente:

|Sector  |Puede hablar con  |No se puede hablar con  |
|---------|---------|---------|
|HR     |Todos         |(sin restricciones)         |
|Lín     |Recursos humanos, marketing, fabricación         |Investigación         |
|Marketing     |Todos         |(sin restricciones)         |
|Investigación     |Recursos humanos, marketing, fabricación        |Lín     |
|Industria |Recursos humanos, marketing |Cualquier persona que no sea HR o marketing |

Teniendo esto en cuenta, el plan de Contoso incluye tres directivas de barrera de información:

1. Una directiva diseñada para evitar que las ventas se comuniquen con la investigación (y otra directiva para evitar que la investigación se comunique con las ventas)
2. Una directiva diseñada para permitir que la fabricación se comunique con RRHH y solo marketing 

No es necesario definir directivas para recursos humanos o marketing.

### <a name="contosos-defined-segments"></a>Segmentos definidos por contoso

Contoso usará el atributo Department en Azure Active Directory para definir segmentos, de la siguiente manera:

|Departamento  |Definición de segmento  |
|---------|---------|
|HR     | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`        |
|Lín     | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"`        |
|Marketing     | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"`        |
|Investigación     | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"`        |
|Industria     | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"`        |

Con los segmentos definidos, contoso continúa definiendo directivas. 

### <a name="contosos-information-barrier-policies"></a>Directivas de la barrera de información de Contoso

Contoso define tres directivas, como se describe en la tabla siguiente:

|Directiva  |Definición de directiva  |
|---------|---------|
|Directiva 1: impedir que las ventas se comuniquen con investigación     | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> En este ejemplo, la Directiva de barrera de información se denomina *ventas-investigación*. Cuando esta directiva está activa y se aplica, ayuda a evitar que los usuarios que están en el segmento de ventas se comuniquen con los usuarios del segmento de investigación. Se trata de una directiva de un solo sentido; no impedirá que la investigación se comunique con ventas. Para ello, se necesita la Directiva 2.      |
|Directiva 2: evitar que la investigación se comunique con las ventas     | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> En este ejemplo, la Directiva de barrera de información se denomina *Research-sales*. Cuando esta directiva está activa y se aplica, ayuda a evitar que los usuarios que están en el segmento de investigación se comuniquen con los usuarios del segmento de ventas.       |
|Directiva 3: permitir que la fabricación se comunique con RRHH y solo marketing     | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing" -State Inactive` <p>En este caso, la Directiva de barrera de información se denomina *manufactura-HRMarketing*. Cuando esta directiva está activa y se aplica, la fabricación solo se puede comunicar con recursos humanos y de marketing. Tenga en cuenta que no se limita la comunicación de RRHH y marketing con otros segmentos. |

Con segmentos y directivas definidos, contoso aplica las directivas mediante la ejecución del cmdlet **Start-InformationBarrierPoliciesApplication** . 

Cuando finaliza, contoso cumple con los requisitos legales y del sector.

## <a name="related-articles"></a>Artículos relacionados

- [Obtener información general sobre las barreras de la información](information-barriers.md)

- [Barreras de la información en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

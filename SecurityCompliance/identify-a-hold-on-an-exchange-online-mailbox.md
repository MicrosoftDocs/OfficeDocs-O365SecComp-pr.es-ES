---
title: Cómo identificar el tipo de retención en un buzón de Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
ms.openlocfilehash: d24e51bca0e3d290f110b1ab40f3ee9ae7993678
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536462"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Cómo identificar el tipo de retención en un buzón de Exchange Online

En este artículo se explica cómo identificar las suspensiones que se colocan en buzones de Exchange Online en Office 365.

Office 365 ofrece una serie de formas en que su organización puede impedir que va a eliminar permanentemente el contenido del buzón. Esto permite a su organización conservar el contenido para satisfacer habituales de cumplimiento de normas o para la duración del departamento jurídico u otros tipos de investigaciones. Aquí tiene una lista de las características de retención (también llamadas suspensiones) en Office 365:

- **La suspensión por litigio** - suspensiones que se aplican a los buzones de usuario en Exchange Online.

- **mantenga presionada la exhibición de documentos electrónicos** - suspensiones que están asociados con un caso de exhibición de documentos electrónicos en el centro de cumplimiento y seguridad. se pueden aplicar a los buzones de usuario y, en el buzón de correo correspondiente para grupos de Office 365 y Microsoft Teams suspensiones de exhibición de documentos electrónicos.

- **Retención local** - suspensiones que se aplican a los buzones de usuario mediante el uso de la exhibición de documentos electrónicos en contexto & herramienta de espera en la administración de Exchange en Exchange se centra en línea.

- **Directiva de retención de office 365** - conserva el contenido de los buzones de usuario en Exchange Online y en el buzón de correo correspondiente para grupos de Office 365 y Microsoft Teams. Puede crear una retención directiva conserva Skype para las conversaciones de negocio, que se almacenan en los buzones de usuario.

  Hay dos tipos de directivas de retención de Office 365 que se pueden asignar a los buzones de correo.

    - **Las directivas de retención de ubicación específica** : estas son las directivas que se asignan a las ubicaciones de contenido de usuarios específicos. Use el cmdlet Get-Mailbox en Exchange Online PowerShell para obtener información acerca de las directivas de retención asignado a buzones específicos.

    - **Las directivas de retención de toda la organización** : se trata de las directivas que se asignan a todas las ubicaciones de contenido en su organización. Use el cmdlet Get-OrganizationConfig en Exchange Online PowerShell para obtener información acerca de las directivas de retención de toda la organización. Para obtener más información, vea la sección "Aplicar una directiva de retención a toda la organización o ubicaciones específicas" en las directivas de retención de información general de Office 365.

Para administrar los buzones de correo en espera, debe identificar el tipo de espera que se coloca en un buzón de correo para que puedan realizar tareas como cambiar la duración de la suspensión, temporal o permanente quitar la suspensión o exclusión de un buzón de correo de una directiva de retención de Office 365. En estos casos, el primer paso es identificar el tipo de espera que se colocan en el buzón de correo. Y debido a que varias suspensiones (y distintos tipos de suspensiones) se pueden colocar en un solo buzón, tendrá que identificar todas las suspensiones que se colocan en un buzón de correo si desea quitar o cambiar dichas suspensiones.

## <a name="step-1-obtaining-the-guid-for-holds-placed-on-a-mailbox"></a>Paso 1: Obtener el GUID de suspensiones colocado en un buzón de correo

Puede ejecutar los siguientes dos cmdlets en Exchange Online PowerShell para obtener el GUID de las suspensiones que se colocan en un buzón de correo. Después de obtener un GUID, usarla para identificar la suspensión específica en el paso 2. Tenga en cuenta que contiene el litigio no se identifican mediante un GUID. Retenciones para litigios están habilitadas o deshabilitadas para un buzón de correo.

- **Get-Mailbox** - uso contiene este cmdlet para determinar si está habilitado el juicio para un buzón de correo y para obtener el GUID de exhibición de documentos electrónicos, suspensiones en contexto y las directivas de retención de Office 365 que se asignan específicamente a un buzón de correo. El resultado de este cmdlet también indicará si un buzón de correo se ha excluido explícitamente de una directiva de retención de toda la organización.

- **Get-OrganizationConfig** - Use este cmdlet para obtener el GUID para las directivas de retención de toda la organización.

Para conectarse a Exchange Online PowerShell, vea [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).

### <a name="get-mailbox"></a>Get-Mailbox

Ejecute el comando siguiente para obtener información sobre las suspensiones y las directivas de retención de Office 365 aplicadas a un buzón de correo.

```
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> Si hay demasiados valores de la propiedad InPlaceHolds y no todos ellos se muestran, puede ejecutar el `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` comando para mostrar cada GUID en una línea independiente.

En la siguiente tabla se describe cómo identificar diferentes tipos de suspensiones según los valores de la propiedad *InPlaceHolds* cuando se ejecuta el cmdlet **Get-Mailbox** .


|Tipo de suspensión  |Valor de ejemplo  |Cómo identificar la suspensión  |
|---------|---------|---------|
|Retención por juicio     |    `True`     |     Juicio está habilitado para un buzón de correo si se establece la propiedad *LitigationHoldEnabled* en `True`.    |
|exhibición de documentos electrónicos     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   La *propiedad InPlaceHolds* contiene el GUID de cualquier suspensión asociado con un caso de exhibición de documentos electrónicos en el centro de cumplimiento y seguridad. Se puede decir esto es una exhibición de documentos electrónicos porque el GUID comienza por la `UniH` prefijo (que denota una retención unificada).      |
|Retención en contexto     |     `c0ba3ce811b6432a8751430937152491` <br/> o <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     La propiedad *InPlaceHolds* contiene el GUID de la retención local que se coloca en el buzón de correo. Puede saber esto es una retención local porque el GUID no inicia con un prefijo o se inicia con el `cld` prefijo.     |
|Directiva de retención de Office 365 aplicado específicamente para el buzón de correo     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> o <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     La propiedad InPlaceHolds contiene el GUID de cualquier directiva de retención de ubicación específica que se aplica a los buzones de correo. Puede identificar las directivas de retención porque el GUID comienza por la `mbx` o la `skp` prefijo. El `skp` prefijo indica que la directiva de retención se aplica a Skype para conversaciones de negocios en el buzón del usuario.    |
|Excluido de una directiva de retención de Office 365 de toda la organización     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     Si un buzón de correo está excluido de una directiva de retención de Office 365 de toda la organización, el GUID para el buzón de correo se excluye de la directiva de retención se muestra en la propiedad InPlaceHolds y se identifica con el `-mbx` prefijo.    |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
Si la propiedad *InPlaceHolds* está vacía cuando se ejecuta el cmdlet **Get-Mailbox** , todavía puede haber uno o más toda la organización Office 365 aplicadas políticas de retención para el buzón de correo. Ejecute el siguiente comando en Exchange Online PowerShell para obtener una lista de GUID para las directivas de retención de Office 365 de toda la organización.

```
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> Si hay demasiados valores de la propiedad InPlaceHolds y no todos ellos se muestran, puede ejecutar el `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando para mostrar cada GUID en una línea independiente.

En la siguiente tabla se describe los distintos tipos de suspensiones de toda la organización y cómo identificar cada tipo de basado en los GUID contenidos en la propiedad *InPlaceHolds* cuando se ejecuta el cmdlet **Get-OrganizationConfig** .


|Tipo de suspensión  |Valor de ejemplo  |Descripción  |
|---------|---------|---------|
|Las directivas de retención 365 de Office que aplican a los buzones de Exchange, carpetas públicas de Exchange y los equipos de chats    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   Las directivas de retención de toda la organización se aplicarán a los buzones de Exchange, carpetas públicas de Exchange, y chats 1xN en Microsoft Teams se identifican mediante los GUID que comienzan con la `mbx` prefijo. Tenga en cuenta que 1xN chats se almacenan en el buzón de correo de los participantes de chat individuales.      |
|Aplicada a los mensajes de canal de Office 365 grupos y equipos de la directiva de retención 365 de Office     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    Las directivas de retención de toda la organización aplicadas a los grupos de Office 365 y los mensajes de canal en Microsoft Teams se identifican mediante los GUID que comienzan con la `grp` prefijo. Tenga en cuenta que los mensajes del canal se almacenan en el buzón de correo de grupo que está asociada con un Team de Microsoft.     |

Para obtener más información las directivas de retención aplicadas a Microsoft Teams, vea la sección "Ubicación de los equipos" [información general de las directivas de retención](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>Descripción del formato del valor de InPlaceHolds para las directivas de retención

Además del prefijo (los buzones, skp o agrupados) que identifica un elemento en la propiedad InPlaceHolds como una directiva de retención de Office 365, el valor también contiene un sufijo que identifica el tipo de acción de retención que está configurada para la directiva. Por ejemplo, el sufijo de acción está resaltado en negrita en los siguientes ejemplos:

   `skp127d7cf1076947929bf136b7a2a8c36f`**: 1**

   `mbx7cfb30345d454ac0a989ab3041051209`**: 2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**: 3**

En la tabla siguiente define las tres acciones de retención posibles:

|Valor  |Descripción  |
|---------|---------|
|**1**     | Indica que la directiva de retención está configurada para eliminar los elementos; la directiva no conserva elementos.        |
|**2**    |    Indica que la directiva de retención está configurada para retener elementos; la directiva de no elimina elementos después de que expire el período de retención.     |
|**3**     |   Indica que la directiva de retención está configurada para retener elementos y, a continuación, eliminarlos después de que expire el período de retención.      |

Para obtener más información acerca de las acciones de retención, consulte la sección "Conservar el contenido para un período de tiempo específico" en [información general de las directivas de retención](retention-policies.md#retaining-content-for-a-specific-period-of-time).
   
## <a name="step-2-using-the-guid-to-identify-the-hold"></a>Paso 2: Utilizando el GUID para identificar la suspensión

Después de obtener el GUID de una suspensión a la que se aplica a un buzón de correo, el siguiente paso es usar ese GUID para identificar la suspensión. Las secciones siguientes muestran cómo se identifica el nombre de la suspensión (y otra información) mediante el uso de la suspensión GUID.

### <a name="ediscovery-holds"></a>suspensiones de exhibición de documentos electrónicos

Ejecute los siguientes comandos en seguridad y cumplimiento centro de PowerShell para identificar una exhibición de documentos electrónicos que se aplican a los buzones de correo. Usar el GUID (sin incluir el prefijo UniH) para la exhibición de documentos electrónicos espera que ha identificado en el paso 1. El primer comando crea una variable que contiene información acerca de la suspensión; Esta variable se usa en los otros comandos. El segundo comando muestra el nombre de la suspensión está asociada con el caso de exhibición de documentos electrónicos. El tercer comando muestra el nombre de la suspensión y una lista de los buzones de a que la suspensión se aplica.

```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold | FL Name,ExchangeLocation
```

Para conectarse a la seguridad y cumplimiento de normas centro de PowerShell, vea [Connect to Office 365 seguridad & PowerShell de centro de cumplimiento](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

### <a name="in-place-holds"></a>Retenciones locales

Ejecute el siguiente comando en Exchange Online PowerShell para identificar la retención local que se aplica a los buzones de correo. Utilice el GUID para la retención local que ha identificado en el paso 1. El comando muestra el nombre de la suspensión y una lista de los buzones de a que la suspensión se aplica.

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```
Tenga en cuenta que si el GUID para la retención local se inicia con el `cld` prefix, no olvide incluir el prefijo al ejecutar el comando anterior.

### <a name="office-365-retention-policies"></a>Directivas de retención de Office 365

Ejecute el siguiente comando en PowerShell de centro de cumplimiento y seguridad a la identidad de la directiva de retención de Office 365 (ubicación específico o de toda la organización) que se aplica a los buzones de correo. Utilice el GUID (sin incluir el prefijo de los buzones, skp o agrupados o el sufijo de acción) que ha identificado en el paso 1.

```
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="next-steps"></a>Pasos siguientes

Después de identificar las suspensiones que se aplican a un buzón de correo, puede realizar tareas como cambiar la duración de la suspensión, temporalmente o quitar de manera permanente la suspensión, o en el caso de las directivas de retención de Office 365, excluir un buzón inactivo de la directiva. Para obtener más información acerca de cómo realizar tareas relacionadas con las suspensiones, vea uno de los siguientes temas:

- Ejecute el [Set-RetentionCompliancePolicy - AddExchangeLocationException \<buzón de usuario >](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps) command en seguridad y cumplimiento centro de PowerShell para excluir un buzón de correo de una directiva de retención de Office 365 de toda la organización. Tenga en cuenta que este comando sólo se puede usar para las directivas de retención donde el valor de la propiedad *ExchangeLocation* es igual a `All`.

- Ejecute el [Set-Mailbox - ExcludeFromOrgHolds \<suspensión GUID sin prefijo o sufijo >](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps) command en Exchange Online PowerShell para excluir un buzón inactivo de una directiva de retención de Office 365 de toda la organización.

- [Cambiar la duración de retención para un buzón inactivo en Office 365](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Eliminar un buzón inactivo en Office 365](delete-an-inactive-mailbox.md)

- [Eliminar elementos de la carpeta de elementos recuperables de buzones en retención en la nube](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)

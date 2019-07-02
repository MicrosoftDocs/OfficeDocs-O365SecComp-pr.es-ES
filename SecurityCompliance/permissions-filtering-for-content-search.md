---
title: Configurar el filtrado de permisos para Búsqueda de contenido
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/14/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: Use el filtrado de permisos de búsqueda de contenido para permitir que un administrador de eDiscovery busque solo en un subconjunto de buzones y sitios de su organización de Office 365.
ms.openlocfilehash: 32db709132ff8e635ee42f2029cf3394c3820105
ms.sourcegitcommit: 803baca9f99a6691fb41a3308e799752e4d8f20c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222274"
---
# <a name="configure-permissions-filtering-for-content-search"></a>Configurar el filtrado de permisos para Búsqueda de contenido

Puede usar el filtrado de permisos de búsqueda para permitir que un administrador de exhibición de documentos electrónicos busque solo en un subconjunto de buzones y sitios de la organización de Office 365. También puede utilizar el filtrado de permisos para permitir que ese mismo administrador de exhibición de documentos electrónicos busque solo contenido de los buzones o los sitios que cumpla unos criterios concretos de búsqueda. Por ejemplo, puede permitir que un administrador de exhibición de documentos electrónicos busque solo en los buzones de usuarios de un departamento o una ubicación en concreto. Para hacerlo, debe crear un filtro que utilice un filtro de destinatarios admitido para limitar en qué buzones puede buscarse. Puede crear también un filtro que especifique qué contenido del buzón puede buscarse. Para ello, debe crear un filtro que utilice una propiedad de mensaje que pueda buscarse. De forma similar, puede permitir que un administrador de exhibición de documentos electrónicos solo busque sitios específicos de SharePoint en su organización. Para hacerlo, debe crear un filtro que limite en qué sitio puede buscarse. También puede crear un filtro que especifique qué contenido del sitio puede buscarse. Para ello, debe crear un filtro que utilice una propiedad de sitio que pueda buscarse.

También puede usar el filtrado de permisos de búsqueda para crear límites lógicos (denominados *límites de cumplimiento*) en una organización de Office 365 que controle las ubicaciones de contenido de usuario (como buzones de correo, sitios de SharePoint y cuentas de OneDrive) que los administradores de eDiscovery específicos pueden buscar. Para obtener más información, consulte [configurar límites de cumplimiento para investigaciones de eDiscovery en Office 365](set-up-compliance-boundaries.md).
  
El filtrado de permisos de búsqueda es compatible con la característica de búsqueda de contenido en el centro de seguridad & cumplimiento. Estos cuatro cmdlets le permiten configurar y administrar los filtros de permisos de búsqueda:
  
[New-ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[Set-ComplianceSecurityFilter](#set-compliancesecurityfilter)

[Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="before-you-begin"></a>Antes de empezar

- Para ejecutar los cmdlets de filtro de seguridad de cumplimiento, debe ser miembro del grupo de roles de administración de la organización en el centro de seguridad & cumplimiento. Para obtener más información, vea [permisos en el centro de seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md).
    
- Tiene que conectar Windows PowerShell al centro de seguridad & cumplimiento y a la organización de Exchange Online para usar los cmdlets de filtro de seguridad de cumplimiento. Esto es necesario porque estos cmdlets necesitan acceso a las propiedades del buzón, que es por qué tiene que conectarse a Exchange Online. Vea los pasos en la sección siguiente. 
    
- Consulte la sección [More information](#more-information) para obtener información adicional acerca de los filtros de permisos de búsqueda. 
    
- El filtrado de permisos de búsqueda se aplica a los buzones inactivos, lo que significa que puede usar el filtrado de contenido de buzones y buzones para limitar quién puede buscar en un buzón inactivo. Consulte la sección [More Information](#more-information) para obtener información adicional acerca del filtrado de permisos y de los buzones inactivos. 
    
-  El filtrado de permisos de búsqueda no se puede usar para limitar quién puede buscar en las carpetas públicas de Exchange. 
    
- No hay ningún límite en el número de filtros de permisos de búsqueda que se pueden crear en una organización. Pero el rendimiento de la búsqueda se verá afectado cuando haya más de 100 filtros de permisos de búsqueda. Para mantener el número de filtros de permisos de búsqueda en la organización tan pequeños como sea posible, cree filtros que combinen las reglas para Exchange, SharePoint y OneDrive en un único filtro siempre que sea posible.
    
## <a name="connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>Conectarse al centro de seguridad & cumplimiento y a Exchange online en una única sesión de PowerShell en remoto

1. Guarde el siguiente texto en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de **. PS1**. Por ejemplo, puede guardarlo en un archivo denominado **ConnectEXO-CC. PS1**.
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. En el equipo local, abra Windows PowerShell, vaya a la carpeta en la que se encuentra el script creado en el paso anterior y, a continuación, ejecute el script. por ejemplo:
    
    ```
    .\ConnectEXO-CC.ps1
    ```
 
¿Cómo se sabe si se ha completado correctamente? Después de ejecutar el script, los cmdlets del centro de seguridad & cumplimiento y Exchange Online se importan a la sesión local de Windows PowerShell. Si no se muestra ningún error, la conexión se habrá establecido correctamente. Una prueba rápida es ejecutar un cmdlet del centro de cumplimiento de & de seguridad y un cmdlet de Exchange Online. Por ejemplo, puede ejecutar **install-UnifiedCompliancePrerequisite** y **Get-Mailbox**. 
  
Si surgen errores, compruebe los requisitos siguientes:
  
- Un problema habitual es una contraseña incorrecta. Vuelva a realizar los dos pasos y preste especial atención al nombre de usuario y la contraseña que escriba en el paso 1.
    
- Compruebe que la cuenta tiene permiso para obtener acceso al centro de seguridad & cumplimiento. Para obtener más información, vea [conceder acceso a los usuarios al centro de seguridad & cumplimiento](grant-access-to-the-security-and-compliance-center.md).
    
- Para evitar que se produzcan ataques por denegación de servicio (DoS), solo se pueden tener abiertas tres conexiones remotas de PowerShell al centro de seguridad & cumplimiento.
    
- Windows PowerShell se debe configurar para ejecutar scripts. Esta opción se configura una sola vez en el equipo, y no cada vez que se conecte. Para hacer que Windows PowerShell ejecute scripts firmados, ejecute el siguiente comando en una ventana de Windows PowerShell con permisos elevados (o sea, una ventana de Windows PowerShell que se abre seleccionando **Ejecutar como administrador**).

    ```
    Set-ExecutionPolicy RemoteSigned
    ```
- Debe abrir el tráfico del puerto TCP 80 entre su equipo local y Office 365. Es probable que esté abierto, pero es algo que hay que tener en cuenta si la organización tiene una directiva de acceso a Internet restrictiva.
    

  
## <a name="new-compliancesecurityfilter"></a>New-ComplianceSecurityFilter

El **New-ComplianceSecurityFilter** se usa para crear un filtro de permisos de búsqueda. En la siguiente tabla se describen los parámetros de este cmdlet. Todos los parámetros son necesarios para crear un filtro de seguridad de cumplimiento. 
  
|**Parámetro**|**Descripción**|
|:-----|:-----|
| _Action_ <br/> | El parámetro _Action_ especifica el tipo de acción de búsqueda al que se aplica el filtro. Las acciones de Búsqueda de contenido posibles son:  <br/><br/> **Export** : el filtro se aplica al exportar los resultados de la búsqueda.  <br/> **Vista previa** : el filtro se aplica al obtener una vista previa de los resultados de búsqueda.  <br/> **Purgar** : el filtro se aplica cuando se depuran los resultados de la búsqueda.  <br/> **Buscar** : el filtro se aplica cuando se ejecuta una búsqueda.  <br/> **Todo** : el filtro se aplica a todas las acciones de búsqueda.  <br/> |
| _FilterName_ <br/> |El parámetro _filtername_ especifica el nombre del filtro de permisos. Este nombre sirve para identificar un filtro al utilizar los cmdlets **Get ComplianceSecurityFilter**, **Set-ComplianceSecurityFilter** y **Remove-ComplianceSecurityFilter**.  <br/> |
| _Filters_ <br/> | El __ parámetro filters especifica los criterios de búsqueda para el filtro de seguridad de cumplimiento. Puede crear tres tipos de filtros diferentes:  <br/><br/> **Filtrado de buzón de correo** : este tipo de filtro especifica los buzones en los que puede __ buscar los usuarios asignados (especificados por el parámetro users). La sintaxis de este tipo de filtro es **Mailbox_** _MailboxPropertyName_, donde _MailboxPropertyName_ especifica una propiedad de buzón de correo que se usa para establecer el ámbito de los buzones que se pueden buscar. Por ejemplo, el filtro `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` de buzón permite que el usuario asignado a este filtro solo busque en buzones de correo que tengan el valor "OttawaUsers" en la propiedad CustomAttribute10.  <br/>  Se puede usar cualquier propiedad de destinatario filtrable admitida para la propiedad _MailboxPropertyName_ . Para obtener una lista de las propiedades admitidas, vea [filterable Properties for the-RecipientFilter Parameter](https://go.microsoft.com/fwlink/p/?LinkId=784903).  <br/><br/> **Filtrado de contenido** de buzones: este tipo de filtro se aplica al contenido que se puede buscar. Especifica el contenido del buzón que los usuarios asignados pueden buscar. La sintaxis de este tipo de filtro es **MailboxContent_** _SearchablePropertyName: Value_, donde _SearchablePropertyName_ especifica una propiedad de lenguaje de consulta de palabras clave (KQL) que se puede especificar en una búsqueda de contenido. Por ejemplo, el filtro `MailboxContent_recipients:contoso.com` de contenido buzón permite que el usuario asignado a este filtro solo busque mensajes enviados a destinatarios en el dominio contoso.com.  <br/>  Para obtener una lista de las propiedades de los mensajes que permiten búsquedas, consulte [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).  <br/><br/> **Filtrado** del sitio y del contenido del sitio: hay dos filtros de SharePoint y de sitio de OneDrive para la empresa que puede usar para especificar el sitio o el contenido del sitio con el que pueden buscar los usuarios asignados:  <br/><br/> - **Site_** _SearchableSiteProperty_ <br/> - **SiteContent_** _SearchableSiteProperty_ <br/><br/>  Estos dos filtros son intercambiables. Por ejemplo, `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` y `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` devolverá los mismos resultados. Pero para ayudarle a identificar lo que hace un filtro, puede `Site_` usar para especificar propiedades relacionadas con el sitio (como una dirección URL del `SiteContent_` sitio) y para especificar propiedades relacionadas con el contenido (como tipos de documentos. Por ejemplo, el filtro `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` permite que el usuario asignado a este filtro solo busque contenido en la https://contoso.sharepoint.com/sites/doctors colección de sitios. El filtro `"SiteContent_FileExtension -eq 'docx'"` permitiría que el usuario asignado a este filtro sólo buscara documentos de Word (Word 2007 y versiones posteriores).  <br/><br/>  Para obtener una lista de las propiedades de sitio que permiten búsquedas, vea [información general sobre las propiedades administradas y rastreadas en SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=331599). Las propiedades marcadas con **sí** en la columna **consultable** se pueden usar para crear un filtro de contenido de sitio o sitio.  <br/> <br/> **Importante:**  Un solo filtro de búsqueda puede tener un tipo de filtro; no puede contener un filtro de buzón de correo y un filtro de sitio; de forma similar, no puede contener un filtro de buzón y un filtro de contenido de buzón. Sin embargo, un filtro puede contener una consulta más compleja del mismo tipo. Por ejemplo,  `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"` <br/><br/> **Importante:** Tiene que crear un filtro de permisos de búsqueda para impedir explícitamente que los usuarios busquen ubicaciones de contenido en un servicio de Office 365 específico (como evitar que un usuario busque en cualquier buzón de Exchange o en cualquier sitio de SharePoint). Es decir, la creación de un filtro de permisos de búsqueda que permita a un usuario buscar en todos los sitios de SharePoint de la organización no impide que el usuario busque buzones de correo. Por ejemplo, para permitir que los administradores de SharePoint solo busquen sitios de SharePoint, tiene que crear un filtro que les impida buscar buzones de correo. De forma similar, para permitir que los administradores de Exchange solo busquen buzones de correo, debe crear un filtro que les impida buscar en sitios.           |
| _Users_ <br/> |El __ parámetro users especifica los usuarios que obtienen este filtro aplicado a sus búsquedas de contenido. Identifique a los usuarios por su alias o su dirección SMTP principal. Se pueden especificar varios valores separados por comas, o bien puede asignar el filtro a todos los usuarios con el valor **Todos**.  <br/> También puede usar el parámetro _users_ para especificar un grupo de funciones del centro de cumplimiento de & de seguridad. Así, podrá crear un grupo de roles personalizado y, a continuación, asignar a ese grupo de roles un filtro de permisos de búsqueda. Por ejemplo, supongamos que tiene un grupo de roles personalizado para los administradores de exhibición de documentos electrónicos de la sede en los Estados Unidos de una compañía multinacional. Puede usar el parámetro _users_ para especificar este grupo de funciones (mediante la propiedad Name del grupo de funciones) y, a continuación, usar el parámetro _Filter_ para permitir que solo se busque en los buzones de los Estados Unidos.  <br/> Con este parámetro no es posible especificar grupos de distribución.  <br/> |
   

## <a name="examples-of-creating-search-permissions-filters"></a>Ejemplos de creación de filtros de permisos de búsqueda

Vea a continuación ejemplos del uso del cmdlet **New-ComplianceSecurityFilter** para crear un filtro de permisos de búsqueda. 
  
Este ejemplo permite al usuario annb@contoso.com realizar todas las acciones de búsqueda de contenido solo para los buzones en Canadá. Este filtro contiene el código de país numérico de tres dígitos correspondiente a Canadá según la ISO 3166-1.

```
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'" -Action All
```

En este ejemplo se permite que los usuarios ' donh y suzanf busquen solo los buzones que tienen el valor ' Marketing ' para la propiedad de buzón CustomAttribute1.

```
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'" -Action Search
```
   
En este ejemplo se permite que los miembros del grupo de roles "Administradores de detección de EE. UU." realicen todas las acciones de Búsqueda de contenido solo en los buzones de Estados Unidos. Este filtro contiene el código de país numérico de tres dígitos correspondiente a Estados Unidos según la ISO 3166-1.
  
```
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryCode  -eq '840'" -Action All
```

En este ejemplo se permite que los miembros del grupo de roles eDiscovery Manager busquen solo los buzones de los miembros del grupo de distribución de usuarios de Ottawa. 
  
```
$DG = Get-DistributionGroup "Ottawa Users"
```

```
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```
En este ejemplo se evita que cualquier usuario elimine contenido de los buzones de los miembros del grupo de distribución Executive Team.

```
$DG = Get-DistributionGroup "Executive Team"
```

```
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users All -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" -Action Purge
```
   
En este ejemplo se permite a los miembros del grupo de roles personalizado OneDrive eDiscovery Managers buscar solo contenido en las ubicaciones de OneDrive para la empresa de la organización.

```
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```
   
> [!NOTE]
> Para restringir a los usuarios la búsqueda de sitios específicos `Site_Path`, use el filtro, como se muestra en el ejemplo anterior. El `Site_Site` uso de no funcionará. 
  
En este ejemplo se limita al usuario a realizar todas las acciones de Búsqueda de contenido solo en los mensajes de correo electrónico enviados durante el año natural 2015.

```
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```
   
De forma parecida al ejemplo anterior, este ejemplo limita al usuario a realizar todas las acciones de Búsqueda de contenido solo en los documentos que se modificaron por última vez durante el año natural 2015.

```
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```
   
En este ejemplo se impide que los miembros del grupo de roles "OneDrive Discovery Managers" realicen acciones de búsqueda de contenido en cualquier buzón de correo de la organización. 

```
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```

En este ejemplo se impide que todos los usuarios de la organización busquen mensajes de correo electrónico enviados o recibidos por los usuarios como Janes o SARAD.

```
New-ComplianceSecurityFilter -FilterName NoSaraJanet -Users All -Filters "MailboxContent_Participants -notlike 'janets@contoso.onmicrosoft.com' -and MailboxContent_Participants -notlike 'sarad@contoso.onmicrosoft.com'" -Action Search
```
  
## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

El **Get-ComplianceSecurityFilter** se usa para devolver una lista de filtros de permisos de búsqueda. Utilice el parámetro _filtername_ para devolver información de un filtro de búsqueda específico. 
  
## <a name="set-compliancesecurityfilter"></a>Set-ComplianceSecurityFilter

El **set-ComplianceSecurityFilter** se usa para modificar un filtro de permisos de búsqueda existente. El único parámetro obligatorio es _filtername_. 
  
|**Parámetro**|**Descripción**|
|:-----|:-----|
| _Action_| El parámetro _Action_ especifica el tipo de acción de búsqueda al que se aplica el filtro. Las acciones de Búsqueda de contenido posibles son: <br/><br/> **Export** : el filtro se aplica al exportar los resultados de la búsqueda.  <br/> **Vista previa** : el filtro se aplica al obtener una vista previa de los resultados de búsqueda.  <br/> **Purgar** : el filtro se aplica cuando se depuran los resultados de la búsqueda.  <br/> **Buscar** : el filtro se aplica cuando se ejecuta una búsqueda.  <br/> **Todo** : el filtro se aplica a todas las acciones de búsqueda.  <br/> |
| _FilterName_|El parámetro _filtername_ especifica el nombre del filtro de permisos. |
| _Filters_| El __ parámetro filters especifica los criterios de búsqueda para el filtro de seguridad de cumplimiento. Puede crear dos tipos diferentes de filtros: <br/><br/>**Filtrado de buzón de correo** : este tipo de filtro especifica los buzones en los que puede __ buscar los usuarios asignados (especificados por el parámetro users). La sintaxis de este tipo de filtro es **Mailbox_** _MailboxPropertyName_, donde _MailboxPropertyName_ especifica una propiedad de buzón de correo que se usa para establecer el ámbito de los buzones que se pueden buscar. Por ejemplo, el filtro `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` de buzón permite que el usuario asignado a este filtro solo busque en buzones de correo que tengan el valor "OttawaUsers" en la propiedad CustomAttribute10.  Se puede usar cualquier propiedad de destinatario filtrable admitida para la propiedad _MailboxPropertyName_ . Para obtener una lista de las propiedades admitidas, vea [filterable Properties for the-RecipientFilter Parameter](https://go.microsoft.com/fwlink/p/?LinkId=784903). <br/><br/>**Filtrado de contenido** de buzones: este tipo de filtro se aplica al contenido que se puede buscar. Especifica el contenido del buzón que los usuarios asignados pueden buscar. La sintaxis de este tipo de filtro es **MailboxContent_** _SearchablePropertyName: Value_, donde _SearchablePropertyName_ especifica una propiedad de lenguaje de consulta de palabras clave (KQL) que se puede especificar en una búsqueda de contenido. Por ejemplo, el filtro `MailboxContent_recipients:contoso.com` de contenido buzón permite que el usuario asignado a este filtro solo busque mensajes enviados a destinatarios en el dominio contoso.com.  Para obtener una lista de las propiedades de los mensajes que permiten búsquedas, consulte [Keyword queries for Content Search](keyword-queries-and-search-conditions.md). <br/><br/>**Filtrado** del sitio y del contenido del sitio: hay dos filtros de SharePoint y de sitio de OneDrive para la empresa que puede usar para especificar el sitio o el contenido del sitio con el que pueden buscar los usuarios asignados: <br/><br/>- **Site_** *SearchableSiteProperty* <br/>- **SiteContent**_*SearchableSiteProperty*<br/><br/>Estos dos filtros son intercambiables. Por ejemplo, `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` y `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` devuelve los mismos resultados. Pero para ayudarle a identificar lo que hace un filtro, puede `Site_` usar para especificar propiedades relacionadas con el sitio (como una dirección URL del `SiteContent_` sitio) y para especificar propiedades relacionadas con el contenido (como tipos de documentos. Por ejemplo, el filtro `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` permite que el usuario asignado a este filtro solo busque contenido en la https://contoso.spoppe.com/sites/doctors colección de sitios. El filtro `"SiteContent_FileExtension -eq 'docx'"` permitiría que el usuario asignado a este filtro sólo buscara documentos de Word (Word 2007 y versiones posteriores).  <br/><br/>Para obtener una lista de las propiedades de sitio que permiten búsquedas, vea [información general sobre las propiedades administradas y rastreadas en SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=331599). Las propiedades marcadas con **sí** en la columna **consultable** se pueden usar para crear un filtro de contenido de sitio o sitio. <br/><br/> **Importante:** Un solo filtro de búsqueda puede tener un tipo de filtro; no puede contener un filtro de buzón de correo y un filtro de sitio; de forma similar, no puede contener un filtro de buzón y un filtro de contenido de buzón. Sin embargo, un filtro puede contener una consulta más compleja del mismo tipo. Por ejemplo,  `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`          |
| _Users_|El __ parámetro users especifica los usuarios que obtienen este filtro aplicado a sus búsquedas de contenido. Como se trata de una propiedad de varios valores, especificar un usuario o un grupo de usuarios con este parámetro sobrescribe la lista de usuarios existente. Vea los siguientes ejemplos para ver la sintaxis para agregar y quitar usuarios seleccionados. <br/><br/>También puede usar el parámetro _users_ para especificar un grupo de funciones del centro de cumplimiento de & de seguridad. Así, podrá crear un grupo de roles personalizado y, a continuación, asignar a ese grupo de roles un filtro de permisos de búsqueda. Por ejemplo, supongamos que tiene un grupo de roles personalizado para los administradores de exhibición de documentos electrónicos de la sede en los Estados Unidos de una compañía multinacional. Puede usar el parámetro _users_ para especificar este grupo de funciones (mediante la propiedad Name del grupo de funciones) y, a continuación, usar el parámetro _Filter_ para permitir que solo se busque en los buzones de los Estados Unidos. <br/><br/>Con este parámetro no es posible especificar grupos de distribución. |

## <a name="examples-of-changing-search-permissions-filters"></a>Ejemplos de cambio de filtros de permisos de búsqueda

Estos ejemplos muestran cómo usar los cmdlets **Get-ComplianceSecurityFilter** y **set-ComplianceSecurityFilter** para agregar o quitar un usuario de la lista de usuarios existente a la que está asignado el filtro. Al agregar o quitar usuarios de un filtro, especifique el usuario mediante su dirección SMTP. 
  
En este ejemplo se agrega un usuario al filtro.

```
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```
```
$filterusers.users.add("pilarp@contoso.com")
```

```
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```
   
En este ejemplo se quita un usuario del filtro.

```
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```
$filterusers.users.remove("annb@contoso.com")
```

```
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```
  
## <a name="remove-compliancesecurityfilter"></a>Remove-ComplianceSecurityFilter

Se usa **Remove-ComplianceSecurityFilter** para eliminar un filtro de búsqueda. Utilice el parámetro _filtername_ para especificar el filtro que desee eliminar. 
  
## <a name="more-information"></a>Más información

- **¿Cómo funciona el filtrado de permisos de búsqueda? ** El filtro de permisos se agrega a la consulta de búsqueda cuando se ejecuta una búsqueda de contenido. El filtro de permisos se une a la consulta de búsqueda por el operador booleano **and** . Por ejemplo, tiene un filtro de permisos que permite a Bob realizar todas las acciones de búsqueda en los buzones de los miembros del grupo de distribución de trabajadores. A continuación, Bob ejecuta una búsqueda de contenido en todos los buzones de la organización `sender:jerry@adatum.com`con la consulta de búsqueda. Dado que el filtro de permisos y la consulta de búsqueda se combinan lógicamente mediante un operador **and** , la búsqueda devuelve cualquier mensaje enviado por Jerry@adatum.com a cualquier miembro del grupo de distribución de trabajadores. 
    
- **¿Qué sucede si tiene varios filtros de permisos de búsqueda?** En una consulta de búsqueda de contenido, varios filtros de permisos **** se combinan mediante operadores booleanos. Por lo tanto, se devolverán resultados si alguno de los filtros es true. En una búsqueda de contenido, todos los filtros (combinados mediante operadores **or** ) se combinan con la consulta de búsqueda por el operador **and** . Vamos a echar el ejemplo anterior, en el que un filtro de búsqueda permite a Bob buscar solo en los buzones de los miembros del grupo de distribución de trabajadores. A continuación, creamos otro filtro que impida a Bob buscar el buzón de correo de Phil ("Mailbox_Alias-ne" Phil ""). Además, supongamos que Phil es un miembro del grupo de trabajadores. Cuando Bob ejecuta una búsqueda de contenido (del ejemplo anterior) en todos los buzones de la organización, los resultados de la búsqueda se devuelven para el buzón de Phil, aunque haya aplicado el filtro para evitar que Bob busque en el buzón de Phil. Esto se debe a que el primer filtro, que permite a Bob buscar en el grupo de trabajadores, es verdadero. Y debido a que Phil es miembro del grupo de trabajadores, Bob puede buscar el buzón de correo de Phil. 
    
- **¿Funciona el filtrado de permisos de búsqueda para los buzones inactivos?** Sí, puede usar los filtros de contenido buzón de correo y buzón de correo para limitar quién puede buscar buzones inactivos en su organización. Como un buzón normal, un buzón inactivo tiene que configurarse con la propiedad recipient que se usa para crear un filtro de permisos. Si es necesario, puede usar el comando **Get-Mailbox-InactiveMailboxOnly** para mostrar las propiedades de los buzones inactivos. Para obtener más información, vea [crear y administrar buzones inactivos en Office 365](create-and-manage-inactive-mailboxes.md).
    
- **¿Funciona el filtrado de permisos de búsqueda para las carpetas públicas?** No. Como se explicó anteriormente, el filtrado de permisos de búsqueda no se puede usar para limitar quién puede buscar en las carpetas públicas de Exchange. Por ejemplo, los elementos de las ubicaciones de carpetas públicas no se pueden excluir de los resultados de búsqueda mediante un filtro de permisos. 
    
- **¿Permite que un usuario busque en todas las ubicaciones de contenido de un servicio específico, también les impide buscar ubicaciones de contenido en un servicio diferente?** No. Como se ha explicado anteriormente, tiene que crear un filtro de permisos de búsqueda para impedir explícitamente que los usuarios busquen ubicaciones de contenido en un servicio de Office 365 específico (como evitar que un usuario busque en cualquier buzón de Exchange o en cualquier sitio de SharePoint). Es decir, la creación de un filtro de permisos de búsqueda que permita a un usuario buscar en todos los sitios de SharePoint de la organización no impide que el usuario busque buzones de correo. Por ejemplo, para permitir que los administradores de SharePoint solo busquen sitios de SharePoint, tiene que crear un filtro que les impida buscar buzones de correo. De forma similar, para permitir que los administradores de Exchange solo busquen buzones de correo, debe crear un filtro que les impida buscar en sitios.

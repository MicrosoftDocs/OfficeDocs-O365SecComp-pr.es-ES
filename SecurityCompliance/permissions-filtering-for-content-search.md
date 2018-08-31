---
title: Configurar el filtrado de permisos para Búsqueda de contenido
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/14/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: Usar permisos de búsqueda de contenido filtrado para permitir que un administrador de exhibición de documentos electrónicos a buscar sólo un subconjunto de los buzones de correo y los sitios de la organización de Office 365.
ms.openlocfilehash: 2b6968a097e7abe5943a84b9ceb9b6d126057cc2
ms.sourcegitcommit: c166964fe14eec69139a2d3d9c10d2c40ab33f91
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23258628"
---
# <a name="configure-permissions-filtering-for-content-search"></a>Configurar el filtrado de permisos para Búsqueda de contenido

Puede usar los permisos de búsqueda filtrado para permitir que un administrador de exhibición de documentos electrónicos a buscar sólo un subconjunto de los buzones de correo y los sitios de la organización de Office 365. También puede usar los permisos para permitir que el mismo administrador de exhibición de documentos electrónicos a buscar sólo para contenido de buzones de correo o sitio que cumpla los criterios de búsqueda específicos de filtrado. Por ejemplo, es posible que permiten a un administrador de exhibición de documentos electrónicos de búsqueda solo los buzones de los usuarios en una ubicación específica o un departamento. Para ello, mediante la creación de un filtro que usa un filtro de destinatarios admitido para limitar qué buzones puede buscar. También puede crear un filtro que especifica qué contenido de los buzones se puede buscar. Esto se realiza mediante la creación de un filtro que use una propiedad de mensaje que admite búsquedas. De forma similar, es posible que permiten a un administrador de exhibición de documentos electrónicos buscar sólo sitios de SharePoint específicos de la organización. Para ello, mediante la creación de un filtro que limita el sitio que se puede buscar. También puede crear un filtro que especifica qué contenido del sitio se puede buscar. Esto se realiza mediante la creación de un filtro que use una propiedad del sitio que admite búsquedas.

También puede usar los permisos de búsqueda filtrado para crear los límites lógicos (denominados *límites de cumplimiento de normas*) dentro de una organización de Office 365 que controlan las ubicaciones de contenido de usuario (por ejemplo, buzones de correo, los sitios de SharePoint y las cuentas de OneDrive) que pueden buscar los administradores de exhibición de documentos electrónicos específicos. Para obtener más información, vea [establecer los límites de cumplimiento para investigaciones de exhibición de documentos electrónicos en Office 365](set-up-compliance-boundaries.md).
  
Permisos de búsqueda filtrado es compatible con la característica de búsqueda de contenido de la seguridad de Office 365 &amp; centro de cumplimiento. Estos cuatro cmdlets le permiten configurar y administrar los filtros de búsqueda de permisisons:
  
[Nueva ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[Set-ComplianceSecurityFilter](#set-compliancesecurityfilter)

[Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="before-you-begin"></a>Antes de empezar

- Para ejecutar los cmdlets de filtro de seguridad de cumplimiento, tiene que ser un miembro del grupo de roles de administración de la organización en la seguridad &amp; centro de cumplimiento. Para obtener más información, vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).
    
- Tiene que conectar Windows PowerShell para ambos la seguridad &amp; centro de cumplimiento y a la organización de Exchange Online para usar los cmdlets de filtro de seguridad de cumplimiento. Esto es necesario porque estos cmdlets necesitan tener acceso a las propiedades del buzón, que es la razón por la que se necesitan para conectarse a Exchange Online. Vea los pasos descritos en la siguiente sección. 
    
- Consulte la sección [More information](#more-information) para obtener información adicional acerca de los filtros de permisos de búsqueda. 
    
- Permisos de búsqueda filtrado es aplicable a los buzones de correo inactivos, lo que significa que puede usar el buzón de correo y el contenido de los buzones de filtrado para limitar quién puede buscar un buzón inactivo. Vea la sección [obtener más información](#more-information) para obtener información adicional sobre permisos filtrado y buzones de correo inactivos. 
    
-  Filtrado de permisos de búsqueda no se puede usar para limitar quién puede buscar las carpetas públicas en Exchange. 
    
- No hay ningún límite para el número de filtros de permisos de búsqueda que se pueden crear en una organización. Sin embargo, el rendimiento de la búsqueda se verán afectado cuando hay más de 100 filtros de permisos de búsqueda. Para mantener el número de filtros de búsqueda de permisos en la organización tan pequeños como sea posible, cree los filtros que se combinan las reglas para Exchange, SharePoint y OneDrive en un único filtro siempre que sea posible.
    
## <a name="connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>Conectarse a la seguridad &amp; centro de cumplimiento y Exchange Online en una sola sesión de PowerShell remota

1. Guarde el siguiente texto en un archivo de secuencia de comandos de Windows PowerShell mediante el uso de un sufijo de nombre de archivo de. ps1. Por ejemplo, puede guardar en un archivo denominado ConnectEXO-CC.ps1.
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. En el equipo local, abra Windows PowerShell, vaya a la carpeta donde se encuentra la secuencia de comandos que creó en el paso anterior y, a continuación, ejecute el script; Por ejemplo:
    
    ```
    .\ConnectEXO-CC.ps1
    ```
 
¿Cómo sé si ha funcionado? Después de ejecutar el script, cmdlets de la seguridad &amp; centro de cumplimiento y Exchange Online se importan en su sesión de Windows PowerShell local. Si no recibe algún error, conectado correctamente. Es una prueba rápida ejecutar una seguridad &amp; centro de cumplimiento cmdlet — por ejemplo, **Install-UnifiedCompliancePrerequisite** — y un cmdlet de Exchange Online, por ejemplo, **Get-Mailbox**. 
  
Si surgen errores, compruebe los requisitos siguientes:
  
- Un problema habitual es una contraseña incorrecta. Vuelva a realizar los dos pasos y preste especial atención al nombre de usuario y la contraseña que escriba en el paso 1.
    
- Compruebe que su cuenta tiene permiso para tener acceso a la seguridad &amp; centro de cumplimiento. Para obtener información detallada, vea [dar a los usuarios acceso a la seguridad &amp; centro de cumplimiento](grant-access-to-the-security-and-compliance-center.md).
    
- Para ayudar a evitar los ataques de denegación de servicio (DoS), está limitado a tres conexiones de PowerShell remotas abiertas a la seguridad &amp; centro de cumplimiento.
    
- Windows PowerShell debe estar configurado para ejecutar scripts. Esta opción se configura una sola vez en el equipo, y no cada vez que se conecte. Para permitir que Windows PowerShell ejecute scripts firmados, ejecute el siguiente comando en una ventana de Windows PowerShell elevada (una ventana de Windows PowerShell que abrió cuando seleccionó **Ejecutar como administrador**).

    ```
    Set-ExecutionPolicy RemoteSigned
    ```
- El tráfico del puerto 80 de TCP es necesario abrir entre el equipo local y Office 365. Está probablemente abierto, pero es algo a tener en cuenta si su organización tiene una directiva de acceso de Internet restrictiva.
    

  
## <a name="new-compliancesecurityfilter"></a>Nueva ComplianceSecurityFilter
<a name="New"> </a>

El **Nuevo ComplianceSecurityFilter** se usa para crear un nuevo filtro de permisos de búsqueda. En la siguiente tabla se describe los parámetros de este cmdlet. Todos los parámetros necesarios para crear un filtro de seguridad de cumplimiento. 
  
|**Parámetro**|**Descripción**|
|:-----|:-----|
| _Action_ <br/> | El parámetro de _acción_ especifica ese tipo de acción de búsqueda que el filtro se aplica a. Las posibles acciones de búsqueda de contenido son:<br/><br/> **Exportar** - el filtro se aplica al exportar los resultados de búsqueda.  <br/> **Vista previa** - el filtro se aplica durante la vista previa de los resultados de búsqueda.  <br/> **Purgar** - el filtro se aplica al depurar los resultados de búsqueda.  <br/> **Búsqueda** - el filtro se aplica cuando se ejecuta una búsqueda.  <br/> **Todos los** - el filtro se aplica a todas las acciones de búsqueda.  <br/> |
| _FilterName_ <br/> |El parámetro _FilterName_ especifica el nombre del filtro de permisos. Este nombre es utilizado a la identidad de un filtro al usar los cmdlets **Get-ComplianceSecurityFilter**, **Set-ComplianceSecurityFilter** y **Remove-ComplianceSecurityFilter** .<br/> |
| _Filtros_ <br/> | El parámetro de _filtros_ especifica los criterios de búsqueda para el filtro de seguridad de cumplimiento. Puede crear tres distintos tipos de filtros:<br/><br/> **Filtrado de buzón de correo** : este tipo de filtro especifica los buzones pueden buscar los usuarios asignados (especificados por el parámetro de _los usuarios_ ). La sintaxis de este tipo de filtro es **Mailbox_** _MailboxPropertyName_, donde _MailboxPropertyName_ especifica una propiedad de buzón de correo que se utiliza para delimitar los buzones que se pueden buscar. Por ejemplo, el filtro de buzón de correo `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` permitiría que el usuario asignado este filtro para buscar sólo los buzones que tienen el valor "OttawaUsers" en la propiedad CustomAttribute10.<br/>  Cualquier propiedad de destinatarios que se pueden filtrar compatible se puede usar para la propiedad _MailboxPropertyName_ . Para obtener una lista de las propiedades admitidas, vea [las propiedades que se pueden filtrar para el parámetro - RecipientFilter](https://go.microsoft.com/fwlink/p/?LinkId=784903).<br/><br/> **Filtrado de contenido de los buzones** - este tipo de filtro se aplica en el contenido que se puede buscar. Especifica el contenido de los buzones que pueden buscar los usuarios asignados. La sintaxis de este tipo de filtro es **MailboxContent_** _SearchablePropertyName:value_, donde _SearchablePropertyName_ especifica una propiedad de lenguaje de consulta de palabras clave (KQL) que se puede especificar en una búsqueda de contenido. Por ejemplo, el filtro de contenido de buzones de correo `MailboxContent_recipients:contoso.com` permitiría que el usuario asignado este filtro para buscar sólo los mensajes enviados a destinatarios en el dominio contoso.com.<br/>  Para obtener una lista de propiedades de mensaje que admite búsquedas, vea [consultas de palabra clave y las condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).  <br/><br/> **Filtrado de sitios y contenido del sitio** - hay dos SharePoint y OneDrive para filtros de negocio relacionados con el sitio que se pueden utilizar para especificar qué sitio o contenido pueden buscar los usuarios asignados:  <br/><br/> - **Site_** _SearchableSiteProperty_ <br/> - **SiteContent_** _SearchableSiteProperty_ <br/><br/>  Estos dos filtros son intercambiables; Por ejemplo `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` y `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` devolverá los resultados de la misma. Pero para ayudar a identificar lo que hace un filtro, se puede usar `Site_` para especificar las propiedades relacionadas con el sitio (por ejemplo, una dirección URL del sitio) y `SiteContent_` para especificar las propiedades relacionadas con el contenido (por ejemplo, tipos de documento. Por ejemplo, el filtro `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` permitiría que el usuario asignado este filtro para buscar solamente contenido en el https://contoso.sharepoint.com/sites/doctors colección de sitios. El filtro `"SiteContent_FileExtension -eq 'docx'"` permitiría que el usuario asignado este filtro para buscar sólo documentos de Word (Word 2007 y versiones posterior).<br/><br/>  Para obtener una lista de propiedades del sitio que admite búsquedas, consulte [Overview of rastreadas y propiedades administradas en SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=331599). Las propiedades marcan con un **Sí** en el ** Queryable ** columna se puede usar para crear un sitio o un filtro de contenido de sitio.<br/> <br/> **Importante:**  Un filtro de búsqueda único sólo puede tener un tipo de filtro; no puede contener un filtro de buzón de correo y un filtro de sitio; de forma similar, no puede contener un filtro de buzón de correo y un filtro de contenido de buzones de correo. Sin embargo, un filtro puede contener una consulta más compleja del mismo tipo. Por ejemplo,`"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"` <br/><br/> **Importante:** Se debe crear un filtro de permisos de búsqueda para impedir explícitamente a los usuarios buscar ubicaciones de contenido en un servicio de Office 365 específico (por ejemplo, impide que un usuario buscar cualquier buzón de correo de Exchange o a cualquier sitio de SharePoint). En otras palabras, creación de un filtro de permisos de búsqueda que permite a un usuario buscar todos los sitios de SharePoint en la organización no impide que el usuario buscar buzones de correo. Por ejemplo, para permitir que los administradores de SharePoint buscar sólo los sitios de SharePoint, debe crear un filtro que impide que la búsqueda de buzones de correo. De forma similar, para permitir que los administradores de Exchange buscar sólo en buzones de correo, se debe crear un filtro que impide que la búsqueda de sitios.           |
| _Usuarios_ <br/> |El parámetro _usuarios_ especifica los usuarios que obtener este filtro aplicado a sus búsquedas de contenido. Identificar a los usuarios por su alias o la dirección SMTP principal. Puede especificar varios valores separados por comas, o puede asignar el filtro a todos los usuarios con el valor de **todos los**.<br/> También puede usar el parámetro de _los usuarios_ para especificar un valor bursátil &amp; grupo de roles de centro de cumplimiento. Un filtro de búsqueda de los permisos de grupo permite crear un grupo de roles personalizados y, a continuación, asignar dicha función. Por ejemplo, supongamos que tiene un grupo de funciones personalizadas para los administradores de exhibición de documentos electrónicos de la subsidiaria de Estados Unidos de una compañía multinacional. Puede usar el parámetro de _los usuarios_ para especificar este grupo de funciones (mediante el uso de la propiedad nombre del grupo de roles) y, a continuación, use el parámetro _Filter_ para permitir que sólo los buzones de correo en los Estados Unidos que se desea buscar.<br/> Con este parámetro no es posible especificar grupos de distribución.  <br/> |
   

## <a name="examples-of-creating-search-permissions-filters"></a>Ejemplos de creación de filtros de búsqueda de permisos

Vea a continuación ejemplos del uso del cmdlet **New-ComplianceSecurityFilter** para crear un filtro de permisos de búsqueda. 
  
En este ejemplo se permite que el usuario annb@contoso.com para llevar a cabo todas las acciones de búsqueda de contenido únicamente para los buzones de correo en Canadá. Este filtro contiene el código de país numérico de tres dígitos de Canadá de ISO 3166-1.

```
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'" -Action All
```

En este ejemplo se permite que los usuarios donh y suzanf busquen solo en los buzones con el valor 'Marketing' para la propiedad de buzón CustomAttribute1.

```
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'" -Action Search
```
   
En este ejemplo se permite que los miembros del grupo de roles "Administradores de detección de EE. UU." realicen todas las acciones de Búsqueda de contenido solo en los buzones de Estados Unidos. Este filtro contiene el código de país numérico de tres dígitos correspondiente a Estados Unidos según la ISO 3166-1.
  
```
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryCode  -eq '840'" -Action All
```

En este ejemplo se permite que los miembros del grupo de roles eDiscovery Manager busquen solo en los buzones de los miembros del grupo de distribución Ottawa Users. 
  
```
$DG = Get-DistributionGroup "Ottawa Users"
```

```
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```
En este ejemplo se impide que cualquier usuario elimine contenido de los buzones de los miembros del grupo de distribución Executive Team.

```
$DG = Get-DistributionGroup "Executive Team"
```

```
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users all -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" -Action Purge
```
   
En este ejemplo se permite que los miembros del grupo de funciones personalizado de OneDrive para la exhibición de documentos electrónicos los administradores a sólo una búsqueda de contenido en OneDrive para las ubicaciones de negocio en la organización.

```
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```
   
> [!NOTE]
> Para restringir los usuarios a buscar sitios específicos, use el filtro de `Site_Path`, tal como se muestra en el ejemplo anterior. Uso de `Site_Site` no funcionará. 
  
En este ejemplo se limita al usuario a realizar todas las acciones de Búsqueda de contenido solo en los mensajes de correo electrónico enviados durante el año natural 2015.

```
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```
   
De forma parecida al ejemplo anterior, este ejemplo limita al usuario a realizar todas las acciones de Búsqueda de contenido solo en los documentos que se modificaron por última vez durante el año natural 2015.

```
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```
   
En este ejemplo se impide que los miembros del grupo de roles "OneDrive de los administradores de detección" realizar acciones de búsqueda de contenido en cualquier buzón de correo en la organización. 

```
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```
  
## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

El **Get-ComplianceSecurityFilter** se usa para devolver una lista de filtros de búsqueda de permisos. Usar el parámetro _FilterName_ para devolver información para un filtro de búsqueda específica. 
  
## <a name="set-compliancesecurityfilter"></a>Set-ComplianceSecurityFilter

El **Conjunto ComplianceSecurityFilter** se usa para modificar un filtro de permisos de búsqueda existente. El único parámetro necesario es _FilterName_. 
  
|**Parámetro**|**Descripción**|
|:-----|:-----|
| _Action_| El parámetro de _acción_ especifica ese tipo de acción de búsqueda que el filtro se aplica a. Las posibles acciones de búsqueda de contenido son:<br/><br/> **Exportar** - el filtro se aplica al exportar los resultados de búsqueda.  <br/> **Vista previa** - el filtro se aplica durante la vista previa de los resultados de búsqueda.  <br/> **Purgar** - el filtro se aplica al depurar los resultados de búsqueda.  <br/> **Búsqueda** - el filtro se aplica cuando se ejecuta una búsqueda.  <br/> **Todos los** - el filtro se aplica a todas las acciones de búsqueda.  <br/> |
| _FilterName_|El parámetro _FilterName_ especifica el nombre del filtro de permisos. |
| _Filtros_| El parámetro de _filtros_ especifica los criterios de búsqueda para el filtro de seguridad de cumplimiento. Puede crear dos distintos tipos de filtros:<br/><br/>**Filtrado de buzón de correo** : este tipo de filtro especifica los buzones pueden buscar los usuarios asignados (especificados por el parámetro de _los usuarios_ ). La sintaxis de este tipo de filtro es **Mailbox_** _MailboxPropertyName_, donde _MailboxPropertyName_ especifica una propiedad de buzón de correo que se utiliza para delimitar los buzones que se pueden buscar. Por ejemplo, el filtro de buzón de correo `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` permitiría que el usuario asignado este filtro para buscar sólo los buzones que tienen el valor "OttawaUsers" en la propiedad CustomAttribute10.  Cualquier propiedad de destinatarios que se pueden filtrar compatible se puede usar para la propiedad _MailboxPropertyName_ . Para obtener una lista de las propiedades admitidas, vea [las propiedades que se pueden filtrar para el parámetro - RecipientFilter](https://go.microsoft.com/fwlink/p/?LinkId=784903).<br/><br/>**Filtrado de contenido de los buzones**- este tipo de filtro se aplica en el contenido que se puede buscar. Especifica el contenido de los buzones que pueden buscar los usuarios asignados. La sintaxis de este tipo de filtro es **MailboxContent_** _SearchablePropertyName:value_, donde _SearchablePropertyName_ especifica una propiedad de lenguaje de consulta de palabras clave (KQL) que se puede especificar en una búsqueda de contenido. Por ejemplo, el filtro de contenido de buzones de correo `MailboxContent_recipients:contoso.com` permitiría que el usuario asignado este filtro para buscar sólo los mensajes enviados a destinatarios en el dominio contoso.com.  Para obtener una lista de propiedades de mensaje que admite búsquedas, vea [consultas de palabra clave para la búsqueda de contenido](keyword-queries-and-search-conditions.md).<br/><br/>**Filtrado de sitios y contenido del sitio** Hay dos SharePoint y OneDrive para filtros de negocio relacionados con el sitio que se pueden utilizar para especificar qué sitio o el contenido del sitio pueden buscar los usuarios asignados: <br/><br/>- **Site_** *SearchableSiteProperty* <br/>- **SiteContent**_*SearchableSiteProperty*<br/><br/>Estos dos filtros son intercambiables; Por ejemplo `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` y `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` devolverá los resultados de la misma. Pero para ayudar a identificar lo que hace un filtro, se puede usar `Site_` para especificar las propiedades relacionadas con el sitio (por ejemplo, una dirección URL del sitio) y `SiteContent_` para especificar las propiedades relacionadas con el contenido (por ejemplo, tipos de documento. Por ejemplo, el filtro `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` permitiría que el usuario asignado este filtro para buscar solamente contenido en el https://contoso.spoppe.com/sites/doctors colección de sitios. El filtro `"SiteContent_FileExtension -eq 'docx'"` permitiría que el usuario asignado este filtro para buscar sólo documentos de Word (Word 2007 y versiones posterior).<br/><br/>Para obtener una lista de propiedades del sitio que admite búsquedas, consulte [Overview of rastreadas y propiedades administradas en SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=331599). Las propiedades marcadas con un **Sí** en la columna **Queryable** pueden usarse para crear un sitio o un filtro de contenido de sitio.<br/><br/> **Importante:** Un filtro de búsqueda único sólo puede tener un tipo de filtro; no puede contener un filtro de buzón de correo y un filtro de sitio; de forma similar, no puede contener un filtro de buzón de correo y un filtro de contenido de buzones de correo. Sin embargo, un filtro puede contener una consulta más compleja del mismo tipo. Por ejemplo,`"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`          |
| _Usuarios_|El parámetro _usuarios_ especifica los usuarios que obtener este filtro aplicado a sus búsquedas de contenido. Puesto que se trata de una propiedad de varios valor, que especifica un usuario o grupo de usuarios con este parámetro sobrescribirá la lista de usuarios existente. Vea los siguientes ejemplos de la sintaxis para agregar y quitar usuarios seleccionados.<br/><br/>También puede usar el parámetro de _los usuarios_ para especificar un valor bursátil &amp; grupo de roles de centro de cumplimiento. Un filtro de búsqueda de los permisos de grupo permite crear un grupo de roles personalizados y, a continuación, asignar dicha función. Por ejemplo, supongamos que tiene un grupo de funciones personalizadas para los administradores de exhibición de documentos electrónicos de la subsidiaria de Estados Unidos de una compañía multinacional. Puede usar el parámetro de _los usuarios_ para especificar este grupo de funciones (mediante el uso de la propiedad nombre del grupo de roles) y, a continuación, use el parámetro _Filter_ para permitir que sólo los buzones de correo en los Estados Unidos que se desea buscar.<br/><br/>Con este parámetro no es posible especificar grupos de distribución. |

## <a name="examples-of-changing-search-permissions-filters"></a>Ejemplos de cambio de filtros de búsqueda de permisos

Estos ejemplos muestran cómo usar los cmdlets **Get-ComplianceSecurityFilter** y **Set-ComplianceSecurityFilter** para agregar o quitar a la lista existente de los usuarios que el filtro se asigna a un usuario. Al agregar o quitar usuarios de un filtro, especifique el usuario mediante el uso de su dirección SMTP. 
  
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

El **Remove-ComplianceSecurityFilter** se usa para eliminar un filtro de búsqueda. Use el parámetro _FilterName_ para especificar el filtro que desee eliminar. 
  
## <a name="more-information"></a>Más información

- **Cómo buscar permisos filtrado trabajo?** El filtro de permisos se agrega a la consulta de búsqueda cuando se ejecuta una búsqueda de contenido. Básicamente, el filtro de permisos está unido a la consulta de búsqueda mediante el operador booleano **AND** . Por ejemplo, supongamos que tiene un filtro de permisos que permite Bob para llevar a cabo todas las acciones de búsqueda en los buzones de correo de los miembros del grupo de distribución de los trabajadores. A continuación, Bob ejecuta una búsqueda de contenido en todos los buzones de la organización con la consulta de búsqueda `sender:jerry@adatum.com`. Debido a que el filtro de permisos y la consulta de búsqueda lógicamente se combinan mediante un operador **AND** , la búsqueda devolverá los mensajes enviados por jerry@adatum.com a cualquier miembro del grupo de distribución de los trabajadores. 
    
- **¿Qué sucede si tiene varios filtros de búsqueda permisos?** En una consulta de búsqueda de contenido, se combinan los operadores booleanos **o** varios filtros de permisos. Por lo que se devolverán los resultados si alguno de los filtros es true. En una búsqueda de contenido, a continuación, se combinan todos los filtros (combinados por operadores **o** ) con la consulta de búsqueda por el operador **AND** . Vamos a echar el ejemplo anterior, donde un filtro de búsqueda permite Bob buscar sólo los buzones de correo de los miembros del grupo de distribución de los trabajadores. A continuación, creamos otro filtro que impide que Bob las búsquedas en buzón de Phil ("/ aliasDeBuzón - ne 'Phil'"). Y supongamos también que Phil es un miembro del grupo de procesos de trabajo. Cuando Bob ejecuta una búsqueda de contenido (desde el ejemplo anterior) en todos los buzones de la organización, se devolverán los resultados de búsqueda para el buzón de Phil aunque aplicar filtro para evitar que las búsquedas en buzón de Phil Bob. Esto es debido a que el primer filtro, que permite Bob buscar el grupo de procesos de trabajo, es true. Y debido a que Phil es un miembro del grupo de procesos de trabajo, Bob puede buscar el buzón de correo de Phil. 
    
- **De búsqueda permisos de filtrado de trabajo de buzones de correo inactivos?** Sí, puede usar el buzón de correo y filtros de contenido de buzones de correo para limitar quién puede buscar buzones inactivos en su organización. Al igual que un buzón normal, un buzón inactivo debe configurarse con la propiedad destinatario que se usa para crear un filtro de permisos. Si es necesario, puede usar el comando **Get-Mailbox-InactiveMailboxOnly** para mostrar las propiedades de buzones de correo inactivos. Para obtener más información, vea [crear y administrar buzones inactivos en Office 365](create-and-manage-inactive-mailboxes.md).
    
- **De búsqueda permisos de filtrado de trabajo para las carpetas públicas?** No. Como ha explicado anteriormente, búsqueda permisos filtrado no se puede usar para limitar quién puede buscar las carpetas públicas en Exchange. Por ejemplo, los elementos en ubicaciones de carpetas públicas no se puede excluir de los resultados de búsqueda por un filtro de permisos. 
    
- **Lo que permite a un usuario buscar todas las ubicaciones de contenido en un servicio específico también evitar que la búsqueda de ubicaciones de contenido en un servicio diferente?** No. Como se explica anteriormente, se debe crear un filtro de permisos de búsqueda para impedir explícitamente a los usuarios buscar ubicaciones de contenido en un servicio de Office 365 específico (por ejemplo, impide que un usuario buscar cualquier buzón de correo de Exchange o a cualquier sitio de SharePoint). En otras palabras, creación de un filtro de permisos de búsqueda que permite a un usuario buscar todos los sitios de SharePoint en la organización no impide que el usuario buscar buzones de correo. Por ejemplo, para permitir que los administradores de SharePoint buscar sólo los sitios de SharePoint, debe crear un filtro que impide que la búsqueda de buzones de correo. De forma similar, para permitir que los administradores de Exchange buscar sólo en buzones de correo, se debe crear un filtro que impide que la búsqueda de sitios.

---
title: Búsqueda de los buzones de correo basados en la nube para los usuarios locales en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/4/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: Use la herramienta de búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento para buscar y exportar datos de chat de MicrosoftTeams (denominados chats 1xN) para los usuarios locales en una implementación híbrida de Exchange.
ms.openlocfilehash: a504dfcf4c82bec036137b90312c01a0b2326ccc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536005"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users-in-office-365"></a>Búsqueda de los buzones de correo basados en la nube para los usuarios locales en Office 365

Si su organización tiene una implementación híbrida de Exchange y ha habilitado Microsoft Teams, los usuarios pueden usar la aplicación de chat de equipos para la mensajería instantánea. Para el usuario basada en la nube, se guardan los datos de chat de los equipos (también denominados 1xN chats) a su buzón principal basados en la nube. Cuando un usuario local usa la aplicación de chat de grupo, su buzón principal es encuentra local. Para evitar esta limitación, Microsoft ha publicado una nueva característica que se crea un área de almacenamiento de información basada en la nube (denominada un buzón de correo basados en la nube para usuarios locales) para almacenar datos de chat de los equipos de los usuarios locales. Esto le permite usar la herramienta de búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento para buscar y exportar datos de chat para los usuarios locales de los equipos. 
  
Estos son los requisitos y la limitación para la configuración y para configurar y los buzones de correo basados en la nube para los usuarios locales de búsqueda:
  
- Las cuentas de usuario en el servicio de directorio local (por ejemplo, Active Directory) deben sincronizarse con Azure Active Directory, el servicio de directorio en Office 365. Esto significa que una cuenta de usuario de correo se crea en Office 365 y está asociada con un usuario cuyo buzón de correo principal se encuentra en la organización local.
    
- El buzón de correo basados en la nube para los usuarios locales es datos del chat usados almacén sólo de los equipos. Un usuario local no se puede iniciar sesión en el buzón de correo basados en la nube o tener acceso de ninguna forma. No se puede utilizar para enviar o recibir mensajes de correo electrónico. 
    
- Se debe enviar una solicitud a Microsoft Support para habilitar la organización buscar datos de chat para los equipos en los buzones de correo basados en la nube para los usuarios locales. Vea [Archivando una solicitud con Microsoft Support para habilitar esta característica en la seguridad &amp; centro de cumplimiento](#filing-a-request-with-microsoft-support-to-enable-this-feature-in-the-security-amp-compliance-center) en este artículo. 
    
 **Nota:** Las conversaciones del canal de los equipos siempre se almacenan en el buzón de correo basados en la nube que está asociado con el equipo. Es decir, que puede usar la búsqueda de contenido a canal de búsqueda sin tengan conversaciones a una solicitud de soporte de archivo. Para obtener más información acerca de la búsqueda de los equipos de canal conversaciones, vea [Buscar en los equipos de Microsoft y los grupos de Office 365](content-search.md#searching-microsoft-teams-and-office-365-groups).
  
## <a name="how-it-works"></a>Funcionamiento

Si un usuario habilitado para los equipos de Microsoft tiene un buzón de correo local y su identidad y cuenta de usuario se han se sincroniza a la nube, Microsoft crea un buzón de correo basados en la nube para almacenar datos de chat de los equipos de 1xN. Después de que los datos de chat de los equipos se almacenan en el buzón de correo basados en la nube, se indizan para la búsqueda. Esto le permite usar la búsqueda de contenido (y búsquedas asociadas con los casos de exhibición de documentos electrónicos) para buscar, obtener una vista previa y exportar datos de chat de los equipos para los usuarios locales. También puede usar ** \*ComplianceSearch** cmdlets en la seguridad de Office 365 &amp; PowerShell de centro de cumplimiento para buscar los equipos de los datos de chat para los usuarios locales. 
  
El gráfico siguiente muestra el flujo de trabajo de cómo los equipos de chat datos para los usuarios de local está disponible para buscar, obtener una vista previa y exportar.
  
![Almacenamiento de información basada en la nube para los usuarios locales en Microsoft Teams](media/895845f8-2ceb-47ed-96c9-5ab7f1aea916.png)
  
Además de esta nueva capacidad, aún puede usar búsqueda de contenido para buscar, obtener una vista previa y exportar contenido en el sitio de SharePoint basada en la nube y el buzón de Exchange asociado a cada Microsoft Team y los equipos de 1xN datos de chat en el buzón de Exchange Online para los equipos usuarios basada en la nube.

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature-in-the-security-amp-compliance-center"></a>Presentar una solicitud con Microsoft Support para habilitar esta característica en la seguridad &amp; centro de cumplimiento

Debe presentar una solicitud con Microsoft Support para habilitar la organización usar la interfaz gráfica de usuario en la seguridad &amp; centro de cumplimiento para buscar datos de chat para los equipos en los buzones de correo basados en la nube para los usuarios locales. Tenga en cuenta que esta característica está disponible en Office 365 seguridad &amp; PowerShell de centro de cumplimiento. No es necesario que enviar una solicitud de soporte para usar PowerShell para buscar datos de chat de los equipos de los usuarios locales. 
  
Incluir la siguiente información al enviar la solicitud a Microsoft Support:
  
- El nombre de dominio predeterminado de la organización de Office 365.
    
- El nombre del inquilino y el identificador de inquilino de su organización de Office 365. Puede encontrar estos en el portal de Azure Active Directory (bajo **Administrar** \> **Propiedades**). Vea la sección [Buscar el identificador del inquilino de Office 365](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b).
    
- El título o la descripción del propósito de la solicitud de soporte técnico siguientes: "Habilitar la búsqueda de contenido de aplicación para los usuarios locales". Esto le ayudará a enrutar la solicitud para el equipo de ingeniería de exhibición de documentos electrónicos de Office 365 que implementará la solicitud. 
    
Después de realizar el cambio de ingeniería, Microsoft Support enviará una fecha de implementación estimado. Tenga en cuenta que el proceso de implementación realiza normalmente 2-3 semanas después de enviar la solicitud de soporte técnico. 
  
### <a name="what-happens-after-this-feature-is-enabled"></a>¿Qué sucede después de habilitar esta característica?

Después de esta característica se implementa en la organización de Office 365, los siguientes cambios se realizan en búsqueda de contenido y en las búsquedas asociadas con una exhibición de documentos electrónicos caso en la seguridad &amp; centro de cumplimiento:
  
- La casilla de verificación **Agregar Office contenido de aplicación para los usuarios locales** se agrega en las **ubicaciones** de búsqueda de contenido. 
    
    ![La casilla de verificación "Adición de contenido de la aplicación de Office para los usuarios de local" se agrega a la interfaz de usuario de búsqueda de contenido](media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- Los usuarios locales se muestran en el selector de ubicaciones de contenido que se utiliza para seleccionar los buzones de usuario de búsqueda. 
    

  
## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a>Búsqueda de contenido de chat los equipos en los buzones de correo basados en la nube para usuarios locales

Después de que se ha habilitado la característica, puede usar la búsqueda de contenido en la seguridad &amp; centro de cumplimiento para buscar datos de chat para los equipos en los buzones de correo basados en la nube para los usuarios locales. 
  
1. En la seguridad &amp; centro de cumplimiento, vaya a **búsqueda &amp; investigación** \> **búsqueda de contenido**
    
2. En la página de **búsqueda** , haga clic en ![icono Agregar](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **nueva búsqueda**.
    
    Como se explica anteriormente, se muestra la casilla de verificación **Agregar Office contenido de aplicación para los usuarios locales** en **ubicaciones**. Tenga en cuenta que está seleccionada de manera predeterminada.
    
3. Crear la consulta de palabra clave y agregar condiciones a la consulta de búsqueda si es necesario. Para buscar sólo equipo charlas datos, puede agregar la siguiente consulta en el cuadro **palabras clave** : 
    
    ```
    kind:im
    ``` 

4. En este momento, puede elegir una de las siguientes opciones en **las ubicaciones**:
    
    - **Todas las ubicaciones** : seleccione esta opción para buscar los buzones de correo de todos los usuarios de su organización. Cuando se selecciona la casilla de verificación, también se buscará en todos los buzones de correo basados en la nube para los usuarios locales. 
    
    - **Ubicaciones específicas** : seleccione esta opción y, a continuación, haga clic en **Modificar** \> elegir usuarios, grupos o equipos a buzones específicos de búsqueda. Como se explica anteriormente, el selector de ubicaciones le permitirá buscar usuarios locales. 
    
5. Guarde y ejecute la búsqueda. Pueden ser una vista previa de los resultados de búsqueda de los buzones de correo basados en la nube para los usuarios locales al igual que otros resultados de búsqueda. Además, puede puede exportar los resultados de búsqueda (incluidos los datos de chat de equipos) a un archivo PST. Para obtener más información, vea: 
    
    - [Crear una nueva búsqueda](content-search.md#create-a-new-search)
    
    - [Vista previa de los resultados de búsqueda](content-search.md#preview-search-results)
    
    - [Exportar los resultados de búsqueda de contenido de la seguridad de Office 365 &amp; centro de cumplimiento](export-search-results.md)
    
## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a>Uso de PowerShell para buscar datos de chat para los equipos en los buzones de correo basados en la nube para usuarios locales

Puede usar los cmdlets **New-ComplianceSearch** y **Set-ComplianceSearch** en la seguridad de Office 365 &amp; PowerShell de centro de cumplimiento para buscar el buzón de correo basados en la nube para los usuarios locales. Como se explica anteriormente, no es necesario que enviar una solicitud de soporte para usar PowerShell para buscar datos de chat de los equipos de los usuarios locales. 
  
1. [Conectarse a Office 365 seguridad &amp; centro de cumplimiento PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
    
2. Ejecute el siguiente PowerShell comando para crear un nuevo contenido busca en los buzones de correo basados en la nube de usuarios locales.
    
    ```
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```
   
    El parámetro *IncludeUserAppContent* se usa para especificar el buzón de correo basados en la nube para el usuario o los usuarios que se especifican mediante el parámetro *ExchangeLocation* . El *AllowNotFoundExchangeLocationsEnabled* permite que los buzones de correo basados en la nube para los usuarios locales. Al usar el `$true` valor para este parámetro, la búsqueda no intenta validar la existencia del buzón antes de que se ejecuta. Esto es necesario para buscar los buzones de correo basados en la nube para los usuarios locales porque no resuelven estos tipos de buzones como buzones regulares. 
    
    En el ejemplo siguiente se busca los equipos de chats (que son mensajes instantáneos) que contienen la palabra clave "redstone" en el buzón de correo basados en la nube de Sara Davis, que es un usuario local en la organización Contoso.
  
    ```
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   Después de crear una nueva búsqueda, asegúrese de usar el cmdlet **Start-ComplianceSearch** para ejecutar la búsqueda. 
  
Para obtener más información de uso de estos cmdlets, consulte:
  
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)
    
- [Set-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-compliancesearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)
    

## <a name="known-issues"></a>Problemas conocidos

- Actualmente, sólo se pueden exportar el contenido de los buzones de correo basados en la nube para, vista previa y búsqueda local a los usuarios. Colocar un buzón de correo basados en la nube para un usuario local en una suspensión asociada con una exhibición de documentos electrónicos caso o asignar a una directiva de retención de Office 365 no es compatible. 
    
- El selector de ubicación de contenido de documentos electrónicos contiene usuarios locales de muestra y le permiten activarlas. Sin embargo, como anteriormente con el procedimiento descrito que para el usuario local no se aplicará la suspensión.
    
## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

 **¿Dónde se encuentran los buzones de correo basados en la nube para los usuarios locales?**
  
Buzones de correo basados en la nube se crean y se almacenan en el mismo centro de datos como la organización de Office 365. 
  
 **¿Hay otros requisitos que no sean de enviar una solicitud de soporte técnico?**
  
 Como se explica anteriormente, se deben sincronizar las identidades de los usuarios con buzones on prem a su organización basada en la nube para que se cree una cuenta de usuario de correo correspondiente para cada cuenta de usuario local en Office 365. Además, su organización debe tener una suscripción a enterprise de Office 365, como una suscripción a Office 365 Enterprise E1, E3 o E5. 
  
 **¿Hay un riesgo de perder los datos de chat de los equipos si el buzón del usuario local se migra a la nube?**
  
No. Cuando se migra el buzón principal de un usuario local a la nube, los datos de chat de los equipos de dicho usuario se migrará a su nuevo buzón principal basados en la nube.
  
 **¿Se puede aplicar una exhibición de documentos electrónicos o las directivas de retención de Office 365 a los usuarios de local?**
  
No.
  
 **¿Puede buscar contenido búsqueda equipos antiguos charlas para los usuarios locales antes de la hora de mi organización envió la solicitud para habilitar esta característica?**
  
Microsoft inició almacenar los datos de chat de los equipos de los usuarios locales en el 31 de enero de 2018. Por lo tanto, si la identidad de un usuario de los equipos locales ha sido sincronizada entre Active Directory y Azure Active Directory desde esta fecha, sus datos de los equipos de chat se almacenará en un buzón de correo basados en la nube y pueden buscar mediante la búsqueda de contenido. Microsoft también está trabajando al almacenar datos de chat de los equipos desde antes del 31 de enero de 2018 en los buzones de correo basados en la nube para los usuarios locales. Para obtener más información acerca de este pronto estará disponible.

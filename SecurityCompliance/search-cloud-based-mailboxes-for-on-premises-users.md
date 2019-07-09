---
title: Buscar buzones de correo basados en la nube para usuarios locales en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/4/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: Use la herramienta de búsqueda de contenido en el centro de seguridad & cumplimiento para buscar y exportar datos de chat de Microsoft Teams (denominados 1xN chats) para usuarios locales en una implementación híbrida de Exchange.
ms.openlocfilehash: b08e1ea9ea9fb9fe834bb10948be532cbc4337b4
ms.sourcegitcommit: 6b2ca6bd153d24a717d6c537efd2d41d35c20a0b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35587807"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users-in-office-365"></a>Buscar buzones de correo basados en la nube para usuarios locales en Office 365

Si su organización tiene una implementación híbrida de Exchange y ha habilitado Microsoft Teams, los usuarios pueden usar la aplicación de chat de Microsoft Teams para mensajería instantánea. En el caso del usuario basado en la nube, los datos de chat de Microsoft Teams (también denominados chats 1xN) se guardan en el buzón de correo basado en la nube principal. Cuando un usuario local usa la aplicación de chat de equipo, su buzón principal se encuentra local. Para superar esta limitación, Microsoft ha lanzado una nueva característica en la que se crea un área de almacenamiento basada en la nube (denominada buzón basado en la nube para usuarios locales) para almacenar los datos de chat de Teams para los usuarios locales. Esto le permite usar la herramienta de búsqueda de contenido en el centro de seguridad & cumplimiento para buscar y exportar los datos de chat de Microsoft Teams para los usuarios locales. 
  
Estos son los requisitos y la limitación para configurar y configurar y buscar buzones de correo basados en la nube para los usuarios locales:
  
- Las cuentas de usuario del servicio de directorio local (como Active Directory) deben estar sincronizadas con Azure Active Directory, el servicio de directorio en Office 365. Esto significa que se crea una cuenta de usuario de correo en Office 365 y se asocia a un usuario cuyo buzón principal está ubicado en la organización local.
    
- El buzón basado en la nube para los usuarios locales solo se usa para almacenar datos de chat de Teams. Un usuario local no puede iniciar sesión en el buzón de correo o el acceso basado en la nube de ninguna manera. No se puede usar para enviar o recibir mensajes de correo electrónico. 
    
- Tiene que enviar una solicitud al soporte técnico de Microsoft para permitir que su organización busque los datos de chat de Teams en los buzones de correo basados en la nube de los usuarios locales. Vea el artículo [sobre cómo archivar una solicitud con el soporte técnico de Microsoft para habilitar esta característica](#filing-a-request-with-microsoft-support-to-enable-this-feature) . 
    
 **Nota:** Las conversaciones del canal de Teams siempre se almacenan en el buzón de correo basado en la nube que está asociado al equipo. Esto significa que puede usar la búsqueda de contenido para buscar conversaciones de canal sin tener que archivar una solicitud de soporte técnico. Para obtener más información sobre las conversaciones del canal de búsqueda en Teams, consulte [Searching Microsoft Teams and Office 365 Groups](content-search.md#searching-microsoft-teams-and-office-365-groups).
  
## <a name="how-it-works"></a>Cómo funciona

Si un usuario habilitado para Microsoft Teams tiene un buzón de correo local y su cuenta de usuario/identidad se ha sincronizado en la nube, Microsoft crea un buzón de correo basado en la nube para almacenar los datos de chat de 1xN Teams. Una vez que los datos de chat de Microsoft Teams se almacenan en el buzón basado en la nube, se indizan para la búsqueda. Esto le permite usar la búsqueda de contenido (y las búsquedas asociadas con casos de eDiscovery) para buscar, obtener una vista previa y exportar los datos de chat de Microsoft Teams a los usuarios locales. También puede usar ** \*** los cmdlets de ComplianceSearch en el PowerShell del centro de cumplimiento de & de seguridad para buscar los datos de chat de Microsoft Teams para los usuarios locales. 
  
En el gráfico siguiente se muestra el flujo de trabajo de cómo los datos de chat de Teams para usuarios locales están disponibles para la búsqueda, la vista previa y la exportación.
  
![Almacenamiento basado en la nube para usuarios locales en Microsoft Teams](media/895845f8-2ceb-47ed-96c9-5ab7f1aea916.png)
  
Además de esta nueva capacidad, puede usar la búsqueda de contenido para buscar, obtener una vista previa y exportar contenido de Teams en el sitio de SharePoint basado en la nube y el buzón de correo de Exchange asociado con cada equipo de Microsoft y 1xN los datos de chat del buzón de correo de Exchange Online para usuarios basados en la nube.

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature"></a>Presentación de una solicitud con el soporte técnico de Microsoft para habilitar esta característica

Debe archivar una solicitud con soporte técnico de Microsoft para permitir que su organización use la interfaz gráfica de usuario del centro de seguridad & cumplimiento para buscar los datos de chat de Microsoft Teams en los buzones de correo basados en la nube para los usuarios locales. Esta característica está disponible en PowerShell del centro de cumplimiento de & de seguridad. No tiene que enviar una solicitud de soporte técnico para usar PowerShell para buscar los datos de chat de Microsoft Teams para los usuarios locales. 
  
Incluya la siguiente información cuando envíe la solicitud a soporte técnico de Microsoft:
  
- El nombre de dominio predeterminado de su organización de Office 365.
    
- El nombre del espacio empresarial y el identificador de inquilino de su organización de Office 365. Puede encontrarlos en el portal de Azure Active Directory (en **Manage** \> **Properties**). Vea [Buscar el identificador de inquilino de Office 365](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b).
    
- El título o la descripción siguiente del propósito de la solicitud de soporte técnico: "habilitar la búsqueda de contenido de la aplicación para usuarios locales". Esto ayuda a enrutar la solicitud al equipo de ingeniería de exhibición de documentos electrónicos de Office 365 que va a implementar la solicitud. 
    
Una vez realizado el cambio de ingeniería, el soporte técnico de Microsoft le enviará una fecha de implementación estimada. El proceso de implementación suele tardar 2-3 semanas después de enviar la solicitud de soporte técnico. 
  
### <a name="what-happens-after-this-feature-is-enabled"></a>¿Qué ocurre después de habilitar esta característica?

Una vez implementada esta característica en la organización de Office 365, se realizan los siguientes cambios en la búsqueda de contenido y en las búsquedas asociadas a un caso de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento:
  
- La casilla **agregar contenido de aplicación de Office a los usuarios locales** se agrega en las **ubicaciones** en la búsqueda de contenido. 
    
    ![La casilla "agregar contenido de la aplicación de Office para usuarios locales" se agrega a la interfaz de usuario de búsqueda de contenido](media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- Los usuarios locales se muestran en el selector de ubicaciones de contenido que se usan para seleccionar los buzones de usuario que se van a buscar. 
    

  
## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a>Búsqueda de contenido de chat de Microsoft Teams en buzones de correo basados en la nube para usuarios locales

Una vez habilitada la característica, puede usar la búsqueda de contenido en el centro de seguridad & cumplimiento para buscar los datos de chat de Microsoft Teams en los buzones de correo basados en la nube para los usuarios locales. 
  
1. En el centro de seguridad & cumplimiento, vaya a búsqueda de **contenido** de **búsqueda** \> .
    
2. En la página **Buscar** , haga ![clic en](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) agregar icono **nueva búsqueda**.
    
    Como se ha explicado anteriormente, la casilla de verificación **agregar contenido de aplicación de Office a los usuarios locales** se muestra en **ubicaciones**. Está seleccionada de forma predeterminada.
    
3. Cree la consulta de palabra clave y agregue condiciones a la consulta de búsqueda si es necesario. Para buscar solo los datos de los chats de equipo, puede Agregar la siguiente consulta en el cuadro **palabras clave** : 
    
    ```
    kind:im
    ``` 

4. En este punto, puede elegir una de las siguientes opciones en **ubicaciones**:
    
    - **Todas las ubicaciones** : Seleccione esta opción para buscar en los buzones de todos los usuarios de la organización. Cuando se selecciona la casilla, también se buscará en todos los buzones de correo basados en la nube de los usuarios locales. 
    
    - **Ubicaciones específicas** : Seleccione esta opción y, a continuación, haga clic en **modificar** \> elija usuarios, grupos o equipos para buscar en buzones específicos. Como se ha explicado anteriormente, el selector de ubicaciones le permite buscar usuarios locales. 
    
5. Guarde y ejecute la búsqueda. Se puede obtener una vista previa de los resultados de búsqueda de los buzones basados en la nube para los usuarios locales como cualquier otro resultado de búsqueda. También puede exportar los resultados de la búsqueda (incluidos los datos de chat de los equipos) a un archivo PST. Para obtener más información, vea: 
    
    - [Create a search](content-search.md#create-a-search)
    
    - [Preview search results](content-search.md#preview-search-results)
    
    - [Exportar resultados de la búsqueda de contenido](export-search-results.md)
    
## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a>Uso de PowerShell para buscar datos de chat de Microsoft Teams en buzones de correo basados en la nube para usuarios locales

Puede usar los cmdlets **New-compliancesearch** y **set-ComplianceSearch** en el PowerShell del centro de cumplimiento de & de seguridad para buscar en el buzón de correo basado en nube para los usuarios locales. Como se ha explicado anteriormente, no tiene que enviar una solicitud de soporte técnico para usar PowerShell para buscar los datos de chat de Microsoft Teams para los usuarios locales. 
  
1. [Conéctese al centro de seguridad & PowerShell del centro de cumplimiento](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
    
2. Ejecute el siguiente comando de PowerShell para crear una búsqueda de contenido que busque los buzones de correo basados en la nube de los usuarios locales.
    
    ```
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```
   
    El parámetro *IncludeUserAppContent* se usa para especificar el buzón basado en la nube para el usuario o los usuarios especificados por el parámetro *ExchangeLocation* . El *AllowNotFoundExchangeLocationsEnabled* permite buzones de correo basados en la nube para los usuarios locales. Cuando se usa el `$true` valor para este parámetro, la búsqueda no intenta validar la existencia del buzón antes de ejecutarse. Esto es necesario para buscar los buzones de correo basados en la nube para los usuarios locales porque estos tipos de buzones no se resuelven como buzones normales. 
    
    En el siguiente ejemplo se buscan chats de Microsoft Teams (que son mensajes instantáneos) que contienen la palabra clave "Redstone" en el buzón de correo basado en la nube de Sara Davis, que es un usuario local de la organización de contoso.
  
    ```
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   Después de crear una búsqueda, asegúrese de usar el cmdlet **Start-ComplianceSearch** para ejecutar la búsqueda. 
  
Para obtener más información sobre el uso de estos cmdlets, consulte:
  
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)
    
- [Set-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-compliancesearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)
    

## <a name="known-issues"></a>Problemas conocidos

- Actualmente, solo puede buscar, obtener una vista previa y exportar el contenido de los buzones basados en la nube para los usuarios locales. No se admite la colocación de un buzón basado en la nube para un usuario local en una retención asociada con un caso de exhibición de documentos electrónicos o la asignación a una directiva de retención de Office 365. 
    
- El selector de ubicación de contenido para eDiscovery muestra los usuarios locales y le permitirá seleccionarlos. Sin embargo, como se explicó anteriormente, la retención no se aplicará al usuario local.
    
## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

 **¿Dónde se encuentran los buzones de correo basados en la nube para los usuarios locales?**
  
Los buzones de correo basados en la nube se crean y almacenan en el mismo centro de recursos que la organización de Office 365. 
  
 **¿Hay otros requisitos que no sean el envío de una solicitud de soporte técnico?**
  
 Como se ha explicado anteriormente, las identidades de los usuarios con buzones locales deben sincronizarse con la organización basada en la nube para que se cree una cuenta de usuario de correo correspondiente para cada cuenta de usuario local en Office 365. La organización también debe tener una suscripción de Office 365 Enterprise, como una suscripción de Office 365 Enterprise E1, E3 o E5. 
  
 **¿Existe el riesgo de perder los datos de chat de Microsoft Teams si el buzón de correo local del usuario se migra a la nube?**
  
No. Al migrar el buzón principal de un usuario local a la nube, los datos de chat de Microsoft Teams para ese usuario se migrarán a su nuevo buzón principal basado en la nube.
  
 **¿Puedo aplicar una retención de exhibición de documentos electrónicos o directivas de retención de Office 365 a los usuarios locales?**
  
No.
  
 **¿Puede buscar contenido buscar chats más antiguos de Microsoft Teams para los usuarios locales antes del tiempo que mi organización envió la solicitud para habilitar esta característica?**
  
Microsoft inició el almacenamiento de los datos de chat de Microsoft Teams para los usuarios locales el 31 de enero de 2018. Por lo tanto, si la identidad de un usuario de Microsoft Teams se ha sincronizado entre Active Directory y Azure Active Directory desde esta fecha, los datos de chat de su equipo se almacenarán en un buzón de correo basado en la nube y se podrán buscar mediante la búsqueda de contenido. Microsoft también está trabajando en almacenar datos de chat de Microsoft Teams desde antes del 31 de enero de 2018 en los buzones de correo basados en la nube para los usuarios locales. Pronto estará disponible más información sobre esto.

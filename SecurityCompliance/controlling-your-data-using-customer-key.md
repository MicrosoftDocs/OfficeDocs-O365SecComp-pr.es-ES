---
title: Controlar los datos en Office 365 con la clave de cliente
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/1/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo configurar la clave de cliente de Office 365 para Exchange Online, Skype empresarial, SharePoint Online y OneDrive para la empresa. Con la clave de cliente, puede controlar las claves de cifrado de la organización y, después, configurar Office 365 para usarlas y cifrar los datos en reposo en los centros de datos de Microsoft.
ms.openlocfilehash: 219ddb94727cd2b708f734a77a8397b3bc3f1064
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258358"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a>Controlar los datos en Office 365 con la clave de cliente

Con la clave de cliente, puede controlar las claves de cifrado de la organización y, después, configurar Office 365 para usarlas y cifrar los datos en reposo en los centros de datos de Microsoft. Es decir, la clave de cliente permite a los clientes agregar una capa de cifrado que les pertenece, con sus claves. Los datos en reposo incluyen datos de Exchange Online y Skype Empresarial que se almacenan en buzones y archivos en SharePoint Online y OneDrive para la Empresa.
  
Debe configurar Azure antes de poder usar la clave de cliente de Office 365. En este tema se describen los pasos que debe seguir para crear y configurar los recursos necesarios de Azure y, a continuación, se proporcionan los pasos para configurar la clave de cliente en Office 365. Una vez completada la configuración de Azure, determine qué directivas y, por lo tanto, qué claves asignar a los buzones de correo y los archivos de su organización. Los buzones de correo y los archivos para los que no se asigna una directiva usarán directivas de cifrado controladas y administradas por Microsoft. Para obtener más información acerca de la clave de cliente o para obtener una introducción general, consulte la [clave de cliente de preguntas más frecuentes sobre Office 365](service-encryption-with-customer-key-faq.md).
  
> [!IMPORTANT]
> Se recomienda encarecidamente seguir los procedimientos recomendados de este tema. Se les llama como **Tip** e **Important**. La clave de cliente le da control sobre las claves de cifrado raíz cuyo ámbito puede ser tan grande como toda la organización. Esto significa que los errores realizados con estas claves pueden tener un gran impacto y pueden dar lugar a interrupciones en el servicio o la pérdida irrevocable de los datos. 
  
## <a name="before-you-begin-setting-up-customer-key"></a>Antes de comenzar a configurar la clave de cliente
<a name="Beforeyoustart"> </a>

Antes de empezar, asegúrese de que dispone de la licencia adecuada para su organización. La clave de cliente en Office 365 se ofrece en Office 365 E5 o en la SKU de cumplimiento avanzada.
  
A continuación, para comprender los conceptos y los procedimientos de este tema, debe revisar la documentación de [Azure Key Vault](https://azure.microsoft.com/en-us/documentation/services/key-vault/) . Además, familiarícese con los términos que se usan en Azure, por ejemplo, [tenant](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).
  
Para proporcionar comentarios sobre la clave de cliente, incluida la documentación, envíe sus ideas, sugerencias y perspectivas a customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a>Información general sobre la configuración de la clave de cliente de Office 365
<a name="Overview"> </a>

Para configurar la clave de cliente, deberá completar estas tareas. En el resto de este tema se proporcionan instrucciones detalladas para cada tarea o vínculos a más información para cada paso del proceso.
  
**En Azure y Microsoft FastTrack:**
  
Completará la mayoría de estas tareas conectándose de forma remota a Azure PowerShell. Para obtener los mejores resultados, use la versión 4.4.0 o posterior de Azure PowerShell.
  
- [Crear dos nuevas suscripciones de Azure](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [Registrar suscripciones de Azure para usar un período de retención obligatorio](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    El registro puede tardar de uno a cinco días hábiles.
    
- [Enviar una solicitud para activar la clave de cliente de Office 365](controlling-your-data-using-customer-key.md#FastTrack)
    
    Una vez que haya creado las dos nuevas suscripciones de Azure, deberá enviar la solicitud de oferta de la clave de cliente correspondiente completando un formulario web hospedado en el portal de Microsoft FastTrack. **El equipo de FastTrack no proporciona asistencia con la clave de cliente. Office simplemente usa el portal de FastTrack para permitirle enviar el formulario y ayudar a hacer un seguimiento de las ofertas relevantes para la clave de cliente**.
  
Una vez que haya enviado una oferta de clave de cliente, Microsoft revisa su solicitud y le notifica Cuándo puede continuar con el resto de las tareas de configuración. Este proceso puede tardar hasta cinco días hábiles.
    
- [Crear un almacén de claves Premium de Azure en cada suscripción](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [Asignar permisos a cada almacén clave](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [Habilitar y, a continuación, confirmar la eliminación de software en los depósitos clave](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [Agregar una clave a cada depósito clave creando o importando una clave](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [Comprobar el nivel de recuperación de las claves](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [Copia de seguridad de Azure Key Vault](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [Validar las opciones de configuración de Azure Key Vault](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [Obtener el URI para cada clave de Azure Key Vault](controlling-your-data-using-customer-key.md#GetKeyURI)
    
**En Office 365:**
  
Exchange Online y Skype empresarial:
  
- [Crear una directiva de cifrado de datos (DEP) para su uso con Exchange Online y Skype empresarial](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [Asignar una DEP a un buzón](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [Validar el cifrado de buzones](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
SharePoint Online y OneDrive para la empresa:
  
- [Crear una directiva de cifrado de datos (DEP) para cada geográfico de SharePoint Online y OneDrive para la empresa](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [Validar el cifrado de sitios de grupo, sitios de grupo y OneDrive para la empresa](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Completar las tareas en Azure Key Vault y Microsoft FastTrack para la clave de cliente
<a name="AzureSteps"> </a>

Complete estas tareas en Azure Key Vault para configurar la clave de cliente de Office 365. Deberá completar estos pasos independientemente de si desea configurar la clave de cliente para Exchange Online y Skype empresarial o SharePoint Online y OneDrive para la empresa, o para todos los servicios admitidos en Office 365.
  
### <a name="create-two-new-azure-subscriptions"></a>Crear dos nuevas suscripciones de Azure
<a name="Create2newsubs"> </a>

Se requieren dos suscripciones de Azure para la clave de cliente. Como práctica recomendada, Microsoft recomienda crear nuevas suscripciones de Azure para usarlas con la clave de cliente. Las claves de Azure Key Vault solo se pueden autorizar para aplicaciones en el mismo inquilino de Azure Active Directory (AAD), debe crear las nuevas suscripciones con el mismo inquilino de Azure AD que se usa con la organización de Office 365 donde se asignará la DEPs. Por ejemplo, con su cuenta profesional o educativa con privilegios de administrador global en su organización de Office 365. Para obtener los pasos detallados, consulte [registrarse para Azure como organización](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/).
  
> [!IMPORTANT]
> La clave de cliente requiere dos claves para cada directiva de cifrado de datos (DEP). Para ello, debe crear dos suscripciones de Azure. Como procedimiento recomendado, Microsoft recomienda que los miembros de la organización se configuren como una clave en cada suscripción. Además, estas suscripciones de Azure solo deben usarse para administrar claves de cifrado para Office 365. Esto protege a su organización en caso de que uno de sus operadores elimine accidentalmente, de forma intencionada, o de una mala administración de las claves de las que es responsable. <br/> Le recomendamos que configure nuevas suscripciones de Azure que solo se usan para administrar recursos de Azure Key Vault para usarlas con la clave de cliente. No hay ningún límite práctico en el número de suscripciones de Azure que puede crear para su organización. Siga estos procedimientos recomendados para minimizar el impacto de los errores humanos mientras ayuda a administrar los recursos usados por la clave de cliente. 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Enviar una solicitud para activar la clave de cliente de Office 365
<a name="FastTrack"> </a>

Una vez que haya completado los pasos de Azure, tendrá que enviar una solicitud de oferta en el [portal de Microsoft FastTrack](https://fasttrack.microsoft.com/). Una vez que haya enviado una solicitud a través del portal web FastTrack, Microsoft comprueba los datos de configuración de Azure Key Vault y la información de contacto que ha proporcionado. Las selecciones que realice en el formulario de oferta en relación con los agentes autorizados de su organización son críticas y necesarias para completar el registro de la clave de cliente. Los agentes de la organización que seleccione en el formulario se usarán para garantizar la autenticidad de cualquier solicitud de revocar y destruir todas las claves utilizadas con una directiva de clave de cifrado de datos de cliente. Deberá realizar este paso una vez para activar la cobertura del cliente para la cobertura de Exchange Online y Skype empresarial, y una segunda vez para activar la clave de cliente de SharePoint Online y OneDrive para la empresa.
  
Para enviar una oferta para activar la clave de cliente, siga estos pasos:
  
1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie sesión en el [portal de Microsoft FastTrack](https://fasttrack.microsoft.com/).
    
2. Una vez que haya iniciado sesión, vaya al **Panel**.
    
3. Elija **ofertas**y revise la lista de ofertas actuales.
    
4. Elija más **información** para la oferta que se le aplique: 
    
  - **Exchange Online y Skype empresarial:** Elija más **información** en la **clave de cliente de la oferta de Exchange** . 
    
  - **SharePoint Online y OneDrive para la empresa:** Elija más **información** sobre la oferta de **clave de cliente para SharePoint y OneDrive para la empresa** . 
    
5. En la página Detalles de la **oferta** , elija **crear solicitud**.
    
6. ReLlene todos los detalles aplicables y la información solicitada en el formulario de oferta. Preste especial atención a las selecciones de los funcionarios de su organización a los que desea conceder autorización para aprobar la destrucción permanente e irreversible de claves de cifrado y datos. Una vez que haya completado el formulario, elija **Enviar**.
    
    Este proceso puede tardar hasta cinco días hábiles una vez que se haya notificado a Microsoft de la solicitud.
    
7. Continúe con la sección período de retención obligatorio a continuación.
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrar suscripciones de Azure para usar un período de retención obligatorio
<a name="RegisterSubsforMRP"> </a>

La pérdida temporal o permanente de las claves de cifrado raíz puede ser muy disruptiva o incluso catastróficas para el funcionamiento del servicio y puede provocar la pérdida de datos. Por este motivo, los recursos usados con la clave de cliente requieren una protección segura. Todos los recursos de Azure que se usan con la clave de cliente ofrecen mecanismos de protección más allá de la configuración predeterminada. Las suscripciones de Azure se pueden etiquetar o registrar de manera que se evite la cancelación inmediata y irrevocable. Esto se conoce como registro de un período de retención obligatorio. Los pasos necesarios para registrar las suscripciones de Azure durante un período de retención obligatorio requieren la colaboración con el equipo de Office 365. Este proceso puede tardar de uno a cinco días laborables. Anteriormente, a veces se hacía referencia a esto como "no cancelar".
  
Antes de ponerse en contacto con el equipo de Office 365, debe realizar los siguientes pasos para cada suscripción de Azure que use con la clave de cliente:
  
1. Inicie sesión en su suscripción de Azure con Azure PowerShell. Para obtener instrucciones, vea [iniciar sesión con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).
    
2. Ejecute el cmdlet Register-AzureRmProviderFeature para registrar sus suscripciones para usar un período de retención obligatorio.
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. Póngase en contacto con Microsoft para finalizar el proceso. Para el equipo de SharePoint y OneDrive para la empresa, póngase en contacto con [Spock@microsoft.com](mailto:spock@microsoft.com). Para Exchange Online y Skype empresarial, póngase en contacto con [exock@microsoft.com](mailto:exock@microsoft.com). El contrato de nivel de servicio (SLA) para completar este proceso es cinco días hábiles después de que Microsoft haya notificado (y comprobado) que ha registrado sus suscripciones para usar un período de retención obligatorio. Incluya lo siguiente en su correo electrónico:
    
    **Asunto**: clave del cliente \<para *el nombre de dominio completo del espacio empresarial*\> 
    
    **Cuerpo**: identificadores de suscripción para los que desea finalizar el período de retención obligatorio. 
    
4. Una vez que reciba la notificación de Microsoft de que se ha completado el registro, compruebe el estado del registro ejecutando el cmdlet Get-AzureRmProviderFeature de la siguiente manera:
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. Después de comprobar que la propiedad de **Estado de registro** del cmdlet Get-AzureRmProviderFeature devuelve un valor de **registrado**, ejecute el siguiente comando para completar el proceso:
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Crear un almacén de claves Premium de Azure en cada suscripción
<a name="CreateKeyVault"> </a>

Los pasos para crear un almacén de claves se documentan en [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), que le guiará a través de la instalación y el inicio de Azure PowerShell, la conexión a su suscripción de Azure, la creación de un grupo de recursos y la creación de un almacén de claves en ese Grupo de recursos.
  
Al crear un almacén de claves, debe elegir una SKU: estándar o Premium. La SKU estándar permite que las claves de Azure Key Vault estén protegidas con software (no hay protección de clave de módulo de seguridad de hardware (HSM) y la SKU Premium permite usar los HSM para proteger las claves de la bóveda clave. La clave de cliente acepta almacenes clave que usan una SKU, pero Microsoft recomienda encarecidamente usar solo la SKU Premium. El costo de las operaciones con claves de cualquier tipo es el mismo, por lo que la única diferencia de costo es el costo cada mes para cada clave protegida por HSM. Consulte [tarifas clave](https://azure.microsoft.com/pricing/details/key-vault/) de la bóveda para obtener más información. 
  
> [!IMPORTANT]
> Use los almacenes clave de SKU Premium y las claves protegidas por HSM para los datos de producción y use únicamente las claves y los almacenes de claves de SKU estándar para fines de prueba y validación. 
  
Para cada servicio de Office 365 con el que va a usar la clave de cliente, cree un almacén de claves en cada una de las dos suscripciones de Azure que ha creado. Por ejemplo, solo para Exchange Online y Skype empresarial, o SharePoint Online y OneDrive para la empresa, solo se creará un par de depósitos. Para habilitar la clave de cliente para Exchange Online y SharePoint Online, deberá crear dos pares de depósitos clave.
  
Use una Convención de nomenclatura para los depósitos clave que refleje el uso previsto de la DEP con la que va a asociar los almacenes. Consulte la sección procedimientos recomendados a continuación para conocer las recomendaciones de Convención de nomenclatura.
  
Cree un conjunto independiente y emparejado de depósitos para cada directiva de cifrado de datos. Para Exchange Online, el ámbito de una directiva de cifrado de datos se elige cuando se asigna la Directiva al buzón. Un buzón puede tener solo una directiva asignada y puede crear hasta 50 directivas. Para SharePoint Online el ámbito de una Directiva son todos los datos de una organización en una ubicación geográfica o geográfica.
  
La creación de almacenes clave también requiere la creación de grupos de recursos de Azure, ya que las bóvedas clave necesitan capacidad de almacenamiento (aunque muy pequeña) y el registro de la bóveda clave, si está habilitado, también genera datos almacenados. Como procedimiento recomendado, Microsoft recomienda el uso de administradores independientes para administrar cada grupo de recursos, con la administración alineada con el conjunto de administradores que administrarán todos los recursos de clave de cliente relacionados.
  
> [!IMPORTANT]
> Para maximizar la disponibilidad, los depósitos clave deben estar en regiones próximos a su servicio de Office 365. Por ejemplo, si su organización de Exchange Online está en Norteamérica, ubique sus depósitos clave en Norteamérica. Si su organización de Exchange Online está en Europa, ubique los depósitos clave en Europa.<br/>Use un prefijo común para los depósitos clave e incluya una abreviatura del uso y el alcance de las claves y el almacén de claves (por ejemplo, para el servicio de SharePoint de Contoso donde los almacenes se ubicarán en Norteamérica, un posible par de nombres es contoso-O365SP-NA-VaultA1 y Contoso-O365SP-NA-VaultA2. Los nombres de almacén son cadenas únicas de forma global dentro de Azure, por lo que es posible que deba probar variantes de sus nombres deseados en caso de que otros clientes de Azure ya hayan reclamado los nombres deseados. A partir de julio 2017 los nombres de almacén no se pueden cambiar, por lo que un procedimiento recomendado es tener un plan escrito para la configuración y usar una segunda persona para comprobar que el plan se ejecuta correctamente.<br/>Si es posible, cree sus depósitos en regiones no emparejadas. Las regiones de Azure emparejadas proporcionan alta disponibilidad en todos los dominios de error de servicio. Por lo tanto, los pares regionales pueden considerarse como una región de copia de seguridad de cada uno. Esto significa que un recurso de Azure que se coloca en una región está obteniendo automáticamente la tolerancia a errores a través de la región emparejada. Por este motivo, la elección de regiones para dos almacenes usados en una DEP en la que las regiones están emparejadas significa que solo se usa un total de dos regiones de disponibilidad. La mayoría de las zonas geográficas solo tienen dos regiones, por lo que todavía no es posible seleccionar regiones no emparejadas. Si es posible, elija dos regiones no emparejadas para los dos almacenes usados con DEP. Esto beneficia de un total de cuatro regiones de disponibilidad. Para obtener más información, vea [continuidad empresarial y recuperación ante desastres (BCDR): regiones emparejadas de Azure](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) para obtener una lista actual de pares regionales. 
  
### <a name="assign-permissions-to-each-key-vault"></a>Asignar permisos a cada almacén clave
<a name="KeyVaultPerms"> </a>

Para cada almacén de claves, tendrá que definir tres conjuntos de permisos distintos para la clave de cliente, según la implementación. Por ejemplo, tendrá que definir un conjunto de permisos para cada uno de los siguientes elementos:
  
- **Administradores de la bóveda clave** que realizarán la administración cotidiana de su almacén clave para su organización. Estas tareas incluyen copia de seguridad, crear, obtener, importar, enumerar y restaurar. 
    
    > [!IMPORTANT]
    > El conjunto de permisos asignado a los administradores de la bóveda de claves no incluye el permiso para eliminar claves. Esto es intencionado y es un ejercicio importante. La eliminación de claves de cifrado no suele realizarse, ya que al hacerlo se destruyen los datos de forma permanente. Como procedimiento recomendado, no conceda este permiso a los administradores de la bóveda clave de forma predeterminada. En su lugar, Reserve esto para los colaboradores clave de la bóveda y asígnelo solo a un administrador a corto plazo una vez que comprenda claramente las consecuencias. 
  
    Para asignar estos permisos a un usuario de su organización de Office 365, inicie sesión en su suscripción de Azure con Azure PowerShell. Para obtener instrucciones, vea [iniciar sesión con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).
    
- Ejecute el cmdlet Set-AzureRmKeyVaultAccessPolicy para asignar los permisos necesarios.
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  Por ejemplo:
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- Contribute de **key Vault** que puede cambiar los permisos en el propio almacén de claves de Azure. Tendrá que cambiar estos permisos a medida que los empleados abandonen o se unan a su equipo, o en la situación extremadamente inusual de que los administradores de la bóveda clave necesiten de forma legítima permiso para eliminar o restaurar una clave. Este conjunto de colaboradores clave del almacén debe tener concedido el **** rol colaborador en su almacén de claves. Puede asignar este rol mediante el administrador de recursos de Azure. Para obtener los pasos detallados, consulte [usar el control de acceso basado en roles para administrar el acceso a los recursos de suscripción de Azure](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). El administrador que crea una suscripción tiene este acceso de forma implícita, así como la capacidad de asignar otros administradores al rol colaborador.
    
- Si tiene previsto usar la clave de cliente con Exchange Online y Skype empresarial, debe conceder permiso a Office 365 para usar el almacén de claves en nombre de Exchange Online y Skype empresarial. Del mismo modo, si tiene previsto usar la clave de cliente con SharePoint Online y OneDrive para la empresa, necesitará agregar el permiso para que la oficina 365 use el almacén de claves en nombre de SharePoint Online y OneDrive para la empresa. Para conceder permiso a Office 365, ejecute el cmdlet **set-AzureRmKeyVaultAccessPolicy** con la siguiente sintaxis: 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    Donde:
    
  - *vaultname* es el nombre del almacén de claves que ha creado. 
    
  - Para Exchange Online y Skype empresarial, reemplace *Office 365 appID* por`00000002-0000-0ff1-ce00-000000000000`
    
  - Para SharePoint Online y OneDrive para la empresa, reemplace *Office 365 appID* por`00000003-0000-0ff1-ce00-000000000000`
    
  Ejemplo: establecer permisos para Exchange Online y Skype empresarial:
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  Ejemplo: establecer permisos para SharePoint Online y OneDrive para la empresa
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Habilitar y, a continuación, confirmar la eliminación de software en los depósitos clave
<a name="SoftDelete"> </a>

Cuando puede recuperar rápidamente las claves, es menos probable que experimente una interrupción del servicio prolongada debido a claves eliminadas accidental o malintencionadamente. Debe habilitar esta configuración, que se conoce como eliminación temporal, para poder usar las claves con la clave de cliente. La habilitación de la eliminación temporal permite recuperar claves o depósitos en un plazo de 90 días de eliminación sin tener que restaurarlos a partir de la copia de seguridad.
  
Para habilitar la eliminación temporal en los almacenes clave, siga estos pasos:
  
1. Inicie sesión en su suscripción de Azure con Windows PowerShell. Para obtener instrucciones, vea [iniciar sesión con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).
    
2. Ejecute el cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) . En este ejemplo, *vaultname* es el nombre del almacén de claves para el que se va a habilitar la eliminación temporal: 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. Confirme que la eliminación de software está configurada para el almacén de claves mediante la ejecución del cmdlet **Get-AzureRmKeyVault** . Si la eliminación temporal está configurada correctamente para el almacén de claves, ¿está habilitada la eliminación temporal? Devuelve un valor de **true**: 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Agregar una clave a cada depósito clave creando o importando una clave
<a name="AddKeystoKeyVault"> </a>

Hay dos formas de agregar claves a un almacén de claves de Azure; puede crear una clave directamente en el almacén de claves, o puede importar una clave. La creación de una clave directamente en el almacén de claves es el método menos complicado, mientras que la importación de una clave proporciona un control total sobre la forma en que se genera la clave.
  
Para crear una clave directamente en el almacén de claves, ejecute el cmdlet [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) de la siguiente manera: 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Donde:
  
-  *vaultname* es el nombre del almacén de claves en el que desea crear la clave. 
    
-  *keyName* es el nombre que desea asignar a la nueva clave. 
    
    > [!TIP]
    > Denomine claves con una Convención de nomenclatura similar, como se ha descrito anteriormente para los almacenes de claves. De este modo, en las herramientas que solo muestran el nombre de la clave, la cadena es autodescriptivo. 
  
- Si piensa proteger la clave con un HSM, asegúrese de especificar **HSM** como el valor del parámetro _Destination_ ; de lo contrario, especifique el **software**.
    
For example,
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

Para importar una clave directamente en el almacén de claves, debe tener un módulo de seguridad de hardware de Thales nShield.
  
Algunas organizaciones prefieren este enfoque para establecer la procedencia de sus claves y este método también ofrece lo siguiente:
  
- El conjunto de herramientas usado para la importación incluye atestación de Thales de que la clave de intercambio de claves (KEK) que se usa para cifrar la clave que genera no es exportable y se genera dentro de un HSM genuino fabricado por Thales.
    
- El conjunto de herramientas incluye atestación de Thales que el mundo de seguridad de la clave de Azure también se generó en un HSM auténtico fabricado por Thales. Esta atestación le demuestra que Microsoft también usa hardware de Thales genuino.
    
Consulte a su grupo de seguridad para determinar si se requieren las atestaciones anteriores. Para obtener instrucciones detalladas para crear una clave local e importarla en el almacén de claves, consulte [How to generaTE HSM-Protected Keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Use las instrucciones de Azure para crear una clave en cada almacén de clave.
  
### <a name="check-the-recovery-level-of-your-keys"></a>Comprobar el nivel de recuperación de las claves
<a name="CheckKeyRecoveryLevel"> </a>

Office 365 requiere que la suscripción de Azure Key Vault esté definida como no cancelar y que las claves usadas por la clave de cliente tengan habilitada la eliminación temporal. Para confirmarlo, consulte el nivel de recuperación de las claves.
  
Para comprobar el nivel de recuperación de una clave, en Azure PowerShell, ejecute el cmdlet Get-AzureKeyVaultKey de la siguiente manera:
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

Si la propiedad _nivel de recuperación_ devuelve cualquier cosa que no sea un valor recuperable **+ ProtectedSubscription**, tendrá que revisar este tema y asegurarse de que ha seguido todos los pasos para poner la suscripción en la lista no cancelar y que tiene habilitada la eliminación temporal en cada uno de los almacenes clave.
  
### <a name="backup-azure-key-vault"></a>Copia de seguridad de Azure Key Vault
<a name="BackupAzureKeyVaultkeys"> </a>

Inmediatamente después de la creación o de cualquier cambio en una clave, realice una copia de seguridad y almacene copias de la copia de seguridad, tanto en línea como sin conexión. Las copias sin conexión no deben estar conectadas a ninguna red, como en un servicio de almacenamiento comercial o seguro físico. Al menos una copia de la copia de seguridad debe almacenarse en una ubicación a la que se pueda tener acceso en caso de desastre. Los blobs de copia de seguridad son los únicos medios de restaurar el material clave en caso de que una clave de almacén clave se destruya de forma permanente o no pueda ser procesada de forma inservible. Las claves externas a Azure Key Vault y que se importaron a Azure Key Vault no se califican como una copia de seguridad porque los metadatos necesarios para que la clave de cliente use la clave no existe con la clave externa. Solo se puede usar una copia de seguridad tomada de Azure Key Vault para las operaciones de restauración con la clave de cliente. Por lo tanto, es fundamental realizar una copia de seguridad del almacén de claves de Azure una vez que se haya cargado o creado una clave.
  
Para crear una copia de seguridad de una clave de Azure Key Vault, ejecute el cmdlet [backup-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) de la siguiente manera:
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

Asegúrese de que el archivo de salida Use `.backup`el sufijo.
  
El archivo de salida resultante de este cmdlet está cifrado y no se puede usar fuera de Azure Key Vault. La copia de seguridad solo se puede restaurar a la suscripción de Azure desde la que se realizó la copia de seguridad.
  
> [!TIP]
> Para el archivo de salida, elija una combinación del nombre de la caja fuerte y el nombre de la clave. Esto hará que el nombre de archivo se describa automáticamente. También se asegurará de que los nombres de archivo de copia de seguridad no entren en conflicto. 
  
Por ejemplo:
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Validar las opciones de configuración de Azure Key Vault
<a name="Validateconfiguration"> </a>

La validación antes de usar claves en un DEP es opcional, pero se recomienda encarecidamente. En particular, si usa los pasos para configurar las claves y los almacenes distintos de los que se describen en este tema, debe validar el estado de los recursos de Azure Key Vault antes de configurar la clave de cliente.
  
Para comprobar que las claves tienen las operaciones GET, wrapKey y unwrapKey habilitadas:
  
Ejecute el cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) de la siguiente manera: 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

En el resultado, busque la Directiva de acceso y la identidad de Exchange Online (GUID) o la identidad de SharePoint Online (GUID) según corresponda. Los tres permisos anteriores deben mostrarse en permisos a claves.
  
Si la configuración de la Directiva de acceso no es correcta, ejecute el cmdlet Set-AzureRmKeyVaultAccessPolicy de la siguiente manera:
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

Por ejemplo, para Exchange Online y Skype empresarial:
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

Por ejemplo, para SharePoint Online y OneDrive para la empresa:
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

Para comprobar que no se ha establecido una fecha de expiración para las claves, ejecute el cmdlet [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) de la siguiente manera: 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

La clave de cliente no puede usar una clave expirada y las operaciones que se intentan con una clave expirada fallarán y, posiblemente, se producirá una interrupción del servicio. Se recomienda encarecidamente que las claves usadas con la clave de cliente no tengan una fecha de expiración. Una fecha de expiración, una vez establecida, no se puede quitar, pero se puede cambiar a una fecha distinta. Si se debe usar una clave que tenga establecida una fecha de expiración, cambie el valor de expiración a 12/31/9999. Las claves con una fecha de expiración establecida en una fecha distinta a 12/31/9999 no pasarán la validación de Office 365.
  
Para cambiar una fecha de expiración que se haya establecido en cualquier valor distinto de 12/31/9999, ejecute el cmdlet [set-AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) de la siguiente manera: 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> No establezca fechas de expiración en las claves de cifrado que use con la clave de cliente. 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Obtener el URI para cada clave de Azure Key Vault
<a name="GetKeyURI"> </a>

Una vez que haya completado todos los pasos de Azure para configurar los almacenes clave y haya agregado las claves, ejecute el siguiente comando para obtener el URI de la clave en cada almacén de clave. Tendrá que usar estos URI cuando cree y asigne cada DEP más adelante, por lo que debe guardar esta información en un lugar seguro. Recuerde ejecutar este comando una vez para cada almacén de clave.
  
En Azure PowerShell:
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: configuración de la clave de cliente para Exchange Online y Skype empresarial
<a name="AzureSteps"> </a>

Antes de empezar, asegúrese de haber completado las tareas necesarias para configurar el almacén de claves de Azure. Vea la [clave de cliente completar tareas en Azure Key Vault y Microsoft FastTrack](controlling-your-data-using-customer-key.md#AzureSteps) para obtener información. 
  
Para configurar la clave de cliente de Exchange Online y Skype empresarial, tendrá que realizar estos pasos conectándose de forma remota a Exchange Online con Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Crear una directiva de cifrado de datos (DEP) para su uso con Exchange Online y Skype empresarial
<a name="CreateDEP4EXOSkype"> </a>

Un DEP está asociado a un conjunto de claves almacenadas en Azure Key Vault. Asigne un DEP a un buzón de correo en Office 365. Office 365 usará entonces las claves identificadas en la Directiva para cifrar el buzón. Para crear la DEP, necesita los URI de la bóveda de clave que obtuvo antes. Consulte [obtener el URI de cada clave de Azure Key Vault](controlling-your-data-using-customer-key.md#GetKeyURI) para obtener instrucciones. 
  
Recuerde! Cuando se crea un DEP, se especifican dos claves que residen en dos depósitos de clave de Azure diferentes. Asegúrese de que estas claves se encuentran en dos regiones de Azure independientes para garantizar la redundancia geográfica.
  
Para crear la DEP, siga estos pasos:
  
1. En el equipo local, con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, [Conéctese a PowerShell de Exchange Online](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) abriendo Windows PowerShell y ejecutando el siguiente comando. 
    
   ```
   $UserCredential = Get-Credential
   ```

2. En el cuadro de diálogo solicitud de credenciales para Windows PowerShell, escriba la información de su cuenta profesional o educativa, haga clic en **Aceptar**y, a continuación, escriba el siguiente comando. 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. Ejecute el comando siguiente.
    
   ```
   Import-PSSession $Session
   ```

4. Para crear un DEP, use el cmdlet New-DataEncryptionPolicy; para ello, escriba el siguiente comando.
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Donde:
    
   -  *PolicyName* es el nombre que desea usar para la Directiva. Los nombres no pueden contener espacios. Por ejemplo, USA_mailboxes. 
    
   -  *PolicyDescription* es una descripción sencilla para el usuario de la Directiva que le ayudará a recordar para qué sirve la Directiva. Puede incluir espacios en la descripción. Por ejemplo, clave raíz para buzones de correo en Estados Unidos y sus zonas de ventas. 
    
   -  *KeyVaultURI1* es el URI para la primera clave de la Directiva. Por ejemplo, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01. 
    
   -  *KeyVaultURI2* es el URI de la segunda clave de la Directiva. Por ejemplo, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02. Separe los dos URI por una coma y un espacio. 
    
   Ejemplo:
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a>Asignar una DEP a un buzón
<a name="assignDEPtomailbox"> </a>

Asigne la DEP a un buzón mediante el cmdlet Set-Mailbox. Una vez asignada la Directiva, Office 365 puede cifrar el buzón con la clave designada en la DEP.
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Donde *MailboxIdParameter* especifica un buzón. Para obtener más información acerca del cmdlet Set-Mailbox, consulte [set-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).
  
### <a name="validate-mailbox-encryption"></a>Validar el cifrado de buzones
<a name="validatemailboxencryption"> </a>

El cifrado de un buzón puede tardar algún tiempo. Para la asignación de directivas primera vez, el buzón también debe completar el movimiento de una base de datos a otra antes de que el servicio pueda cifrar el buzón. Se recomienda esperar 72 horas antes de intentar validar el cifrado después de cambiar una DEP o la primera vez que asigna un DEP a un buzón.
  
Use el cmdlet Get-MailboxStatistics para determinar si un buzón está cifrado.
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

La propiedad IsEncrypted devuelve un valor **true** si el buzón está cifrado y un valor de **false** si el buzón no está cifrado. 

El tiempo para completar los movimientos de buzones depende del número de buzones a los que se asigna la DEP por primera vez, así como del tamaño de los buzones. Si los buzones no se han cifrado después de una semana desde el momento en que se asignó la DEP, inicie un movimiento de buzón para los buzones sin cifrar mediante el cmdlet New-MoveRequest.

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a>Office 365: configuración de la clave de cliente para SharePoint Online y OneDrive para la empresa
<a name="AzureSteps"> </a>

Antes de empezar, asegúrese de haber completado las tareas necesarias para configurar el almacén de claves de Azure. Vea la [clave de cliente completar tareas en Azure Key Vault y Microsoft FastTrack](controlling-your-data-using-customer-key.md#AzureSteps) para obtener información. 
  
Para configurar la clave de cliente de SharePoint Online y OneDrive para la empresa, necesitará realizar estos pasos conectándose de forma remota a SharePoint Online con Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>Crear una directiva de cifrado de datos (DEP) para cada geográfico de SharePoint Online y OneDrive para la empresa
<a name="CreateDEP4SPOODfB"> </a>

Un DEP está asociado a un conjunto de claves almacenadas en Azure Key Vault. Se aplica una DEP a todos los datos en una ubicación geográfica, también denominada geo. Si usa la característica multigeográfica de Office 365 (actualmente en versión preliminar), puede crear un DEP por geográfico. Si no usa la función multigeográfica, puede crear una DEP en Office 365 para usarla con SharePoint Online y OneDrive para la empresa. Office 365 usará entonces las claves identificadas en la DEP para cifrar los datos en esa geografía. Para crear la DEP, necesita los URI de la bóveda de clave que obtuvo antes. Consulte [obtener el URI de cada clave de Azure Key Vault](controlling-your-data-using-customer-key.md#GetKeyURI) para obtener instrucciones. 
  
Recuerde! Cuando se crea un DEP, se especifican dos claves que residen en dos depósitos de clave de Azure diferentes. Asegúrese de que estas claves se encuentran en dos regiones de Azure independientes para garantizar la redundancia geográfica.
  
Para crear un DEP, debe conectarse de forma remota a SharePoint Online mediante Windows PowerShell.
  
1. En el equipo local, con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, [Conéctese a SharePoint Online PowerShell](https://technet.microsoft.com/library/fp161372.aspx).
    
2. En el shell de administración de Microsoft SharePoint Online, ejecute el cmdlet [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) de la siguiente manera: 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Cuando registra el DEP, el cifrado comienza en los datos de la geografía. Esto puede tardar algún tiempo.
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a>Validar el cifrado de sitios de grupo, sitios de grupo y OneDrive para la empresa
<a name="validateencryptionSPO"> </a>

Puede comprobar el estado del cifrado ejecutando el cmdlet Get-SPODataEncryptionPolicy de la siguiente manera:
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

El resultado de este cmdlet incluye:
  
- URI de la clave principal.
    
- URI de la clave secundaria.
    
- El estado de cifrado de la geografía. Los Estados posibles son:
    
  - No **registrado:** Aún no se ha aplicado el cifrado de clave de cliente. 
    
  - **Registro:** Se ha aplicado el cifrado de clave de cliente y los archivos se encuentran en proceso de cifrado. Si la geografía está en este estado, también se mostrará la información sobre el porcentaje de sitios en la geografía que se completa para que pueda supervisar el progreso del cifrado. 
    
  - **Registrado:** Se ha aplicado el cifrado de clave de cliente y todos los archivos de todos los sitios se han cifrado. 
    
  - **Desplazamiento:** Hay un lanzamiento de clave en curso. Si la geografía está en este estado, también se mostrará la información sobre el porcentaje de sitios que han completado la operación de desplazamiento de claves para que pueda supervisar el progreso. 
    
## <a name="managing-customer-key-for-office-365"></a>Administración de la clave de cliente de Office 365
<a name="ManageCustomerKey"> </a>

Una vez configurada la clave de cliente para Office 365, puede realizar estas tareas de administración adicionales.
  
- [Restaurar claves de Azure Key Vault](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [Desplazamiento o rotación de una clave en Azure Key Vault que se usa con la clave de cliente](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [Administrar permisos de almacén de claves](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [Determinación de la DEP asignada a un buzón](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a>Restaurar claves de Azure Key Vault
<a name="RestoreAzureKeyVaultKeys"> </a>

Antes de realizar una restauración, use las capacidades de recuperación proporcionadas por la eliminación temporal. Todas las claves que se usan con la clave de cliente deben tener habilitada la eliminación temporal. La eliminación temporal actúa como una papelera de reciclaje y permite la recuperación de hasta 90 días sin necesidad de restaurarla. La restauración solo debe ser necesaria en circunstancias extremas o inusuales, por ejemplo, si se pierde la clave o el almacén de claves. Si necesita restaurar una clave para usarla con la clave de cliente, en Azure PowerShell, ejecute el cmdlet restore-AzureKeyVaultKey de la siguiente manera:
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

Por ejemplo:
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Si ya existe una clave con el mismo nombre en el almacén de claves, se producirá un error en la operación de restauración. Restore-AzureKeyVaultKey restaura todas las versiones principales y todos los metadatos de la clave, incluido el nombre de la clave.
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a>Desplazamiento o rotación de una clave en Azure Key Vault que se usa con la clave de cliente
<a name="RollCKkey"> </a>

Tanto la clave de Azure como la clave de cliente no requieren las claves de desplazamiento. Además, es prácticamente imposible poner en peligro las claves que están protegidas con HSM. Incluso si una clave raíz estaba en posesión de un actor malintencionado, no hay ningún medio viable de usarlo para descifrar datos, ya que solo el código de Office 365 sabe cómo usarlo. Sin embargo, la clave de cliente admite la rotación de una clave.
  
> [!CAUTION]
> Haga solo una clave de cifrado que use con la clave de cliente cuando exista una razón técnica clara o cuando un requisito de cumplimiento exija que tenga que hacer roll? a la clave. Además, no elimine las claves que estén asociadas a directivas. Al revertir las claves, habrá contenido cifrado con las claves anteriores. Por ejemplo, los buzones activos se volverán a cifrar con frecuencia, los buzones inactivos, desconectados y deshabilitados pueden seguir cifrados con las claves anteriores. SharePoint Online realiza una copia de seguridad del contenido para restauración y recuperación, por lo que es posible que todavía haya contenido archivado con claves antiguas. <br/> Para garantizar la seguridad de sus datos, SharePoint Online permitirá que no haya más de una operación Roll Key en curso a la vez. Si desea aplicar ambas claves en un almacén de claves, tendrá que esperar a que se complete completamente la primera operación de rotación de clave. Nuestra recomendación es escalonar las operaciones de roll Key en diferentes intervalos, de modo que no se trata de un problema. 
  
Cuando se gira una clave, se solicita una nueva versión de una clave existente. Para solicitar una nueva versión de una clave existente, use el mismo cmdlet, [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), con la misma sintaxis que usó para crear la clave en primer lugar.
  
Por ejemplo:
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

En este ejemplo, dado que ya existe una clave llamada **contoso-O365EX-na-VaultA1-Key001** en el almacén **contoso-O365EX-na-VaultA1** , se creará una nueva versión de clave. La operación agrega una nueva versión de clave. Esta operación conserva las versiones anteriores de la clave en el historial de versiones de la clave, de modo que los datos cifrados anteriormente con esa clave todavía se pueden descifrar. Una vez que haya completado la desactivación de cualquier clave asociada a una DEP, debe ejecutar un cmdlet adicional para asegurarse de que la clave de cliente comienza a usar la nueva clave. 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>Habilitar Exchange Online y Skype empresarial para usar una clave nueva después de girar o rotar claves en Azure Key Vault

Al aplicar las claves de Azure Key Vault asociadas con un DEP usado con Exchange Online y Skype empresarial, debe ejecutar el siguiente comando para actualizar el DEP y habilitar el inicio de Office 365 con la nueva clave.
  
Para indicar a la clave de cliente que use la nueva clave para cifrar buzones en Office 365 ejecute el cmdlet Set-DataEncryptionPolicy de la siguiente manera:
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

En un plazo de 48 horas, los buzones activos cifrados con esta Directiva se asociarán con la clave actualizada. Siga los pasos descritos en [determinar el DEP asignado a un buzón de correo](controlling-your-data-using-customer-key.md#DeterminemailboxDEP) para comprobar el valor de la propiedad DataEncryptionPolicyID del buzón. El valor de esta propiedad cambiará una vez se haya aplicado la clave actualizada. 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>Habilitar SharePoint Online y OneDrive para la empresa para usar una clave nueva después de girar o rotar claves en Azure Key Vault

Cuando se revierte cualquiera de las claves de Azure Key Vault asociadas con un DEP usado con SharePoint Online y OneDrive para la empresa, se debe ejecutar el cmdlet [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) para actualizar el DEP y habilitar el inicio de Office 365 con la nueva clave. 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

Se iniciará la operación de desplazamiento de claves para SharePoint Online y OneDrive para la empresa. Esta acción no es inmediata. Para ver el progreso de la operación de desplazamiento de claves, ejecute el cmdlet Get-SPODataEncryptionPolicy de la siguiente manera:
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a>Administrar permisos de almacén de claves
<a name="Managekeyvaultperms"> </a>

Hay disponibles varios cmdlets que permiten ver y, si es necesario, quitar permisos de almacén de clave. Es posible que necesite quitar permisos, por ejemplo, cuando un empleado deja el equipo.
  
Para ver los permisos de almacén de clave, ejecute el cmdlet Get-AzureRmKeyVault:
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

Por ejemplo:
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

Para quitar los permisos de un administrador, ejecute el cmdlet Remove-AzureRmKeyVaultAccessPolicy:
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
-UserPrincipalName <UPN of user>
```

Por ejemplo:
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Determinación de la DEP asignada a un buzón
<a name="DeterminemailboxDEP"> </a>

Para determinar la DEP asignada a un buzón, use el cmdlet Get-MailboxStatistics. El cmdlet devuelve un identificador único (GUID).
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

Donde *GeneralMailboxOrMailUserIdParameter* especifica un buzón. Para obtener más información acerca del cmdlet Get-MailboxStatistics, consulte [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).
  
Use el GUID para averiguar el nombre descriptivo de la DEP a la que está asignado el buzón de correo mediante la ejecución del siguiente cmdlet.
  
```
Get-DataEncryptionPolicy <GUID>
```

Donde *GUID* es el GUID que devuelve el cmdlet Get-MailboxStatistics en el paso anterior. 
  


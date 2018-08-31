---
title: Controlar los datos en Office 365 con la clave de cliente
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
description: Obtenga información sobre cómo configurar clave de cliente para Office 365 para Exchange Online, Skype para la empresa, SharePoint Online y OneDrive para la empresa. Con la clave de cliente, controlar las claves de cifrado de la organización y, a continuación, configurar Office 365 para usarlos para cifrar los datos en reposo en centros de datos de Microsoft.
ms.openlocfilehash: f8d7c12c32ca74b842f676f4a2ccde4d1c758361
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22559235"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a>Controlar los datos en Office 365 con la clave de cliente

Con la clave de cliente, controlar las claves de cifrado de la organización y, a continuación, configurar Office 365 para usarlos para cifrar los datos en reposo en centros de datos de Microsoft. Datos en reposo incluyen los datos de Exchange Online y Skype para la empresa que se almacena en los buzones de correo y los archivos que se almacenan en SharePoint Online y OneDrive para la empresa.
  
Debe configurar Azure para poder usar clave de cliente de Office 365. En este tema se describe los pasos que debe seguir para crear y configurar los recursos necesarios de Azure y luego se proporciona los pasos para la configuración de clave de cliente en Office 365. Después de haber completado el programa de instalación de Azure, determine qué directiva y, por lo tanto, qué teclas, para asignar a los buzones de correo y los archivos de la organización. Buzones de correo y los archivos para los que no asigne una directiva usará las directivas de cifrado que se controlan y administradas por Microsoft. Para obtener más información sobre la clave de cliente, o para obtener una descripción general, consulte la [Clave de cliente de preguntas más frecuentes de Office 365](service-encryption-with-customer-key-faq.md).
  
> [!IMPORTANT]
> Se recomienda que siga los procedimientos recomendados en este tema. Estos se denominan como **Sugerencia** e **importante**. Cliente clave le proporciona que control sobre las claves de cifrado de raíz cuyo ámbito puede ser tan grande como toda la organización. Esto significa que se cometen con estas claves puede tener un gran impacto y puede ocasionar que las interrupciones de servicio o pérdida irreparable de los datos. 
  
## <a name="before-you-begin-setting-up-customer-key"></a>Antes de comenzar la configuración de clave de cliente
<a name="Beforeyoustart"> </a>

Antes de empezar, asegúrese de que tener la licencia adecuada para su organización. Clave de cliente en Office 365 está disponible en Office 365 E5 o la SKU de cumplimiento de normas avanzadas.
  
A continuación, para comprender los conceptos y procedimientos descritos en este tema, debe revisar la documentación de la [Cámara de clave de Azure](https://azure.microsoft.com/en-us/documentation/services/key-vault/) . Además, a familiarizarse con los términos utilizados en Azure, por ejemplo, el [inquilino](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).
  
Para proporcionar comentarios en la clave del cliente, incluida la documentación, envíe sus ideas, sugerencias y perspectivas a customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a>Información general de la configuración de clave de cliente de Office 365
<a name="Overview"> </a>

Para configurar la clave del cliente se realice estas tareas. El resto de este tema proporciona instrucciones detalladas para cada tarea o vínculos a para obtener más información para cada paso del proceso.
  
**En Azure y FastTrack de Microsoft:**
  
La mayoría de estas tareas se efectuarán mediante la conexión de forma remota a Azure PowerShell. Para obtener mejores resultados, utilice la versión 4.4.0 o una versión posterior de Windows Azure PowerShell.
  
- [Crear dos nuevas suscripciones de Azure](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [Registrar las suscripciones de Azure para usar un período de retención obligatoria](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    El registro puede tardar de uno a cinco días laborables.
    
- [Enviar una solicitud para activar la clave de cliente de Office 365](controlling-your-data-using-customer-key.md#FastTrack)
    
    Una vez que ha creado las dos suscripciones en Azure nuevo, debe enviar la solicitud de oferta de clave de cliente correspondiente al completar un formulario web que se hospeda en el portal de Microsoft FastTrack. El equipo de FastTrack no proporciona asistencia con clave de cliente. Office simplemente usa el portal de FastTrack para permitirle enviar el formulario y nos ayudará a realizar un seguimiento de las ofertas relevantes para la clave de cliente.
  
Una vez que se han enviado una oferta de clave de cliente, Microsoft revisa la solicitud y le notifica cuando puede continuar con el resto de las tareas del programa de instalación. Este proceso puede tardar hasta cinco días laborables.
    
- [Creación de una cámara de clave de Azure premium en cada suscripción](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [Asignar permisos a cada cámara clave](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [Habilitar y, a continuación, confirmar la eliminación de suave en los depósitos de clave](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [Agregar una clave a cada cámara clave ya sea mediante la creación o importar una clave](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [Compruebe el nivel de recuperación de las claves](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [Copia de seguridad cámara clave de Azure](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [Validar los valores de configuración de cámara de clave de Azure](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [Obtener el identificador URI para cada clave de cámara de clave de Azure](controlling-your-data-using-customer-key.md#GetKeyURI)
    
**En Office 365:**
  
Exchange Online y Skype para la empresa:
  
- [Crear una directiva de cifrado de datos (DEP) para su uso con Exchange Online y Skype para la empresa](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [Asignar una DEP a un buzón de correo](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [Validar el cifrado de buzón de correo](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
SharePoint Online y OneDrive para la empresa:
  
- [Crear una directiva de cifrado de datos (DEP) para cada OneDrive y SharePoint Online para profesionales geo](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [Validar el cifrado de sitios de grupo, sitios de grupo y OneDrive para la empresa](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Completar las tareas en Azure clave cámara y Microsoft FastTrack para clave de cliente
<a name="AzureSteps"> </a>

Completar estas tareas en Azure clave Vault para configurar la clave del cliente de Office 365. Debe completar estos pasos, independientemente de si piensa configurar clave de cliente para Exchange Online y Skype para empresas o SharePoint Online y OneDrive para la empresa o para todos los servicios compatibles de Office 365.
  
### <a name="create-two-new-azure-subscriptions"></a>Crear dos nuevas suscripciones de Azure
<a name="Create2newsubs"> </a>

Dos suscripciones Azure son necesarias para la clave de cliente. Como práctica recomendada, Microsoft recomienda crear nuevas suscripciones Azure para su uso con clave de cliente. Sólo se pueden autorizar Azure claves de cámara de clave para aplicaciones en el mismo arrendatario de Azure Active Directory (AAD), debe crear las suscripciones nuevo con el mismo arrendatario de Azure AD se utiliza con la organización de Office 365 donde se asignará la depós. Por ejemplo, con su cuenta de trabajo o escuela que tiene privilegios de administrador global de la organización de Office 365. Para obtener instrucciones detalladas, consulte [suscribirse a Azure como una organización](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/).
  
> [!IMPORTANT]
> Clave de cliente requiere dos claves para cada directiva de cifrado de datos (DEP). Para poder realizar esta acción, debe crear dos suscripciones de Azure. Como práctica recomendada, Microsoft recomienda que tienen miembros independientes de la organización configurar una clave en cada suscripción. Además, estas suscripciones Azure sólo deben usarse para administrar las claves de cifrado para Office 365. Esto protege la organización en caso de que uno de los operadores de forma accidental, intencionadamente o intencionada elimina o mismanages en caso contrario, las claves para los que son responsables.<br/> Se recomienda que configure las nuevas suscripciones Azure que únicamente se utilizan para la administración de recursos de Azure clave Vault para su uso con clave de cliente. No hay ningún límite práctico para el número de Azure suscripciones que se pueden crear para su organización. Estos procedimientos recomendados se minimizar el impacto de los errores humanos al ayudar a administrar los recursos utilizados por clave de cliente. 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Enviar una solicitud para activar la clave de cliente de Office 365
<a name="FastTrack"> </a>

Una vez que haya completado los pasos de Azure, debe enviar una solicitud de oferta en el [portal de Microsoft FastTrack](https://fasttrack.microsoft.com/). Una vez que ha enviado una solicitud a través del portal de web FastTrack, Microsoft comprueba la cámara de clave de Azure configuración datos e información de contacto que ha proporcionado. Las selecciones que realice en el formulario oferta con respecto a los agentes autorizados de la organización es necesaria para la finalización de registro de la clave del cliente y no críticos. Los agentes de la organización que seleccione en el formulario que se usará para garantizar la autenticidad de cualquier solicitud para revocar y destruir todas las claves que se utiliza con una directiva de cifrado de datos de clave de cliente. Debe realizar este paso una vez para activar la clave de cliente para que Exchange Online y Skype para profesionales de cobertura y una segunda vez activar la clave de cliente para SharePoint Online y OneDrive para la empresa.
  
Para enviar una oferta para activar la clave de cliente, siga estos pasos:
  
1. Uso de una cuenta de trabajo o escuela que tiene permisos de administrador global de la organización de Office 365, inicie sesión en el [portal de Microsoft FastTrack](https://fasttrack.microsoft.com/).
    
2. Una vez que ha iniciado sesión, vaya al **panel**.
    
3. Elija **ofrece**y revise la lista de las ofertas de actuales.
    
4. Elija **Obtener más información** para la oferta que se aplica a usted: 
    
  - **Exchange Online y Skype para la empresa:** Elija **Obtener más información** sobre la oferta de **Clave de cliente de Exchange** . 
    
  - **SharePoint Online y OneDrive para la empresa:** Eligió **Obtener más información** sobre la oferta de **Clave de cliente de SharePoint y OneDrive para la empresa** . 
    
5. En la página **Detalles de la oferta** , elija **Crear una solicitud**.
    
6. Rellene todos los detalles correspondientes y la información solicitada en el formulario de oferta. Preste especial atención a las selecciones para que los agentes de la organización que desea autorizar para aprobar la destrucción permanente y irreversible de claves de cifrado y de datos. Una vez que haya completado el formulario, elija **Enviar**.
    
    Este proceso puede tardar hasta cinco días de negocio una vez que Microsoft ha sido notificado de la solicitud.
    
7. Continúe con la sección de período de retención obligatoria más adelante.
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrar las suscripciones de Azure para usar un período de retención obligatoria
<a name="RegisterSubsforMRP"> </a>

La pérdida temporal o permanente de las claves de cifrado de raíz puede ser muy perjudiciales o incluso tras errores graves a la operación de servicio y puede provocar una pérdida de datos. Por este motivo, los recursos que se utiliza con la clave de cliente requieren protección segura. Todos los recursos de Azure que se usan con clave de cliente ofrecen mecanismos de protección más allá de la configuración predeterminada. Suscripciones de Azure pueden ser etiquetadas o registradas de forma que impiden la cancelación de inmediata y irrevocable. Esto se conoce como registro durante un período de retención obligatoria. Los pasos necesarios para registrar las suscripciones de Azure para un período de retención obligatoria requieren una colaboración con el equipo de Office 365. Este proceso puede tardar de uno a cinco días laborables. Anteriormente, esto se denomina a "No Cancelar".
  
Antes de ponerse en contacto con el equipo de Office 365, debe realizar los siguientes pasos para cada suscripción de Azure que usan con clave de cliente:
  
1. Inicie sesión en su suscripción de Azure con Azure PowerShell. Para obtener instrucciones, vea [iniciar sesión con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).
    
2. Ejecute el cmdlet Register-AzureRmProviderFeature para registrar las suscripciones para usar un período de retención obligatoria.
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. Póngase en contacto con Microsoft para que el proceso finalizando. Para SharePoint y OneDrive para el equipo de negocios, póngase en contacto con [spock@microsoft.com](mailto:spock@microsoft.com). Para Exchange Online y Skype para la empresa, póngase en contacto con [exock@microsoft.com](mailto:exock@microsoft.com). El contrato de nivel de servicio (SLA) para la finalización de este proceso es de cinco días de negocio una vez que Microsoft ha sido una notificación (y comprobado) que hayan registrado las suscripciones para usar un período de retención obligatoria. Incluir lo siguiente en su correo electrónico:
    
    **Asunto**: clave del cliente para \< *nombre de dominio completo de su inquilino*\> 
    
    **Cuerpo**: los identificadores de suscripción para la que desea que tengan el período finaliza una retención obligatoria. 
    
4. Una vez que recibe la notificación de Microsoft que el registro es completado, compruebe el estado del registro ejecutando el cmdlet Get-AzureRmProviderFeature como se indica a continuación:
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. Después de comprobar que la propiedad de **Estado de registro** desde el cmdlet Get-AzureRmProviderFeature devuelve un valor de **Registered**, ejecute el siguiente comando para completar el proceso:
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Creación de una cámara de clave de Azure premium en cada suscripción
<a name="CreateKeyVault"> </a>

Los pasos para crear una clave cámara se documentan en [Getting Started with Azure clave Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), que le guiará a través de la instalación e iniciar Windows Azure PowerShell, que se conectan a su suscripción de Azure, creación de un grupo de recursos y crear un depósito de clave en el que grupo de recursos.
  
Cuando se crea una cámara clave, debe elegir un SKU: Standard o Premium. La SKU estándar permite claves de Azure clave Vault para estar protegidos con software - no hay ninguna protección de clave de módulo de seguridad de Hardware (HSM) - y la SKU Premium permite el uso de los HSM para la protección de las claves de cámara de clave. Clave de cliente acepta depósitos claves que usan cualquier SKU, aunque Microsoft recomienda encarecidamente que use sólo el SKU Premium. El costo de las operaciones con claves de cualquier tipo es el mismo, por lo que la única diferencia de costo es el costo por mes para cada clave protegida HSM. Para obtener más información, vea [clave de cámara de precios](https://azure.microsoft.com/pricing/details/key-vault/) . 
  
> [!IMPORTANT]
> Utilice las teclas de protegida HSM y depósitos de SKU Premium claves para los datos de producción y usar sólo depósitos claves estándar SKU y claves con fines de prueba y validación. 
  
Para cada servicio de Office 365 con la que va a usar clave de cliente, cree una cámara clave en cada una de las dos suscripciones en Azure que ha creado. Por ejemplo, para Exchange Online y Skype para empresas sólo o SharePoint Online y OneDrive para la empresa solo, creará solo un par de depósitos. Para habilitar la clave de cliente para Exchange Online y SharePoint Online, va a crear dos pares de claves depósitos.
  
Usar una convención de nomenclatura para depósitos claves que refleja el uso intencionado de la característica DEP a los que se asocian los depósitos. Vea la sección de procedimientos recomendados a continuación para recomendaciones de convención de nomenclatura.
  
Crear un conjunto de depósitos para cada directiva de cifrado de datos independiente y emparejado. Para Exchange Online, el ámbito de una directiva de cifrado de datos se elige por usted al asignar la directiva al buzón de correo. Un buzón de correo puede tener sólo una directiva asignada, y puede crear directivas de hasta cincuenta. Para SharePoint Online el ámbito de una directiva es todos los datos dentro de una organización en una ubicación geográfica o ubican.
  
La creación de depósitos claves también requiere la creación de grupos de recursos de Azure, ya que depósitos claves necesitan la capacidad de almacenamiento de información (aunque muy pequeño) y cámara de clave de registro, si se habilita, también genera los datos almacenados. Como procedimiento recomendado Microsoft recomienda el uso de los administradores independientes para administrar cada grupo de recursos, con la administración que se alinea con el conjunto de los administradores que va a administrar todos los recursos relacionados de clave de cliente.
  
> [!IMPORTANT]
> Para maximizar la disponibilidad, deben ser sus claves depósitos en regiones cerca de su servicio de Office 365. Por ejemplo, si la organización de Exchange Online está en Norteamérica, coloque los depósitos claves en Norteamérica. Si la organización de Exchange Online se encuentra en Europa, coloque las claves depósitos en Europa.<br/>Usar un prefijo común para depósitos claves e incluya una abreviatura del uso y el ámbito de las claves y cámara clave (por ejemplo, para el servicio de Contoso SharePoint donde se encuentran los depósitos en América del Norte, un par de nombres de posibles es Contoso-O365SP-NA-VaultA1 y Contoso-O365SP-NA-VaultA2. Nombres de cámara son cadenas globalmente únicas dentro de Azure, por lo que es posible que necesite para probar las variaciones de los nombres que desee en el caso de los nombres que desee ya se hayan solicitado por otros clientes de Azure. A partir de julio de 2017 cámara nombres no se puede cambiar, por lo que es una práctica recomendada tener un plan escrito para el programa de instalación y use una segunda persona para comprobar que el plan se ejecuta correctamente.<br/>Si es posible, cree los depósitos en regiones que no sean emparejada. Regiones de Azure emparejadas proporcionan una alta disponibilidad a través de dominios de errores de servicio. Por lo tanto, pares regionales pueden considerarse como región de copia de seguridad del otro. Esto significa que un recurso de Azure que se coloca en una región tiene automáticamente la tolerancia a errores a través de la región emparejada. Por este motivo, selección de regiones para dos depósitos usados en una DEP donde las regiones están emparejado significa que sólo un total de las dos regiones de disponibilidad están en uso. La mayoría de áreas geográficas sólo tienen dos regiones, por lo que no es posible seleccionar regiones no emparejados. Si es posible, elija dos regiones que no sean emparejados para los depósitos de dos que se utiliza con una dependencia Esto supone una ventaja de un total de cuatro áreas de disponibilidad. Para obtener más información, vea [recuperación ante desastres y continuidad del negocio (BCDR): áreas de Azure emparejada](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) para obtener una lista de pares regionales. 
  
### <a name="assign-permissions-to-each-key-vault"></a>Asignar permisos a cada cámara clave
<a name="KeyVaultPerms"> </a>

Para cada depósito de clave, debe definir tres conjuntos independientes de los permisos de clave de cliente, dependiendo de su implementación. Por ejemplo, debe definir un conjunto de permisos para cada una de las siguientes opciones:
  
- **Los administradores de cámara de clave** que se va a realizar la administración diaria de su cámara clave para su organización. Estas tareas incluyen la copia de seguridad, crean, obtengan, importación, lista y restauran. 
    
    > [!IMPORTANT]
    > El conjunto de permisos asignados a los administradores de la cámara clave no incluye el permiso para eliminar claves. Esto es intencionado y una práctica importante. Eliminación de las claves de cifrado normalmente no se realiza, ya que realiza entonces permanentemente destruye datos. Como procedimiento recomendado, no conceder este permiso a los administradores de la cámara clave de forma predeterminada. En su lugar, esto se reserva para los colaboradores de cámara clave y sólo asignarla a un administrador en una base de corto plazo una vez que se entiende una descripción clara de las consecuencias. 
  
    Para asignar estos permisos a un usuario en la organización de Office 365, inicie sesión en su suscripción de Azure con Azure PowerShell. Para obtener instrucciones, vea [iniciar sesión con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).
    
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

- **Los colaboradores de cámara de clave** que se pueden cambiar los permisos en el depósito de clave de Azure propio. Debe cambiar estos permisos como empleados dejan o unirse a su equipo, o en la situación muy poco habitual que la clave vault administradores legítima necesitan permiso para eliminar o restaurar una clave. Este conjunto de las necesidades de los colaboradores de cámara clave tener el rol de **Colaborador** en su cámara clave. Puede asignar este rol mediante el Administrador de recursos de Azure. Para obtener instrucciones detalladas, consulte [Control de acceso de Use Role-Based para administrar el acceso a los recursos de suscripción de Azure](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). El administrador que crea una suscripción a tiene este acceso de forma implícita, así como la capacidad para asignar a otros administradores al rol Colaborador.
    
- Si piensa usar clave de cliente con Exchange Online y Skype para la empresa, debe conceder permiso a Office 365 para utilizar la cámara clave en nombre de Exchange Online y Skype para la empresa. Del mismo modo, si piensa usar clave de cliente con SharePoint Online y OneDrive para la empresa, debe agregar permisos para Office 365 utilizar la cámara clave en nombre de SharePoint Online y OneDrive para la empresa. Para conceder permiso a Office 365, ejecute el cmdlet **Set-AzureRmKeyVaultAccessPolicy** mediante la siguiente sintaxis: 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    Donde:
    
  - *vaultname* es el nombre de la cámara clave que ha creado. 
    
  - Para Exchange Online y Skype para la empresa, reemplace *appID de Office 365* con`00000002-0000-0ff1-ce00-000000000000`
    
  - Para SharePoint Online y OneDrive para la empresa, reemplace *appID de Office 365* con`00000003-0000-0ff1-ce00-000000000000`
    
  Ejemplo: Configuración de permisos para Exchange Online y Skype para la empresa:
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  Ejemplo: Configuración de permisos para SharePoint Online y OneDrive para la empresa
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Habilitar y, a continuación, confirmar la eliminación de suave en los depósitos de clave
<a name="SoftDelete"> </a>

Cuando se puede recuperar rápidamente las claves, es menos probable que a experimenta una interrupción del servicio ampliado debido a las claves eliminadas accidentalmente o de forma malintencionada. Debe habilitar esta configuración, que se conoce como eliminar suave, antes de poder utilizar las claves con clave de cliente. Habilitación de eliminar suave le permite recuperar claves o depósitos dentro de 90 días de eliminación sin tener que restaurarlos desde la copia de seguridad.
  
Para habilitar eliminar suave en los depósitos de clave, siga estos pasos:
  
1. Inicie sesión en su suscripción de Azure con Windows Powershell. Para obtener instrucciones, vea [iniciar sesión con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).
    
2. Ejecute el cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) . En este ejemplo, *vaultname* es el nombre de la cámara clave para la que va a habilitar eliminar suave: 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. Confirmar eliminar suave está configurada para la cámara clave ejecutando el cmdlet **Get-AzureRmKeyVault** . ¿Si eliminar suave está configurado correctamente para el depósito de clave, el software eliminar habilitado? propiedad devuelve un valor de **True**: 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Agregar una clave a cada cámara clave ya sea mediante la creación o importar una clave
<a name="AddKeystoKeyVault"> </a>

Existen dos maneras de agregar las claves a una cámara de clave de Azure; puede crear una clave directamente en la clave de cámara, o puede importar una clave. Creación de una clave directamente en depósito de clave es el método menos complicado, mientras importar una clave proporciona un control total sobre cómo se genera la clave.
  
Para crear una clave directamente en su cámara clave, ejecute el cmdlet [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) como sigue: 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Donde:
  
-  *vaultname* es el nombre de la cámara clave en la que desea crear la clave. 
    
-  *nombre de clave* es el nombre que desea dar a la nueva clave. 
    
    > [!TIP]
    > Claves de nombre con una convención de nomenclatura similar, como se describió anteriormente para depósitos claves. De este modo, en herramientas que muestran sólo el nombre de clave, la cadena es autodescriptiva. 
  
- Si tiene la intención de proteger la clave con un HSM, asegúrese de que de lo contrario, especifique **HSM** como el valor del parámetro de _destino_ , especifique **Software**.
    
Por ejemplo,
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

Para importar una clave directamente a su cámara clave, debe tener un nShield Thales módulo de seguridad de Hardware.
  
Algunas organizaciones prefieren este método para establecer la procedencia de sus claves y este método también proporciona lo siguiente:
  
- El conjunto de herramientas utilizada para la importación incluye certificación de Thales que no es exportable la clave de Exchange de clave (KEK) que se usa para cifrar la clave que se genera y se genera dentro de un HSM original que se fabricó por Thales.
    
- El conjunto de herramientas incluye certificación de Thales que el mundo de la seguridad de Azure clave cámara también se generó en un auténtico HSM fabricado por Thales. La certificación demuestra a usted que Microsoft también está usando hardware de Thales original.
    
Compruebe con su grupo de seguridad para determinar si son necesarias las declaraciones anteriores. Para que obtener instrucciones detalladas para crear una clave local y se importa a su cámara clave, vea [cómo generar y transferir claves protegida HSM para depósito de clave de Azure](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Use las instrucciones de Azure para crear una clave en cada cámara clave.
  
### <a name="check-the-recovery-level-of-your-keys"></a>Compruebe el nivel de recuperación de las claves
<a name="CheckKeyRecoveryLevel"> </a>

Office 365 requiere que la suscripción de Azure clave cámara está establecida en no cancelar y que las teclas usadas por clave de cliente tienen suave eliminar habilitado. Puede confirmarlo mirando en el nivel de recuperación en las claves.
  
Para comprobar el nivel de recuperación de una clave, en Windows Azure PowerShell, ejecute el cmdlet Get-AzureKeyVaultKey como sigue:
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

Si la propiedad de _Nivel de recuperación_ devuelve nada que no sea un valor de **Recuperable + ProtectedSubscription**, necesitará revisar este tema y asegúrese de que ha seguido todos los pasos para colocar la suscripción en la lista no cancelar y que debe eliminar suave habilitado en cada uno de los depósitos de clave.
  
### <a name="backup-azure-key-vault"></a>Copia de seguridad cámara clave de Azure
<a name="BackupAzureKeyVaultkeys"> </a>

Inmediatamente después de la creación o cualquier cambio a una clave, realizar una copia de seguridad y almacenar copias de la copia de seguridad, en línea y sin conexión. Copias sin conexión deben no esté conectadas a cualquier red, por ejemplo, en un servicio de almacenamiento físico de seguros o comerciales. Al menos una copia de la copia de seguridad debe almacenarse en una ubicación que sea accesible en el caso de un desastre. Los objetos binarios de copia de seguridad son los únicos medios de restauración de material de clave debe una clave de cámara de clave se destruye permanentemente o inoperativo en caso contrario. Claves que son externos a Azure clave cámara y se importaron a Azure clave cámara no cumple los requisitos como una copia de seguridad porque los metadatos necesarios para la clave del cliente usar la clave no existe con la clave externa. Sólo una copia de seguridad tomado de cámara de Azure clave se puede usar para operaciones de restauración con clave de cliente. Por lo tanto, es esencial que se realice una copia de seguridad de Azure clave cámara una vez que se cargan o creada una clave.
  
Para crear una copia de seguridad de una clave de cámara de clave de Azure, ejecute el cmdlet de [AzureKeyVaultKey de copia de seguridad](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) de la siguiente manera:
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

Asegúrese de que el archivo de salida utiliza el sufijo de `.backup`.
  
El archivo de salida resultante de este cmdlet se cifra y no se puede usar fuera de cámara de clave de Azure. Sólo para la suscripción de Azure desde la que se realizó la copia de seguridad se puede restaurar la copia de seguridad.
  
> [!TIP]
> Para el archivo de salida, elija una combinación de su nombre de depósito y el nombre de la clave. Esto hará que el archivo nombre autodescriptiva. También asegurará que los nombres de archivo de copia de seguridad no entrar en conflicto. 
  
Por ejemplo:
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Validar los valores de configuración de cámara de clave de Azure
<a name="Validateconfiguration"> </a>

Realizar la validación antes de usar claves en una DEP es opcional, pero se recomienda encarecidamente. En particular, si usa los pasos para configurar las claves y depósitos distinto de los que se describen en este tema, debe validar el estado de los recursos de Azure clave cámara antes de configurar la clave del cliente.
  
Para comprobar que las claves tienen operaciones get, wrapKey y unwrapKey habilitadas:
  
Ejecute el cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) como sigue: 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

En el resultado, busque para la directiva de acceso y de la identidad de Exchange Online (GUID) o la identidad de SharePoint Online (GUID), según corresponda. Las tres de los permisos anteriores deben mostrarse en permisos para las claves.
  
Si la configuración de directiva de acceso no es correcta, ejecute el cmdlet Set-AzureRmKeyVaultAccessPolicy como sigue:
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

Por ejemplo, para Exchange Online y Skype para la empresa:
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

Por ejemplo, para SharePoint Online y OneDrive para la empresa:
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

Para comprobar que no se establece una fecha de caducidad para las claves que se ejecute el cmdlet [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) como sigue: 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

No se puede usar una clave que han expirado por clave de cliente y se producirá un error en operaciones intentadas con una clave que han expirado y, posiblemente, provocar una interrupción del servicio. Se recomienda encarecidamente que las claves que se utiliza con la clave de cliente no tienen una fecha de caducidad. Una fecha de caducidad, una vez que el conjunto, no se pueden quitar, pero se puede cambiar a una fecha diferente. Si debe usar una clave que tenga una fecha de caducidad, cambie el valor de expiración a 31/12/9999. Claves con una fecha de caducidad se establece en una fecha distinta de 31/12/9999 no pasará la validación de Office 365.
  
Para cambiar una fecha de caducidad que se ha establecido en un valor distinto de 31/12/9999, ejecute el cmdlet [Set-AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) como sigue: 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> No establecer fechas de caducidad en las claves de cifrado que se utiliza con la clave de cliente. 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Obtener el identificador URI para cada clave de cámara de clave de Azure
<a name="GetKeyURI"> </a>

Una vez que haya completado todos los pasos en Azure para configurar sus claves depósitos y agrega las claves, ejecute el siguiente comando para obtener el URI de la clave en cada cámara clave. Debe utilizar estos identificadores URI al crear y asignar cada DEP más adelante, por lo que guarde esta información en un lugar seguro. Recuerde que debe ejecutar este comando una vez para cada depósito de clave.
  
En Azure PowerShell:
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: Configuración de clave de cliente para Exchange Online y Skype para la empresa
<a name="AzureSteps"> </a>

Antes de empezar, asegúrese de que ha completado las tareas necesarias para configurar la cámara de clave de Azure. Para obtener información, vea [completar las tareas en Azure clave cámara y FastTrack de Microsoft para la clave de cliente](controlling-your-data-using-customer-key.md#AzureSteps) . 
  
Para configurar la clave de cliente para Exchange Online y Skype para la empresa, debe realizar estos pasos mediante la conexión de forma remota a Exchange Online con Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Crear una directiva de cifrado de datos (DEP) para su uso con Exchange Online y Skype para la empresa
<a name="CreateDEP4EXOSkype"> </a>

Una característica DEP está asociada con un conjunto de claves que se almacenan en Azure clave cámara. Asignar una DEP a un buzón en Office 365. Office 365, a continuación, usará las teclas identificadas en la directiva para cifrar el buzón de correo. Para crear la DEP, necesita a los URI de cámara clave obtenido anteriormente. Para obtener instrucciones, vea [obtener el identificador URI para cada clave de cámara de clave de Azure](controlling-your-data-using-customer-key.md#GetKeyURI) . 
  
¡Recuerde! Cuando se crea una DEP, especifique dos claves que residen en dos diferentes depósitos de clave de Azure. Asegúrese de que estas claves se encuentran en dos regiones de Azure independientes para garantizar la redundancia de geo.
  
Para crear la DEP, siga estos pasos:
  
1. En el equipo local, usando una cuenta de trabajo o escuela que tiene permisos de administrador global de la organización de Office 365, [conectarse a Exchange Online PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) abrir Windows PowerShell y ejecute el siguiente comando. 
    
   ```
   $UserCredential = Get-Credential
   ```

2. En el cuadro de diálogo solicitud de credenciales de Windows PowerShell, escriba su trabajo o escuela información de cuenta, haga clic en **Aceptar**y, a continuación, escriba el siguiente comando. 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. Ejecute el siguiente comando.
    
   ```
   Import-PSSession $Session
   ```

4. Para crear una DEP, use el cmdlet New-DataEncryptionPolicy escribiendo el siguiente comando.
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Donde:
    
   -  *PolicyName* es el nombre que desea usar para la directiva. Los nombres no pueden contener espacios. Por ejemplo, USA_mailboxes. 
    
   -  *PolicyDescription* es una descripción de usuario descriptivo de la directiva que le ayudarán a recordar cuál es la directiva. Puede incluir espacios en la descripción. Por ejemplo, raíz clave para los buzones de correo en Estados Unidos y sus territorios. 
    
   -  *KeyVaultURI1* es el identificador URI para la primera clave en la directiva. Por ejemplo, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01. 
    
   -  *KeyVaultURI2* es el identificador URI para la segunda clave en la directiva. Por ejemplo, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02. Separe a los dos URI por una coma y un espacio. 
    
   Ejemplo:
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a>Asignar una DEP a un buzón de correo
<a name="assignDEPtomailbox"> </a>

Asignar la DEP a un buzón de correo mediante el cmdlet Set-Mailbox. Una vez que asigne la directiva, Office 365 puede cifrar el buzón de correo con la clave designada en la DEP.
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Donde *MailboxIdParameter* especifica un buzón de correo. Para obtener más información acerca del cmdlet Set-Mailbox, consulte [Set-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).
  
### <a name="validate-mailbox-encryption"></a>Validar el cifrado de buzón de correo
<a name="validatemailboxencryption"> </a>

Cifrar un buzón de correo puede tardar un poco. Para la primera asignación de directivas de tiempo, el buzón de correo también debe completar el traslado de una base de datos a otro antes de que el servicio puede cifrar el buzón de correo. Se recomienda que espere 72 horas antes de intentar validar cifrado después de cambiar una DEP o la primera vez se puede asignar una DEP a un buzón.
  
Use el cmdlet Get-MailboxStatistics para determinar si se cifra un buzón de correo.
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

La propiedad IsEncrypted devuelve un valor de **true** si se cifra el buzón de correo y el valor **false** si el buzón de correo no se cifra. 

El tiempo para completar movimientos de buzones depende del número de buzones a los que asignar la característica DEP por primera vez, así como el tamaño de los buzones de correo. Si no ha cifrado los buzones de correo después de una semana desde el momento en que asignó la DEP, iniciar un movimiento del buzón para los buzones de correo sin cifrar mediante el cmdlet New-MoveRequest.

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a>Office 365: Configuración de clave de cliente para SharePoint Online y OneDrive para la empresa
<a name="AzureSteps"> </a>

Antes de empezar, asegúrese de que ha completado las tareas necesarias para configurar la cámara de clave de Azure. Para obtener información, vea [completar las tareas en Azure clave cámara y FastTrack de Microsoft para la clave de cliente](controlling-your-data-using-customer-key.md#AzureSteps) . 
  
Para configurar la clave del cliente para SharePoint Online y OneDrive para la empresa, debe realizar estos pasos mediante la conexión de forma remota en SharePoint Online con Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>Crear una directiva de cifrado de datos (DEP) para cada OneDrive y SharePoint Online para profesionales geo
<a name="CreateDEP4SPOODfB"> </a>

Una característica DEP está asociada con un conjunto de claves que se almacenan en Azure clave cámara. Aplicar una DEP para todos los datos en una ubicación geográfica, también denominado un geo. Si usa la característica de multi-ubican de Office 365 (actualmente en la vista previa), puede crear uno DEP por ubican. Si no está utilizando multi-ubican, puede crear uno DEP en Office 365 para su uso con SharePoint Online y OneDrive para la empresa. Office 365, a continuación, usará las teclas identificadas en la característica DEP para cifrar los datos en ese ubican. Para crear la DEP, necesita a los URI de cámara clave obtenido anteriormente. Para obtener instrucciones, vea [obtener el identificador URI para cada clave de cámara de clave de Azure](controlling-your-data-using-customer-key.md#GetKeyURI) . 
  
¡Recuerde! Cuando se crea una DEP, especifique dos claves que residen en dos diferentes depósitos de clave de Azure. Asegúrese de que estas claves se encuentran en dos regiones de Azure independientes para garantizar la redundancia de geo.
  
Para crear una DEP, debe conectarse de forma remota en SharePoint Online mediante el uso de Windows PowerShell.
  
1. En el equipo local, usando una cuenta de trabajo o escuela que tiene permisos de administrador global de la organización de Office 365, [conectarse a SharePoint Online Powershell](https://technet.microsoft.com/library/fp161372.aspx).
    
2. En la consola de administración de Microsoft en línea de SharePoint ejecute el cmdlet [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) como sigue: 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Cuando se registre la DEP, cifrado comienza en los datos en el ubican. Esto puede tardar un poco.
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a>Validar el cifrado de sitios de grupo, sitios de grupo y OneDrive para la empresa
<a name="validateencryptionSPO"> </a>

Puede comprobar el estado de cifrado ejecutando el cmdlet Get-SPODataEncryptionPolicy como se indica a continuación:
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

El resultado de este cmdlet incluye:
  
- El URI de la clave principal.
    
- El URI de la clave secundaria.
    
- El estado de cifrado para el ubican. Los Estados posibles son:
    
  - **No registradas:** Cifrado de clave de cliente aún no se ha aplicado. 
    
  - **Registro:** Se ha aplicado el cifrado de clave de cliente y los archivos se encuentran en el proceso de cifrado. Si su geo se encuentra en este estado, se podrá también se mostrará información en qué porcentaje de sitios en la ubican están completas para que pueda supervisar el progreso de cifrado. 
    
  - **Registrado:** Se ha aplicado el cifrado de clave de cliente, y se han cifrado todos los archivos en todos los sitios. 
    
  - **Sucesivas:** Una clave roll está en curso. Si su geo se encuentra en este estado, se podrá también se mostrará información en qué porcentaje de sitios haya completado la operación roll clave para que se puede supervisar el progreso. 
    
## <a name="managing-customer-key-for-office-365"></a>Administración de clave de cliente de Office 365
<a name="ManageCustomerKey"> </a>

Después de que ha configurado la clave del cliente de Office 365, puede realizar estas tareas de administración adicionales.
  
- [Restaurar las claves de cámara de clave de Azure](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [Constante o girar una clave en Azure depósito de clave que se utiliza con la clave de cliente](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [Administrar los permisos de la clave de cámara](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [Determinar la DEP asignada a un buzón de correo](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a>Restaurar las claves de cámara de clave de Azure
<a name="RestoreAzureKeyVaultKeys"> </a>

Antes de realizar una restauración, use las funciones de recuperación proporcionadas por eliminar suave. Todas las claves que se usan con clave de cliente se necesitan tener suave eliminar habilitado. Eliminar suave actúa como una Papelera de reciclaje y permite la recuperación de hasta 90 días sin necesidad de restaurar. Restauración sólo será necesario en circunstancias extremas o poco habituales, por ejemplo, si se pierde la clave o depósito de clave. Si debe restaurar una clave para su uso con clave de cliente, en Azure PowerShell, ejecute el cmdlet Restore-AzureKeyVaultKey como sigue:
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

Por ejemplo:
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Si ya existe una clave con el mismo nombre en la caja fuerte de clave, se producirá un error en la operación de restauración. AzureKeyVaultKey de restauración restaura todas las versiones de clave y todos los metadatos de la clave, incluido el nombre de la clave.
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a>Constante o girar una clave en Azure depósito de clave que se utiliza con la clave de cliente
<a name="RollCKkey"> </a>

Constante de claves no es necesario por cualquier cámara de clave de Azure o por clave de cliente. Además, las claves que están protegidas con un HSM son prácticamente imposibles para poner en peligro. Incluso si una clave raíz estuvieron en posesión de un actor malintencionado no hay ningún medio viable de uso para descifrar los datos, ya que sólo el código de Office 365 sabe cómo usarla. Sin embargo, la aplicación de una clave es compatible con clave de cliente.
  
> [!CAUTION]
> Aplicar sólo una clave de cifrado que utilice con clave de cliente cuando exista una razón desactive técnica o un requisito de cumplimiento de normas determina que se debe aplicar la clave. Además, no elimine las claves que están o se han asociado con directivas. Cuando restaure su claves, encontrará contenido cifrarse con las claves anteriores. Por ejemplo, mientras buzones activos se vuelva a cifrarán con frecuencia, como inactiva, buzones desconectados y deshabilitados aún se cifran con las claves anteriores. SharePoint Online realiza copia de seguridad de contenido para fines de restauración y recuperación, por lo que puede haber contenido archivado con las claves antiguas.<br/> Para garantizar la seguridad de los datos, SharePoint Online le permitirá no más de una operación de deshacer clave estén en curso en un momento. Si desea aplicar ambas de las claves en una cámara de clave, que necesitará para esperar a la primera operación roll clave totalmente completa. Nuestra recomendación es escalonar las operaciones clave roll en intervalos diferentes, por lo que no es un problema. 
  
Cuando restaure una clave, que va a solicitar una nueva versión de una clave existente. Para solicitar una nueva versión de una clave existente, se usa el cmdlet mismo, [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), con la misma sintaxis que usan para crear la clave en primer lugar.
  
Por ejemplo:
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

En este ejemplo, dado que una clave denominada **Contoso-O365EX-NA-VaultA1-Key001** ya existe en la cámara **Contoso-O365EX-NA-VaultA1** , se creará una nueva versión de la clave. La operación agrega una nueva versión de la clave. Esta operación mantiene las versiones anteriores de clave en el historial de versiones de la clave, por lo que aún se pueden descifrar los datos cifrados anteriormente con esa clave. Una vez haya completado la constante cualquier tecla que está asociada con una DEP, a continuación, debe ejecutar un cmdlet adicional para asegurarse de que clave de cliente comienza con la nueva clave. 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>Habilitar Exchange Online y Skype para la empresa usar una nueva clave después de restaurar o girar claves en Azure clave de cámara

Cuando se lleve a cabo cualquiera de las claves de Azure clave depósito asociadas con una DEP se usan con Exchange Online y Skype para la empresa, debe ejecutar el siguiente comando para actualizar la característica DEP y habilitar Office 365 comenzar a usar la nueva clave.
  
Para indicar a la clave de cliente para usar la nueva clave para cifrar los buzones de correo en Office 365, ejecute el cmdlet Set-DataEncryptionPolicy como sigue:
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

Dentro de 48 horas, los buzones de correo activa cifradas mediante esta directiva se asociará con la clave actualizada. Utilice los pasos en [Determine la DEP asignada a un buzón de correo](controlling-your-data-using-customer-key.md#DeterminemailboxDEP) para comprobar el valor de la propiedad DataEncryptionPolicyID para el buzón de correo. Una vez que se ha aplicado la clave actualizada, se cambiará el valor de esta propiedad. 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>Habilitar SharePoint Online y OneDrive para la empresa usar una nueva clave después de restaurar o girar claves en Azure clave de cámara

Cuando se lleve a cabo cualquiera de las claves de Azure clave depósito asociadas con una DEP se usan con SharePoint Online y OneDrive para la empresa, debe ejecutar el cmdlet [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) para actualizar la característica DEP y habilitar Office 365 comenzar a usar la nueva clave. 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

Esto se iniciará la operación roll clave para SharePoint Online y OneDrive para la empresa. Esta acción no es inmediata. Para ver el progreso de la clave de operación de deshacer, ejecute el cmdlet Get-SPODataEncryptionPolicy como sigue:
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a>Administrar los permisos de la clave de cámara
<a name="Managekeyvaultperms"> </a>

Varios cmdlets están disponibles que le permiten ver y, si es necesario, quitar los permisos de cámara clave. Es posible que necesite quitar permisos, por ejemplo, cuando un empleado deja el equipo.
  
Para ver los permisos de la clave de cámara, ejecute el cmdlet Get-AzureRmKeyVault:
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

Por ejemplo:
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

Para quitar permisos de un administrador, ejecute el cmdlet Remove-AzureRmKeyVaultAccessPolicy:
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
-UserPrincipalName <UPN of user>
```

Por ejemplo:
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Determinar la DEP asignada a un buzón de correo
<a name="DeterminemailboxDEP"> </a>

Para determinar la DEP asignada a un buzón de correo, use el cmdlet Get-MailboxStatistics. El cmdlet devuelve un identificador único (GUID).
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

Donde *GeneralMailboxOrMailUserIdParameter* especifica un buzón de correo. Para obtener más información acerca del cmdlet Get-MailboxStatistics, vea [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).
  
Usar el GUID para averiguar el nombre descriptivo de la característica DEP al que está asignado el buzón de correo ejecutando el cmdlet siguiente.
  
```
Get-DataEncryptionPolicy <GUID>
```

Donde *GUID* es el GUID devuelto por el cmdlet Get-MailboxStatistics en el paso anterior. 
  


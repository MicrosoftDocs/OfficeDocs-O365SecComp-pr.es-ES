---
title: Configurar directivas de supervisión para su organización
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: Configure las directivas de revisión de supervisión para capturar las comunicaciones de los empleados para su revisión.
ms.openlocfilehash: 92630b1405af6e297390751d9b00e24a82e03087
ms.sourcegitcommit: f0e3c9de0b545081a4d264f74559b941f6c71410
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "31958629"
---
# <a name="configure-supervision-policies-for-your-organization"></a>Configurar directivas de supervisión para su organización

Usar directivas de supervisión para capturar las comunicaciones de los empleados para que las examinen los revisores externos o internos. Para obtener más información sobre cómo las directivas de supervisión pueden ayudarle a supervisar las comunicaciones en su organización, consulte [directivas de supervisión en Office 365](supervision-policies.md).

> [!NOTE]
> Los usuarios supervisados por directivas de supervisión deben tener una licencia de cumplimiento de Microsoft 365 E5, una licencia de Office 365 Enterprise E3 con el complemento de cumplimiento avanzado o incluirse en una suscripción a Office 365 Enterprise E5.
Si no tiene un plan existente de Enterprise E5 y desea intentar la supervisión, puede [registrarse para obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).
  
Siga estos pasos para configurar y usar la supervisión en su organización de Office 365:
  
- **Paso 1 (opcional)** - [configurar grupos para supervisión (opcional)](#step-1---set-up-groups-for-supervision-optional)

    Antes de empezar a usar la supervisión, determine quién necesita las comunicaciones revisadas y quién realizará las revisiones. Si quiere empezar solo con unos pocos usuarios para ver cómo funciona la supervisión, puede omitir la configuración de grupos por ahora.

- **Paso 2 (obligatorio)** - [hacer que la supervisión esté disponible en su organización (obligatorio)](#step-2---make-supervision-available-in-your-organization-required)

    Se agrega al grupo de funciones de revisión de supervisión para que pueda configurar directivas. Cualquier usuario que tenga este rol asignado puede tener acceso a la página **supervisión** en el centro de cumplimiento. Si el correo electrónico que se puede rever está hospedado en Exchange Online, cada revisor debe tener [acceso remoto de PowerShell a Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

- **Paso 3 (opcional)** - [crear tipos personalizados de información confidencial y diccionarios de palabras clave personalizados](#step-3---create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)

    Si necesita un tipo de información confidencial personalizado o un diccionario de palabras clave personalizado para la Directiva de supervisión, debe crearlo antes de iniciar el Asistente para la supervisión.

- **Paso 4 (obligatorio)** - [configurar una directiva de supervisión](#step-4---set-up-a-supervision-policy-required)

    Las directivas de supervisión se crean en el centro de cumplimiento. Estas directivas definen qué comunicaciones están sujetas a revisión en su organización y especifica quién realiza las revisiones. Las comunicaciones incluyen el correo electrónico y las comunicaciones de Microsoft Teams y las comunicaciones de la plataforma de terceros (como Facebook, Twitter, etc.).

- **Paso 5: (opcional)** [Probar la Directiva de supervisión](#step-5---test-your-supervision-policy-optional)

    Pruebe la Directiva de supervisión para asegurarse de que funciona según lo deseado. Es importante asegurarse de que la estrategia de cumplimiento cumple los estándares.

- **Paso 6: (opcional)** [Configurar Outlook para revisores que no desean usar el panel de supervisión de Office 365 o Outlook en la web (anteriormente conocido como Outlook Web App) para revisar las comunicaciones](#step-6---configure-outlook-for-reviewers-optional) supervisadas

    Configure Outlook para proporcionar a los revisores acceso a la funcionalidad de supervisión del cliente de Outlook para que puedan evaluar y clasificar cada elemento.

## <a name="step-1---set-up-groups-for-supervision-optional"></a>Paso 1: configurar grupos para supervisión (opcional)

 Al crear una directiva de supervisión, se define quién ha revisado sus comunicaciones y quién realiza las revisiones. En la Directiva, usará direcciones de correo electrónico para identificar personas o grupos de personas. Para simplificar la configuración, puede crear grupos para los usuarios que tengan su comunicación revisada y grupos para los usuarios que revisen dichas comunicaciones. Si está usando grupos, es posible que necesite varios. Por ejemplo, desea supervisar las comunicaciones entre dos grupos de personas distintas o si desea especificar un grupo que no se va a supervisar.

Use el siguiente gráfico para ayudarle a configurar los grupos de su organización para las directivas de supervisión:

| **Miembro de la Directiva** | **Grupos admitidos** | **Grupos no admitidos** |
|:-----|:-----|:-----|
|Usuarios superVisados | Grupos de distribución <br> Grupos de Office 365 | Grupos de distribución dinámicos |
| Reviewers | Grupos de seguridad habilitados para correo  | Grupos de distribución <br> Grupos de distribución dinámicos |
  
Para administrar usuarios supervisados en grandes organizaciones empresariales, es posible que necesite supervisar a todos los usuarios en grupos grandes. Puede usar PowerShell para configurar un grupo de distribución para una directiva de supervisión global para el grupo asignado. Esto le permite supervisar miles de usuarios con una sola directiva y mantener la Directiva de supervisión actualizada a medida que los empleados nuevos se unen a su organización.

1. Cree un [grupo de distribución](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps) dedicado para la Directiva de supervisión global con las siguientes propiedades: Asegúrese de que este grupo de distribución no se use para otros fines u otros servicios de Office 365.

    - **MemberDepartRestriction = cerrado**. Garantiza que los usuarios no puedan quitar a sí mismos del grupo de distribución.
    - **MemberJoinRestriction = cerrado**. Garantiza que los usuarios no pueden agregarse a sí mismos al grupo de distribución.
    - **ModerationEnabled = true**. Garantiza que todos los mensajes enviados a este grupo están sujetos a aprobación y que el grupo no se está usando para comunicarse fuera de la configuración de la Directiva de supervisión.

    ```
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```
2. Seleccione un [atributo personalizado de Exchange](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) sin usar para realizar un seguimiento de los usuarios agregados a la Directiva de supervisión de su organización.

3. Ejecute el siguiente script de PowerShell en una programación recurrente para agregar usuarios a la Directiva de supervisión:

    ```
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

Para obtener más información acerca de la configuración de grupos, vea:
- [Crear y administrar grupos de distribución](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Administrar grupos de seguridad habilitados para correo](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Información general sobre los grupos de Office 365](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2---make-supervision-available-in-your-organization-required"></a>Paso 2: hacer que la supervisión esté disponible en su organización (obligatorio)

Para que la **supervisión** esté disponible como una opción de menú en el centro de cumplimiento, debe tener asignado el rol de administrador de revisión de supervisión.
  
Para ello, puede agregarse como miembro del grupo de funciones de revisión de supervisión, o bien puede crear un grupo de roles.
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>Adición de miembros al grupo de roles de revisión de supervisión

1. Inicie sesión [https://protection.office.com](https://protection.office.com) con las credenciales de una cuenta de administrador en la organización de Office 365.

2. En el centro de cumplimiento, vaya a **permisos**.

3. Seleccione el grupo de roles **revisión de supervisión** y, a continuación, haga clic en el icono Editar.

4. En la sección **miembros** , agregue las personas que desea que administren la supervisión de su organización.

### <a name="create-a-new-role-group"></a>Crear un nuevo grupo de roles

1. Inicie sesión [https://protection.office.com](https://protection.office.com) con las credenciales de una cuenta de administrador en la organización de Office 365.

2. En el centro de cumplimiento, vaya a **permisos** y, después,**+** haga clic en Agregar ().

3. En la sección **roles** , haga clic en**+** agregar () y desplácese hacia abajo hasta **Administrador de revisión de supervisión**. Agregue este rol al grupo de roles.

4. En la sección **miembros** , agregue las personas que desea que administren la supervisión de su organización.

Para obtener más información acerca de los grupos de roles y los permisos, consulte perMissions [in the Compliance Center](permissions-in-the-security-and-compliance-center.md).

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>Habilitar el acceso remoto de PowerShell para revisores (si el correo electrónico se hospeda en Exchange Online)

1. Siga las instrucciones de [habilitar o deshabilitar el acceso a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

## <a name="step-3---create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a>Paso 3: crear tipos personalizados de información confidencial y diccionarios de palabras clave personalizados (opcional)

Para elegir entre los tipos de información confidencial personalizados existentes o los diccionarios de palabras clave personalizados en el Asistente para directivas de supervisión, primero debe crear estos elementos si es necesario.

### <a name="create-custom-keyword-dictionarylexicon-optional"></a>Crear Diccionario o léxico personalizado de palabra clave (opcional)

Use un editor de texto (como el Bloc de notas) para crear un nuevo archivo que incluya los términos de palabra clave que desea supervisar en una directiva de supervisión. Asegúrese de que cada término está en una línea independiente y guarde el archivo en formato **Unicode/UTF-16 (Little endian)** .

### <a name="create-custom-sensitive-information-types"></a>Crear tipos personalizados de información confidencial

1. Cree un nuevo tipo de información confidencial y agregue el diccionario personalizado en el centro de seguridad & cumplimiento de Office 365. Navegue hasta **** \> **tipos de información confidencial** de clasificaciones y siga los pasos del **Asistente para nuevos tipos de información confidencial**. Aquí podrá:

    - Definir un nombre y una descripción para el tipo de información confidencial
    - Definir los elementos de proximidad, nivel de confianza y patrón principal
    - Importe el diccionario personalizado como requisito para el elemento correspondiente
    - Revisar las selecciones y crear el tipo de información confidencial

    Para obtener información más detallada, consulte [crear un tipo personalizado de información confidencial](create-a-custom-sensitive-information-type.md) y [crear un diccionario de palabras clave](create-a-keyword-dictionary.md)

    Una vez creado el diccionario o léxico personalizado, puede ver las palabras clave configuradas con el cmdlet [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) o agregar y quitar términos con el cmdlet [set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) .

## <a name="step-4---set-up-a-supervision-policy-required"></a>Paso 4: configurar una directiva de supervisión (obligatorio)
  
1. Inicie sesión [https://protection.office.com](https://protection.office.com) con las credenciales de una cuenta de administrador en la organización de Office 365.

2. En el centro de cumplimiento, seleccione **supervisión**.
  
3. Seleccione **crear** y, a continuación, siga el Asistente para configurar las siguientes páginas de la Directiva. Con el asistente, podrá:

    - Asigne un nombre y una descripción a la Directiva.
    - Elija los usuarios o grupos que desea supervisar, incluida la elección de los usuarios o grupos que quiera excluir.
    - Definir las condiciones de la Directiva de supervisión.
    - Elija si le gustaría incluir tipos de información confidencial. Aquí puede seleccionar los tipos de información confidencial predeterminada y personalizado.
    - Definir el porcentaje de comunicaciones que se van a revisar.
    - Elija los revisores para la Directiva. Los revisores pueden ser usuarios individuales o [grupos de seguridad habilitados para correo](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group). Todos los revisores deben tener buzones hospedados en Exchange Online.
    - Revise las selecciones de la Directiva y cree la Directiva.

## <a name="step-5---test-your-supervision-policy-optional"></a>Paso 5: probar la Directiva de supervisión (opcional)

Después de crear una directiva de supervisión, es aconsejable probarla para asegurarse de que la Directiva aplica correctamente las condiciones que ha definido. Es posible que también desee [probar sus directivas de prevención de pérdida de datos (DLP)](create-test-tune-dlp-policy.md) si las directivas de supervisión incluyen tipos de información confidencial. Siga estos pasos para probar la Directiva de supervisión:

1. Abra un cliente de correo electrónico o Microsoft teams que haya iniciado sesión como usuario supervisado definido en la Directiva que desea probar.
2. Envíe un correo electrónico o un chat de Microsoft teams que cumpla los criterios que haya definido en la Directiva de supervisión. Puede ser una palabra clave, el tamaño de los datos adjuntos, el dominio, etc. Asegúrese de determinar si la configuración condicional configurada en la Directiva es demasiado restrictiva o demasiado flexible.

    > [!Note]
    > Los correos electrónicos sujetos a directivas definidas se procesan casi en tiempo real y se pueden probar inmediatamente una vez configurada la Directiva. Los chats de Microsoft Teams pueden tardar hasta 24 horas en procesarse por completo en una directiva. 

3. Inicie sesión en su inquilino de Office 365 como revisor designado en la Directiva de supervisión. Navegue hasta la **supervisión** > de la*Directiva* > personalizada**abierta** para ver el informe de la Directiva.

## <a name="step-6---configure-outlook-for-reviewers-optional"></a>Paso 6: configurar Outlook para revisores (opcional)

Los revisores que quieran usar Outlook en lugar del panel de supervisión en Office 365 para revisar las comunicaciones deben configurar su cliente de Outlook.

### <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a>Paso 1: copiar la dirección del buzón de supervisión

Para configurar la revisión para escritorio de Outlook o Outlook para la web, necesita la dirección del buzón de supervisión creado como parte de la configuración de la Directiva de supervisión.
  
> [!NOTE]
> Si otra persona creó la Directiva, debe obtener esta dirección para instalar el complemento.

 **Para buscar la dirección del buzón de supervisión**
  
1. Inicie sesión en el [centro de cumplimiento](https://compliance.microsoft.com) usando credenciales para una cuenta de administrador de su organización.

2. Vaya a **supervisión**.

3. Seleccione una directiva de supervisión para las comunicaciones que quiera revisar.

4. En el control flotante detalles de la Directiva, en **buzón de supervisión**, copie la dirección.<br/>![Sección "buzón de supervisión" de un control flotante de la Directiva de supervisión que muestra la dirección del buzón de supervisión resaltada](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
### <a name="step-2-configure-the-supervision-mailbox-for-outlook-access"></a>Paso 2: configurar el buzón de supervisión para Outlook Access

A continuación, los revisores tienen que ejecutar un par de comandos de PowerShell de Exchange Online para que puedan conectar Outlook al buzón de supervisión.
  
1. Conexión al PowerShell de Exchange Online. [Pasos que seguir](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)

2. Ejecute los siguientes comandos, donde *SupervisoryReview {GUID} @domain. onmicrosoft.com* es la dirección que copió en el paso 1 anterior y *User* es el nombre del revisor que se conectará al buzón de supervisión en el paso 3.

    ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```

    ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```

3. Espere al menos una hora antes de continuar con el paso 3.

### <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a>Paso 3: crear un perfil de Outlook para conectar con el buzón de supervisión

En el último paso, los revisores tienen que crear un perfil de Outlook para conectarse al buzón de correo de supervisión.

> [!NOTE]
> Para crear un nuevo perfil de Outlook, use la configuración de correo en el panel de control de Windows. La ruta de acceso que realice para obtener esta configuración puede depender del sistema operativo Windows (Windows 7, Windows 8 o Windows 10) que esté usando y de la versión de Outlook que esté instalada.
  
1. Abra el panel de control. En el cuadro de **búsqueda** de la parte superior de la ventana, escriba **correo**.<br/>(¿No está seguro de cómo llegar al panel de control? Consulte [¿Dónde está el panel de control?](https://support.microsoft.com/help/13764/windows-where-is-control-panel))
  
2. Abra la aplicación de **correo** .

3. En **configuración de correo: Outlook**, haga clic en **Mostrar perfiles**.<br/>![Cuadro de diálogo "configuración de correo: Outlook" con el botón "Mostrar perfiles" resaltado](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)
  
4. En **correo**, haga clic en **Agregar**. A continuación, en **nuevo perfil**, escriba un nombre para el buzón de correo de supervisión (como **supervisión**).<br/>![El cuadro de diálogo "nuevo perfil" que muestra el nombre "supervisión" en el cuadro "nombre del perfil"](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)
  
5. En **conectar Outlook a Office 365**, haga clic en **conectar con una cuenta diferente**.<br/>![El mensaje "conectar Outlook a Office 365" con el vínculo "conectar a otra cuenta" resaltado](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)
  
6. En **configuración automática**de la cuenta, elija **configuración manual o tipos de servidores adicionales**y, a continuación, haga clic en **siguiente**.

7. En **elegir el tipo de cuenta**, elija **Office 365**. A continuación, en el cuadro **dirección de correo electrónico** , escriba la dirección del buzón de supervisión que copió anteriormente.<br/>![La página "Elija el tipo de cuenta" del cuadro de diálogo "Agregar cuenta" de Outlook que muestra el cuadro "dirección de correo electrónico" resaltado.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)
  
8. Cuando se le solicite, escriba sus credenciales de Office 365.

9. Si se ejecuta correctamente, verá la carpeta **supervisión \<: nombre\> de directiva** que aparece en la vista lista de carpetas de Outlook.

## <a name="powershell-reference"></a>Referencia de PowerShell

Si es necesario, puede crear y administrar directivas de supervisión con los siguientes cmdlets de PowerShell:

- [New-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [Get-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [Set-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [Remove-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [New-SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [Set-SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [Get-SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [Get-SupervisoryReviewOverallProgressReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [Get-SupervisoryReviewTopCasesReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)
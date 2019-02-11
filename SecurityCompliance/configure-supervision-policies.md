---
title: Configurar directivas de supervisión para su organización
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: Configurar las directivas de una revisión de supervisión para capturar las comunicaciones de los empleados para su revisión.
ms.openlocfilehash: 898ef9951ea20dec1e0cc6c28ad1ed6f9a0ded6e
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29768041"
---
# <a name="configure-supervision-policies-for-your-organization"></a>Configurar directivas de supervisión para su organización

Usar directivas de supervisión para capturar a las comunicaciones de los empleados para examen por revisores internos o externos. Para obtener más información acerca de cómo las directivas de supervisión pueden ayudarle a supervisar las comunicaciones en la organización, vea [las directivas de supervisión de Office 365](supervision-policies.md).

> [!NOTE]
> Los usuarios supervisados por las directivas de supervisión deben tener una licencia de acceso E3 Enterprise de Office 365 con el complemento de cumplimiento avanzadas o estar incluidos en una suscripción a Office 365 Enterprise E5. Si no tiene un plan de empresa E5 existente y desea probar supervisión, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).
  
Siga estos pasos para configurar y usar la supervisión de la organización de Office 365:
  
- **Paso 1 (opcional)** - [Configurar grupos para supervisión](configure-supervision-policies.md#exampledist)

    Antes de empezar a usar la supervisión, determine quién habrá sus comunicaciones ha revisado y quién llevará a cabo las revisiones. Si desea empezar a trabajar con unos pocos usuarios para ver cómo funciona la supervisión, puede omitir la configuración de grupos de por ahora.

- **Paso 2 (obligatorio)** - [realizar supervisión disponible en la organización](configure-supervision-policies.md#MakeAvailable)

    Agregarse al grupo de funciones de revisión de supervisión por lo que puede configurar las directivas. Cualquier persona que tiene este rol asignado puede tener acceso a la página de **supervisión** en el **Gobierno de datos** en el centro de cumplimiento de seguridad &. Si el correo electrónico que se debe revisar está hospedado en Exchange Online, cada revisor también debe tener [el acceso remoto a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

- **Paso 3 (opcional)** - [Configurar tipos de información confidencial personalizada o palabra clave custom diccionarios/políticas](configure-supervision-policies.md#sensitiveinfo)

    Si necesita usar un tipo de información confidencial personalizado o un diccionario personalizado de palabra clave para la directiva de supervisión, debe crear antes de iniciar al Asistente para la supervisión.

- **Paso 4 (obligatorio)** - [Configurar una directiva de supervisión](configure-supervision-policies.md#setupsuper)

    Va a crear directivas de supervisión en el centro de cumplimiento de seguridad &. Estas directivas se definen las comunicaciones que están sujetas a la revisión de la organización y especifica que debe llevar a cabo las revisiones. Las comunicaciones incluyen correo electrónico y comunicaciones de Microsoft Teams, así como comunicaciones de plataforma 3rd terceros (por ejemplo, Facebook, Twitter, etcetera.)

- **Paso 5: (opcional)** [Prueba la nueva directiva de supervisión](configure-supervision-policies.md#TestPolicy)

    Probar la directiva de supervisión para asegurarse de que funciona como se desee es una parte importante de asegurarse de que la estrategia de cumplimiento de normas cumple los estándares.

- **Paso 6: (opcional)** [Configuración de complemento de Outlook para los revisores que no desea usar el panel de supervisión de Office 365 u OWA para revisar las comunicaciones](configure-supervision-policies.md#UseOutlook)

    El complemento de supervisión para Outlook proporciona a los revisores acceso a la derecha de la funcionalidad de supervisión en el cliente de Outlook para que puedan evaluar y clasificar cada elemento.

<a name="exampledist"> </a>

## <a name="step-1---set-up-groups-for-supervision-optional"></a>Paso 1: configurar grupos de supervisión (opcional)

 Cuando se crea una directiva de supervisión, determinará que van a tener sus comunicaciones revisado y quién llevará a cabo las revisiones. En la directiva, debe usar direcciones de correo electrónico para identificar los individuos o grupos de personas. Para simplificar el programa de instalación, crear grupos para las personas que tendrán su comunicación revisado y grupos para las personas que va a revisar las comunicaciones. Si usa grupos, puede que necesite varios — por ejemplo, si desea supervisar las comunicaciones entre dos grupos distintos de personas, o si desea especificar un grupo que no se va a ser supervisados. Para obtener información detallada acerca de cómo funciona esto, vea [grupos de distribución de ejemplo](configure-supervision-policies.md#GroupExample) .
  
Para supervisar las comunicaciones entre o dentro de los grupos de la organización, configurar los grupos de distribución en el centro de administración de Exchange (vaya a **destinatarios** \> **grupos**). Para obtener más información acerca de cómo configurar grupos de distribución, vea [Administrar grupos de distribución](http://go.microsoft.com/fwlink/?LinkId=613635)
  
> [!NOTE]
> También puede usar los grupos de distribución dinámicos o grupos de seguridad para la supervisión si lo prefiere. Para ayudarle a decidir si estas mejor más adecuado para su organización necesita, vea [Administrar grupos de seguridad habilitados para correo](http://go.microsoft.com/fwlink/?LinkId=627033)y [Administrar grupos de distribución dinámica](http://go.microsoft.com/fwlink/?LinkId=627058).
  
<a name="GroupExample"> </a>

### <a name="example-distribution-groups"></a>Grupos de distribución de ejemplo

En este ejemplo se incluye un grupo de distribución que se ha configurado para una organización financiera denominada Contoso financiera internacional.
  
En Contoso Financial International, se debe supervisar un muestreo de las comunicaciones entre los agentes de los Estados Unidos. Sin embargo, los responsables de cumplimiento normativo dentro de ese grupo no requieren supervisión. En este ejemplo, podemos crear los siguientes grupos:
  
|**Configurar este grupo de distribución**|**Dirección del grupo (alias)**|**Descripción**|
|:-----|:-----|:-----|
|Todos los agentes de Estados Unidos | US_Brokers@contoso.com | Este grupo incluye las direcciones de correo electrónico de todos los agentes en Estados Unidos que trabajan para Contoso. |
| Todos los responsables de cumplimiento de Estados Unidos | US_Compliance@contoso.com  | Este grupo incluyen direcciones de correo electrónico para todos los agentes de cumplimiento en Estados Unidos que trabajan para Contoso. Dado que este grupo es un subconjunto de todos los agentes en Estados Unidos, puede usar este alias para agentes de cumplimiento exentos de una directiva de supervisión. |
  
<a name="MakeAvailable"> </a>

## <a name="step-2---make-supervision-available-in-your-organization-required"></a>Paso 2: asegúrese de supervisión disponible en la organización (obligatorio)

Para hacer que la **supervisión** que está disponible como una opción de menú en el centro de cumplimiento de seguridad &, debe tener asignado el rol de administrador de la revisión de supervisión.
  
Para ello, puede agregarse como un miembro del grupo de roles de revisión de supervisión o puede crear un nuevo grupo de funciones.
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>Agregar a miembros a un grupo de roles de la revisión de supervisión

1. Iniciar sesión en [https://protection.office.com](https://protection.office.com) uso de credenciales para una cuenta de administrador de la organización de Office 365.

2. En el centro de cumplimiento de seguridad &, vaya a **permisos**.

3. Seleccione el grupo de roles de **Revisión de supervisión** y, a continuación, haga clic en el icono de edición.

4. En la sección **miembros** , agregue las personas que desea administrar la supervisión para su organización.

### <a name="create-a-new-role-group"></a>Crear un nuevo grupo de roles

1. Iniciar sesión en [https://protection.office.com](https://protection.office.com) uso de credenciales para una cuenta de administrador de la organización de Office 365.

2. En el centro de cumplimiento de seguridad &, vaya a **permisos** y, a continuación, haga clic en Agregar (**+**).

3. En la sección **Roles** , haga clic en Agregar (**+**) y desplácese hacia abajo de la **Supervisión de revisión de administrador**. Agregue esta función al grupo de funciones.

4. En la sección **miembros** , agregue las personas que desea administrar la supervisión para su organización.

Para obtener más información sobre grupos de roles y los permisos, vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>Habilitar el acceso remoto de PowerShell para revisores (si el correo electrónico se hospeda en Exchange Online)

1. Siga las instrucciones en [Habilitar o deshabilitar el acceso a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

<a name="sensitiveinfo"> </a>
  
## <a name="step-3---create-custom-sensitive-information-types-or-custom-keyword-dictionaries-optional"></a>Paso 3: crear diccionarios de palabra clave personalizados o tipos de información confidencial personalizado (opcional)

Con el fin de elegir entre los tipos de información confidencial personalizadas existentes o diccionarios de palabra clave personalizada en el Asistente para la directiva de supervisión, primero debe crear estos elementos si es necesario.

### <a name="create-custom-sensitive-information-types"></a>Crear tipos de información confidencial personalizado

1. Crear un nuevo tipo de información confidencial en el centro de cumplimiento de seguridad de Office 365 &. Vaya a **las clasificaciones** \> **tipos de información confidencial** y siga los pasos descritos en el **Asistente para nuevo tipo de información confidencial**. Aquí podrá:

    - Definir un nombre y una descripción para el tipo de información confidencial
    - Definir la proximidad, nivel de confianza y elementos de patrón principal
    - Revise las selecciones y crear el tipo de información confidencial

    Para obtener información más detallada, vea [crear un tipo de información confidencial personalizada](create-a-custom-sensitive-information-type.md).

### <a name="create-custom-keyword-dictionarylexicon"></a>Crear diccionario/política de palabra clave personalizados

1. Con un editor de texto (como el Bloc de notas), cree un nuevo archivo que incluye los términos de palabra clave que le gustaría supervisar en una directiva de supervisión. Asegúrese de que cada término se encuentra en una línea independiente y guarde el archivo en el formato **Unicode o UTF-16 (Little Endian)** .
2. Importar el archivo de palabras clave en el inquilino de Office 365 con PowerShell. Para conectarse a Office 365 con PowerShell, vea [Connect to & PowerShell de centro de cumplimiento de seguridad de Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

    Una vez conectado a Office 365 con PowerShell, ejecute los siguientes comandos para importar el diccionario de palabras clave:

    ```
    $fileData = Get-Content "your keyword path and file name" -Encoding Byte -ReadCount 0

    New-DlpKeywordDictionary -Name "Name for your keyword dictionary" -Description "optional description for your keyword dictionary" -FileData $fileData
    ```
    Para obtener información más detallada, vea [crear un diccionario de palabra clave](create-a-keyword-dictionary.md).

3. Crear un nuevo tipo de información confidencial en el centro de cumplimiento de seguridad de Office 365 &. Vaya a **las clasificaciones** \> **tipos de información confidencial** y siga los pasos descritos en el **Asistente para nuevo tipo de información confidencial**. Aquí podrá:

    - Definir un nombre y una descripción para el tipo de información confidencial
    - Agregar el diccionario personalizado como un requisito para el elemento coincidente
    - Revise las selecciones y crear el tipo de información confidencial

    Una vez creado el vocabulario/diccionario personalizado, puede ver las palabras clave configuradas con el cmdlet [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) o agregar y quitar términos usando el cmdlet [Set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) .

    Para obtener información más detallada, vea [crear un tipo de información confidencial personalizada](create-a-custom-sensitive-information-type.md).

<a name="setupsuper"> </a>

## <a name="step-4---set-up-a-supervision-policy-required"></a>Paso 4: configurar una directiva de supervisión (obligatorio)
  
1. Iniciar sesión en [https://protection.office.com](https://protection.office.com) uso de credenciales para una cuenta de administrador de la organización de Office 365.

2. En el centro de cumplimiento de seguridad &, seleccione **supervisión**.
  
3. Seleccione **crear** y, a continuación, siga el Asistente para configurar las siguientes páginas de la directiva. Mediante el asistente, hará lo siguiente:

    - Asigne a la directiva un nombre y una descripción.
    - Elija los usuarios o grupos para supervisar, incluida la elección de los usuarios o grupos que desea excluir.
    - Definir las condiciones de la directiva de supervisión.
    - Elija si desea incluir los tipos de información confidencial. Aquí es donde puede seleccionar predeterminado y tipos de información confidencial personalizado.
    - Definir el porcentaje de comunicaciones para revisar.
    - Elija los revisores de la directiva. Los revisores pueden los usuarios individuales o [grupos de seguridad habilitados para correo](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).
    - Revise las selecciones de directiva y crear la directiva.

<a name="TestPolicy"> </a>

## <a name="step-5---test-your-supervision-policy-optional"></a>Paso 5: probar la directiva de supervisión (opcional)

Después de crear una directiva de supervisión, es una buena idea para probar para asegurarse de que se está aplicando correctamente las condiciones que haya definido por la directiva. Es posible que también desee [probar las directivas de prevención (DLP) de pérdida de datos](create-test-tune-dlp-policy.md) si las directivas de supervisión incluyen tipos de información confidencial. Siga los pasos siguientes para probar la directiva de supervisión:

1. Abrir un cliente de correo electrónico o Microsoft Teams iniciado sesión como un usuario supervisado definido en la directiva que desea probar.
2. Enviar un correo electrónico o chat de Microsoft Teams que cumpla los criterios que haya definido en la directiva de supervisión. Esto puede ser una palabra clave, el tamaño de datos adjuntos, el dominio, etcetera. Asegúrese de que es determinar si los valores condicionales configurados en la directiva es demasiado restrictivo o demasiado flexible.

    > [!Note]
    > Mensajes de correo electrónico sujetos a directivas definidas se procesan en casi en tiempo real y se pueden probar inmediatamente después de configurar la directiva. Chats en Microsoft Teams pueden tardar hasta 24 horas para procesar completamente en una directiva. 

3. Inicie sesión en el inquilino de Office 365 como un revisor designado en la directiva de supervisión. Vaya a **supervisión** > *Su directiva personalizada* > **abiertos** para ver el informe de la directiva.

<a name="UseOutlook"> </a>

## <a name="step-6---set-up-outlook-add-in-for-reviewers-optional"></a>Paso 6: configuración de complemento de Outlook para los revisores (opcional)

Los revisores que desea usar Outlook en lugar de usar el panel de supervisión en Office 365 o Outlook en la web para revisar las comunicaciones deben instalar el complemento de supervisión para su cliente de Outlook.

### <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a>Paso 1: Copiar la dirección para el buzón de supervisión

Para instalar el complemento para escritorio de Outlook, necesitará la dirección para el buzón de supervisión que se creó como parte de la configuración de directiva de supervisión.
  
> [!NOTE]
> Si otra persona creó la directiva, debe obtener esta dirección de ellas para instalar el complemento.

 **Para buscar la dirección del buzón de correo de supervisión**
  
1. Inicie sesión en la [seguridad &amp; centro de cumplimiento](https://protection.office.com) uso de credenciales para una cuenta de administrador de la organización de Office 365.

2. Vaya a **supervisión**.

3. Haga clic en la directiva de supervisión que está recopilando a las comunicaciones que desee revisar.

4. En la emergente de detalles de directiva, en **el buzón de correo de supervisión**, copie la dirección.<br/>![La sección 'Buzón de correo de supervisión' de emergente de detalles de una directiva de supervisión que muestra la dirección del buzón de correo de supervisión resaltada](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
### <a name="step-2-configure-the-supervision-mailbox-for-outlook-desktop-access"></a>Paso 2: Configurar el buzón de supervisión para el acceso al escritorio de Outlook

A continuación, los revisores tendrá que ejecutar los comandos de PowerShell en Exchange Online un par para que puedan conectarse a Outlook en el buzón de supervisión.
  
1. Conectarse a Exchange Online PowerShell. [¿Cómo hacerlo?](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)

2. Ejecute los comandos siguientes, donde *SupervisoryReview{GUID}@domain.onmicrosoft.com* es la dirección que copió en el paso 1 más arriba, y el *usuario* es el nombre del revisor que van a conectar con el buzón de correo de supervisión en el paso 3.

    ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```

    ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```

3. Espere al menos una hora antes de pasar al paso 3 por debajo.

### <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a>Paso 3: Crear un perfil de Outlook para conectar con el buzón de supervisión

Para el paso final, revisores será necesario crear un perfil de Outlook para conectar con el buzón de supervisión.

> [!NOTE]
> Para crear un nuevo perfil de Outlook, usará la configuración de correo en el Panel de Control de Windows. La ruta de acceso que hay que realizar para tener acceso a estas opciones es posible que dependen de qué sistema operativo de Windows (Windows 7, Windows 8 o Windows 10) utiliza y se instala la versión de Outlook.
  
1. Abra el Panel de Control y, en el cuadro de **búsqueda** en la parte superior de la ventana, escriba **correo**.<br/>¿(No está seguro de cómo obtener el panel de Control? Vea [donde es el Panel de Control?](https://support.microsoft.com/help/13764/windows-where-is-control-panel))
  
2. Abra la aplicación de **correo** .

3. En la **Configuración de correo - Outlook**, haga clic en **Mostrar perfiles**.<br/>![La 'configuración de correo - Outlook' cuadro de diálogo con el botón 'Mostrar perfiles' resaltado](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)
  
4. En **correo**, haga clic en **Agregar**. A continuación, en **Nuevo perfil**, escriba un nombre para el buzón de correo de supervisión (por ejemplo, **supervisión**).<br/>![El cuadro de diálogo 'Nuevo perfil' que muestra el nombre 'Supervisión' en el cuadro Nombre del perfil](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)
  
5. En **Outlook conectarse a Office 365**, haga clic en **Conectar a una cuenta diferente**.<br/>![El mensaje 'Outlook conectarse a Office 365' con el vínculo 'Conectar con una cuenta diferente' resaltado](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)
  
6. En la **Configuración automática de cuenta**, elija **el programa de instalación Manual o tipos de servidores adicionales**y, a continuación, haga clic en **siguiente**.

7. En **Elija el tipo de cuenta**, elija **Office 365**. A continuación, en el cuadro **Dirección de correo electrónico** , escriba la dirección del buzón de supervisión que copió anteriormente.<br/>![La página 'Elija su tipo de cuenta' del cuadro de diálogo 'Agregar cuenta' en Outlook que muestra el cuadro 'Dirección de correo electrónico' resaltado.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)
  
8. Cuando se le solicite, escriba sus credenciales de Office 365.

9. Si tiene éxito, verá el **supervisión - \<nombre de la directiva\> ** carpeta que aparecen en la vista lista de carpetas de Outlook.

## <a name="powershell-reference"></a>Referencia de PowerShell

Si es necesario, puede crear y administrar las directivas de supervisión con los siguientes cmdlets de PowerShell:

- [Nueva SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [Get-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [Set-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [Remove-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [Nueva SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [Set-SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [Get-SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [Get-SupervisoryReviewOverallProgressReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [Get-SupervisoryReviewTopCasesReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)
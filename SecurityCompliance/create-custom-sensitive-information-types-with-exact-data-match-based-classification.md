---
title: Crear un tipo de información confidencial personalizado con coincidencia exacta de datos
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Crear un tipo de información confidencial personalizado con clasificación basada en coincidencia exacta de datos
ms.openlocfilehash: 77a30f7db24e903e7d6859d10edb0cc186441494
ms.sourcegitcommit: 28c104fb6a72d624fab5ac6178b5b0df9fa81484
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2019
ms.locfileid: "36297768"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a>Crear un tipo de información confidencial personalizado con clasificación basada en coincidencia exacta de datos

## <a name="overview"></a>Información general

Los [tipos de información confidencial](https://review.docs.microsoft.com/es-ES/office365/securitycompliance/custom-sensitive-info-types) se usan para ayudar a evitar el uso compartido accidental o inadecuado de información confidencial. Como administrador, puede usar el  [Centro de seguridad y cumplimiento](https://review.docs.microsoft.com/es-ES/office365/securitycompliance/create-a-custom-sensitive-information-type) o [PowerShell](https://review.docs.microsoft.com/es-ES/office365/securitycompliance/create-a-custom-sensitive-information-type-in-scc-powershell) para definir un tipo de información confidencial basado en patrones, evidencia (palabras clave como *empleado*, *insignia*, *id.*, etc.), proximidad de caracteres (la similitud de la evidencia y los caracteres en un patrón determinado) y niveles de confianza. Estos tipos de información confidencial satisfacen las necesidades de negocio para muchas organizaciones.

Pero, ¿qué pasa si quiere un tipo de información confidencial que use valores de datos exactos, en lugar de coincidir solo con patrones genéricos? Con la clasificación basada en coincidencia exacta de datos (EDM), puede crear un tipo de información confidencial personalizado que está diseñado para:

- ser dinámico y actualizable;
- ser más escalable;
- generar menos falsos positivos;
- funcionar con datos confidenciales estructurados;
- trabajar con información confidencial de forma más segura; y
- usarse con varios servicios de nube de Microsoft.

![Clasificación basada en EDM](media/EDMClassification.png)

La clasificación basada en EDM le permite crear tipos de información confidencial personalizados que hacen referencia a valores exactos en una base de datos de información confidencial. La base de datos puede ser actualizada diaria o semanalmente, y puede contener hasta 10 millones de filas de datos. Así que mientras los empleados, clientes o pacientes van y vienen y cambian los registros, los tipos de información confidencial se mantienen al día y aplicables. Y puede usar la clasificación basada en EDM con directivas, como [directivas de prevención de pérdida de datos](https://review.docs.microsoft.com/es-ES/office365/securitycompliance/data-loss-prevention-policies) (DLP) o [directivas de archivo de Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/data-protection-policies).

## <a name="required-licenses-and-permissions"></a>Permisos y licencias necesarios

Debe ser un administrador global, administrador de cumplimiento o administrador de Exchange Online para realizar las tareas descritas en este artículo. Para obtener más información acerca de los permisos de DLP, vea [Permisos](https://review.docs.microsoft.com/es-ES/office365/securitycompliance/data-loss-prevention-policies#permissions).

Cuando esté disponible de forma general, la clasificación basada en EDM se incluirá en estas suscripciones:

- Office 365 E5
- Microsoft 365 E5
- Cumplimiento y protección de la información de Microsoft 365
- Cumplimiento avanzado de Office 365

## <a name="the-work-flow-at-a-glance"></a>El flujo de trabajo de un vistazo

|Fase  |Requisitos  |
|---------|---------|
|[Parte 1: Configurar la clasificación basada en EDM](#part-1-set-up-edm-based-classification)<br/><br/>(Según sea necesario)<br/>- [Editar el esquema de la base de datos](#editing-the-schema-for-edm-based-classification) <br/>- [Quitar el esquema](#removing-the-schema-for-edm-based-classification) |- Acceso de lectura a los datos confidenciales<br/>- Esquema base de datos en formato .xml (ejemplo proporcionado)<br/>- Paquete de reglas en formato .xml (ejemplo proporcionado)<br/>- Permisos de administrador para el Centro de seguridad y cumplimiento (con PowerShell) |
|[Parte 2: Indizar y cargar los datos confidenciales](#part-2-index-and-upload-the-sensitive-data)<br/><br/>(Según sea necesario)<br/>[Actualizar los datos](#refreshing-your-sensitive-information-database) |- Cuenta de usuario y de grupo de seguridad personalizado<br/>- Acceso de administrador local en el equipo con el agente de carga EDM<br/>- Acceso de lectura a los datos confidenciales<br/>- Procesar y programar la actualización de los datos|
|[Parte 3: Usar clasificación basada en EDM con los servicios de nube de Microsoft](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |- Suscripción de Office 365 con DLP<br/>- Característica de clasificación basada en EDM habilitada (en versión preliminar) |

### <a name="part-1-set-up-edm-based-classification"></a>Parte 1: Configurar la clasificación basada en EDM

La configuración de la clasificación basada en EDM implica guardar los datos confidenciales en formato .csv, definir un esquema para la base de datos de información confidencial, crear un paquete de reglas y cargar el paquete de reglas y el esquema.

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a>Definir el esquema de la base de datos de información confidencial

1. Identifique la información confidencial que quiera usar. Exporte los datos a una aplicación, como Microsoft Excel, y guarde el archivo en formato .csv. El archivo de datos puede incluir un máximo de:
      - Hasta 10 millones de filas de datos confidenciales
      - Hasta 32 columnas (campos) por origen de datos
      - Hasta 5 columnas (campos) marcadas como utilizables en búsquedas

2. Estructure los datos confidenciales en el archivo .csv de forma que la primera fila incluya los nombres de los campos que se usan para la clasificación basada en EDM. En el archivo .csv, puede que tenga nombres de campo, como "NSS", "FechaNacimiento", "Nombre", "Apellido", etc. Por ejemplo, nuestro archivo .csv se llama *RegistrosPacientes.csv* e incluye las columnas *IdPaciente*,  *NEM*, *Apellidos*, *Nombre*, *NSS* , etc.

3. Defina el esquema de la base de datos de información confidencial en formato .xml (similar al ejemplo siguiente). Nombre este archivo de esquema edm.xml y configúrelo para que por cada columna de la base de datos haya una línea que use la sintaxis \<Field name="" searchable=""/\>.

      - Use nombres de columna para los valores *Nombre de campo* .
      - Use *searchable="true"* para los campos que quiere que se puedan buscar, hasta un máximo de 5 campos. Debe designar un mínimo de un campo como utilizable para búsqueda.

Por ejemplo, el siguiente archivo .xml define el esquema para una base de datos de registros de pacientes, con cinco campos especificados para la búsqueda: *IdPaciente*, *NEM*,  *NSS*, *Teléfono* y *FechaNacimiento*.

(Puede copiar, modificar y usar nuestro ejemplo).

 ```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
      <DataStore name="PatientRecords" description="Schema for patient records" version="1">
            <Field name="PatientID" searchable="true" />
            <Field name="MRN" searchable="true" />
            <Field name="FirstName" />
            <Field name="LastName" />
            <Field name="SSN" searchable="true" />
            <Field name="Phone" searchable="true" />
            <Field name="DOB" searchable="true" />
            <Field name="Gender" />
            <Field name="Address" />
      </DataStore>
</EdmSchema>
```

4. [Conéctese a PowerShell del Centro de seguridad y cumplimiento de Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

5. Para cargar el esquema de la base de datos, ejecute, uno a la vez, los siguientes cmdlets:

```powershell
$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
```

Se le pedirá que confirme lo siguiente:

> Confirmar
>
> ¿Está seguro de que desea realizar esta acción?
>
> Se importará el nuevo esquema EDM para el almacén de datos "registrospacientes".
>
> ¿\[S\] Sí \[T\] Sí a todo \[N\] No \[A\] No a todo \[?\] Ayuda (el valor predeterminado es "S"):

> [!TIP]
> Si quiere que los cambios se realicen sin confirmación, en el paso 5, use este cmdlet: New-DlpEdmSchema -FileData $edmSchemaXml

> [!NOTE]
> La actualización de EDMSchema con adiciones puede tardar de 10 a 60 minutos. La actualización debe completarse antes de ejecutar los pasos que usan las adiciones.

Ahora que se ha definido el esquema de la base de datos de información confidencial, el siguiente paso es configurar un paquete de reglas. Vaya a la sección [Configurar un paquete de reglas](#set-up-a-rule-package).

#### <a name="editing-the-schema-for-edm-based-classification"></a>Editar el esquema de la clasificación basada en EDM

Si quiere realizar cambios en el archivo edm.xml, como cambiar los campos que se usan para la clasificación basada en EDM, siga estos pasos:

1. Edite el archivo edm.xml (este es el archivo tratado en la sección [Definir el esquema](#define-the-schema-for-your-database-of-sensitive-information) de este artículo).

2. [Conéctese a PowerShell del Centro de seguridad y cumplimiento de Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

3. Para actualizar el esquema de la base de datos, ejecute, uno a la vez, los siguientes cmdlets:

```powershell
$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
```

Se le pedirá que confirme lo siguiente:

> Confirmar
>
> ¿Está seguro de que desea realizar esta acción?
>
> Se actualizará el esquema EDM para el almacén de datos "registrospacientes".
>
> ¿\[S\] Sí \[T\] Sí a todo \[N\] No \[A\] No a todo \[?\] Ayuda (el valor predeterminado es "S"):

> [!TIP]
> Si quiere que los cambios se realicen sin confirmación, en el paso 3, use este cmdlet: Set-DlpEdmSchema -FileData $edmSchemaXml

> [!NOTE]
> La actualización de EDMSchema con adiciones puede tardar de 10 a 60 minutos. La actualización debe completarse antes de ejecutar los pasos que usan las adiciones.

## <a name="removing-the-schema-for-edm-based-classification"></a>Eliminación del esquema de la clasificación basada en EDM

(Según sea necesario) Si quiere quitar el esquema que está usando de la clasificación basada en EDM, siga estos pasos:

1. [Conéctese a PowerShell del Centro de seguridad y cumplimiento de Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

2. Ejecute los siguientes cmdlets de PowerShell y sustituya el nombre del almacén de datos "registrospacientes" por el que quiere quitar:

```powershell
Remove-DlpEdmSchema -Identity patientrecords
```

Se le pedirá que confirme lo siguiente:

> Confirmar
>
> ¿Está seguro de que desea realizar esta acción?
>
> Se quitará el esquema EDM para el almacén de datos "registrospacientes".
>
> ¿\[S\] Sí \[T\] Sí a todo \[N\] No \[A\] No a todo \[?\] Ayuda (el valor predeterminado es "S"):

> [!TIP]
>  Si quiere que los cambios se realicen sin confirmación, en el paso 2, use este cmdlet: Remove-DlpEdmSchema -Identity registrospacientes -Confirm:$false

### <a name="set-up-a-rule-package"></a>Configuración de un paquete de reglas

1. Cree un paquete de reglas en formato .xml (con codificación Unicode), similar al ejemplo siguiente: (Puede copiar, modificar y usar nuestro ejemplo).

Cuando configure el paquete de reglas, asegúrese de hacer referencia correctamente al archivo .csv y al archivo edm.xml. Puede copiar, modificar y usar nuestro ejemplo. En este XML de ejemplo, debe personalizar los siguientes campos para crear el tipo confidencial de EDM:

- 
  **RulePack id y ExactMatch id**: use  [New-GUID](https://docs.microsoft.com/es-ES/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6)  para generar un GUID.

- **Datastore**: este campo especifica el almacén de datos de búsqueda de EDM que se va a usar. Debe proporcionar un nombre de origen de datos de un esquema EDM configurado.

- **idMatch**: este campo señala al elemento principal para EDM.
  - Matches: especifica el campo que se usará en la búsqueda exacta. Se proporciona un nombre de campo que se puede buscar en el esquema EDM para DataStore.
  - Classification: este campo especifica la coincidencia de tipo confidencial que desencadena la búsqueda de EDM. Puede especificar el nombre o el GUID de una clasificación personalizada o integrada existente.

- **Match:** este campo señala a la evidencia adicional que se encuentra cerca de idMatch.
  - Matches: se proporciona un nombre de campo en el esquema EDM para DataStore.
- **Resource:** esta sección especifica el nombre y la descripción del tipo confidencial en varias configuraciones regionales.
  - idRef: ha proporcionado un GUID para ExactMatch id.
  - Asignación del nombre y edición de las descripciones del esquema: personalizar según sea necesario.

```xml
<RulePackage xmlns="http://schemas.microsoft.com/office/2018/edm">
  <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b11">
    <Version build="0" major="2" minor="0" revision="0" />
    <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
    <Details defaultLangCode="en-us">
      <LocalizedDetails langcode="en-us">
        <PublisherName>IP DLP</PublisherName>
        <Name>Health Care EDM Rulepack</Name>
        <Description>This rule package contains the EDM sensitive type for health care sensitive types.</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  <Rules>
    <ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
        <Any minMatches ="3" maxMatches ="100">
          <match matches="PatientID" />
          <match matches="MRN"/>
          <match matches="FirstName"/>
          <match matches="LastName"/>
          <match matches="Phone"/>
          <match matches="DOB"/>
        </Any>
      </Pattern>
    </ExactMatch>
    <LocalizedStrings>
      <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB371">
        <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
        <Description default="true" langcode="en-us">EDM Sensitive type for detecting Patient SSN.</Description>
      </Resource>
    </LocalizedStrings>
  </Rules>
</RulePackage>
```

1. Cargue el paquete de reglas ejecutando, uno a la vez, los siguientes cmdlets de PowerShell:

```powershell
$rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
```

Ya tiene configurada la clasificación basada en EDM. El siguiente paso es indexar los datos confidenciales y luego cargar los datos indizados.

Recuerde del procedimiento anterior que nuestro esquema RegistrosPacientes define cinco campos para la búsqueda: *IdPaciente*, *NEM*, *NSS*, *Teléfono* y *FechaNacimiento*. Nuestro paquete de reglas de ejemplo incluye esos campos y hace referencia al archivo de esquema de la base de datos (edm.xml), con un elemento *ExactMatch* por campo de búsqueda. Considere el siguiente elemento ExactMatch:

```xml
<ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
        <Any minMatches ="3" maxMatches ="100">
          <match matches="PatientID" />
          <match matches="MRN"/>
          <match matches="FirstName"/>
          <match matches="LastName"/>
          <match matches="Phone"/>
          <match matches="DOB"/>
        </Any>
      </Pattern>
    </ExactMatch>
```

En este ejemplo, tenga en cuenta lo siguiente:

- El nombre de dataStore hace referencia al archivo .csv que hemos creado anteriormente: **dataStore = "RegistrosPacientes"**.

- El valor de idMatch hace referencia a un campo para la búsqueda que aparece en el archivo de esquema de la base de datos: **idMatch matches = "NSS"**.

- El valor classification hace referencia a un tipo de información confidencial existente o personalizada: **classification = "Número de seguridad social de Estados Unidos (NSS)"**. (En este caso, usamos el tipo de información confidencial existente del número de la seguridad social de Estados Unidos).

> [!NOTE]
> La actualización de EDMSchema con adiciones puede tardar de 10 a 60 minutos. La actualización debe completarse antes de ejecutar los pasos que usan las adiciones.

### <a name="part-2-index-and-upload-the-sensitive-data"></a>Parte 2: Indizar y cargar los datos confidenciales

Durante esta fase, configurará una cuenta de usuario y un grupo de seguridad personalizado y configurará la herramienta de agente de carga de EDM. Después, usará la herramienta para indexar los datos confidenciales y luego cargar los datos indizados.

#### <a name="set-up-the-security-group-and-user-account"></a>Configuración de la cuenta de usuario y del grupo de seguridad personalizado

1. Como administrador global, vaya al centro de administración ([https://admin.microsoft.com](https://admin.microsoft.com/)) y [cree un grupo de seguridad](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) denominado EDM\_DataUploaders.

2. Agregue uno o más usuarios al grupo de seguridad *EDM\_DataUploaders* . (Estos usuarios administrarán la base de datos de información confidencial).

3. Asegúrese de que cada usuario que administra la información confidencial es un administrador local en el equipo que usa para el agente de carga de EDM.

#### <a name="set-up-the-edm-upload-agent"></a>Configuración del agente de carga de EDM

>[!NOTE]
> Antes de comenzar este procedimiento, asegúrese de que es miembro del grupo de seguridad *EDM\_DataUploaders* y un administrador local en el equipo.

1. Descargue e instale el [Agente de carga de EDM](https://go.microsoft.com/fwlink/?linkid=2088639). De forma predeterminada, la ubicación de la instalación debe ser C:\\Archivos de programa\\Microsoft\\EdmUploadAgent.

2. Para autorizar al agente de carga de EDM, abra el símbolo de Windows (como administrador) y ejecute el siguiente comando:

    `EdmUploadAgent.exe /Authorize`

3. Inicie con su cuenta profesional o educativa de Office 365.

El siguiente paso es usar el agente de carga de EDM para indexar los datos confidenciales y luego cargar los datos indizados.

#### <a name="index-and-upload-the-sensitive-data"></a>Indización y carga de datos confidenciales

Guarde el archivo de datos confidenciales (recuerde que nuestro ejemplo es *RegistrosPacientes.csv*) en la unidad local en el equipo. (Hemos guardado nuestro archivo *RegistrosPacientes.csv*  de ejemplo en C:\\Edm\\Data).

Para indizar y cargar los datos confidenciales, ejecute el siguiente comando en el símbolo de Windows:

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

Ejemplo: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\RegistrosPacientes.csv /HashLocation C:\\Edm\\Hash**

Para separar y ejecutar el índice de datos confidenciales en un entorno aislado, ejecute el índice y cargue los pasos por separado.

Para indizar los datos confidenciales, ejecute el siguiente comando en el símbolo de Windows:

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

Ejemplo: **EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\RegistrosPacientes.csv /HashLocation C:\\Edm\\Hash**

Para cargar los datos indizados, ejecute el siguiente comando en el símbolo de Windows:

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

Ejemplo: **EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\RegistrosPacientes.EdmHash**

Para comprobar que se han cargado los datos confidenciales, ejecute el siguiente comando en el símbolo de Windows:

`EdmUploadAgent.exe /GetDataStore`

Verá una lista de almacenes de datos y la última vez que se actualizaron, como se muestra a continuación:

Continúe con el proceso de configuración y programación para [actualizar la base de datos de información confidencial](#refreshing-your-sensitive-information-database).

En este momento, está listo para usar la clasificación basada en EDM con los servicios de nube de Microsoft. Por ejemplo, puede [configurar una directiva DLP con clasificación basada en EDM](#to-create-a-dlp-policy-with-edm).

#### <a name="refreshing-your-sensitive-information-database"></a>Actualizar la base de datos de información confidencial

Puede actualizar la base de datos de información confidencial de forma diaria o semanal, la herramienta de carga de EDM puede volver a indizar los datos confidenciales y cargar de nuevo los datos indizados.

1. Determine el proceso y la frecuencia (diaria o semanal) para actualizar la base de datos de información confidencial.

2. Vuelva a exportar los datos confidenciales a una aplicación, como Microsoft Excel, y guarde el archivo en formato .csv. Mantenga el mismo nombre de archivo y la ubicación que usó cuando siguió los pasos descritos en [Indización y carga de datos confidenciales](#index-and-upload-the-sensitive-data).

> [!NOTE]
> Si no hay ningún cambio en la estructura (nombres de campo) del archivo .csv, no necesita realizar cambios en el archivo de esquema de la base de datos al actualizar los datos. Pero si necesita realizar cambios, asegúrese de editar el esquema de la base de datos y su paquete de reglas consecuentemente.

3. Use el [Programador de tareas](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) para automatizar los pasos 2 y 3 en el procedimiento [Indización y carga de datos confidenciales](#index-and-upload-the-sensitive-data) . Puede programar tareas con varios métodos:

| **Método**             | **Qué hacer**                                                                                                                                                                                                                                                                                                                                                                                                                     |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Windows PowerShell     | Consulte la documentación [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) y [script de PowerShell de ejemplo](#example-powershell-script-for-task-scheduler) de este artículo |
| API del Programador de tareas     | Consulte la documentación del [Programador de tareas](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler)                                                                                                                                                                                                                                                                                 |
| Interfaz de usuario de Windows | En Windows, haga clic en **Inicio** y escriba programador de tareas. A continuación, en la lista de resultados, haga clic en **Programador de tareas** y **Ejecutar como administrador**.                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a>Script de PowerShell de ejemplo para el Programador de tareas

Esta sección incluye un script de PowerShell de ejemplo que puede usar para programar las tareas de indización de datos y carga de los datos indizados:

##### <a name="to-schedule-index-and-upload-in-a-combined-step"></a>Para programar el índice y la carga en un paso combinado

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ‘ /HashLocation’ + $hashLocation
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadDataArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

#### <a name="to-schedule-index-and-upload-as-separate-steps"></a>Para programar el índice y la carga en pasos separados

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation
$uploadHashArgs = '/UploadHash /DataStoreName ' + $dataStoreName + ' /HashFile ' + $hashFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $createHashArgs -WorkingDirectory $edminstallpath
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadHashArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a>Parte 3: Usar clasificación basada en EDM con los servicios de nube de Microsoft

Las directivas de Office 365 DLP para Exchange Online (correo electrónico), OneDrive para la Empresa (archivos), Microsoft Teams (conversaciones) y Microsoft Cloud App Security DLP serán compatibles con tipos de información confidencial de EDM.

Los tipos de información confidencial de EDM para las siguientes situaciones están actualmente en desarrollo, pero todavía no están disponibles:

- Office 365 DLP para SharePoint (archivos)
- Clasificación automática de las etiquetas de sensibilidad y las etiquetas de retención

#### <a name="to-create-a-dlp-policy-with-edm"></a>Para crear una directiva DLP con EDM

1. Vaya al Centro de seguridad y cumplimiento ([https://protection.office.com](https://protection.office.com/)).

2. Haga clic en **Prevención de pérdida de datos** \> **Directiva**.

3. Elija **Crear una directiva** \> **Personalizada** \> **Siguiente**.

4. En la pestaña **Nombre de la directiva** , especifique un nombre y una descripción y elija **Siguiente**.

5. En la pestaña **Elegir ubicaciones** , haga clic en **Permitir elegir ubicaciones concretas** y luego en **Siguiente**.

6. En la columna **Estado** , seleccione **correo electrónico de Exchange, cuentas de OneDrive, conversación de equipos y mensaje de canal** , y después elija **Siguiente**. (Nota: en este momento, EDM no es compatible con los sitios de SharePoint y la Directiva DLP no detectará archivos en SharePoint para EDM)

7. En la pestaña **Configuración de directiva** , elija **Usar la configuración avanzada** y luego elija **Siguiente**.

8. Elija **+ Nueva regla**.

9. En la sección **Nombre** , especifique un nombre y una descripción para la regla.

10. En la sección **Condiciones** en la lista **+ Agregar una condición,** elija **El contenido incluye tipo confidencial**.<br/>![El contenido incluye tipos de información confidencial](media/edm-dlp-newrule-conditions.png)<br/>

11. Busque el tipo de información confidencial que creó al configurar el paquete de reglas y elija **+ Agregar**.  
    Luego elija **Listo**.

12. Termine de seleccionar las opciones para la regla, como **Notificaciones de usuario**, **Invalidaciones de usuario**, **Informes de incidentes**, etc. y luego elija **Guardar**.

13. En la pestaña **Configuración de directiva,** revise las reglas y elija **Siguiente**.

14. Especifique si quiere activar la directiva inmediatamente, probarla o dejarla desactivada. Luego elija **Siguiente**.

15. En la pestaña **Revisar la configuración,** , revise la directiva. Realice los cambios necesarios. Cuando haya terminado, seleccione **Crear**.

> [!NOTE]
> Espere aproximadamente una hora para que la nueva directiva DLP pase por el centro de datos.

## <a name="related-articles"></a>Artículos relacionados


  [Tipos de información confidencial integrados y lo que buscan](https://review.docs.microsoft.com/es-ES/office365/securitycompliance/what-the-sensitive-information-types-look-for)


  [Tipos de información confidencial personalizados](https://review.docs.microsoft.com/es-ES/office365/securitycompliance/custom-sensitive-info-types)


  [Información general de directivas DLP](https://review.docs.microsoft.com/es-ES/office365/securitycompliance/data-loss-prevention-policies)

[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)


  [New-DlpEdmSchema](https://docs.microsoft.com/es-ES/powershell/module/exchange/policy-and-compliance-dlp/new-dlpedmschema?view=exchange-ps)

## <a name="feedback"></a>Comentarios
Los comentarios de GitHub están habilitados, pero agregar problemas solo está disponible en el sitio público.

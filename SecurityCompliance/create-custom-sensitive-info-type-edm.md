---
title: Crear un tipo de información confidencial personalizado con coincidencia exacta de datos
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 05/15/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Crear un tipo de información confidencial personalizado con clasificación basada en coincidencia exacta de datos
ms.openlocfilehash: 3b15bf0197918d6bbc3897f9fa578c40b70d3f4e
ms.sourcegitcommit: 4eb4ca899adcf4d86501530f875eb49af8cdaeb7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2019
ms.locfileid: "34083193"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification-preview"></a><span data-ttu-id="dcb0d-103">Crear un tipo de información confidencial personalizado con coincidencia exacta de datos (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="dcb0d-103">See Create a custom sensitive information type with Exact Data Match based classification (Preview).</span></span>

## <a name="overview"></a><span data-ttu-id="dcb0d-104">Información general</span><span class="sxs-lookup"><span data-stu-id="dcb0d-104">Overview</span></span>

<span data-ttu-id="dcb0d-105">Los [tipos de información confidencial](custom-sensitive-info-types.md) se usan para ayudar a evitar el uso compartido accidental o inadecuado de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-105">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help prevent inadvertent or inappropriate sharing of sensitive information.</span></span> <span data-ttu-id="dcb0d-106">Como administrador, puede usar el [Centro de seguridad y cumplimiento](create-a-custom-sensitive-information-type.md) o [PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) para definir un tipo de información confidencial basado en patrones, evidencia (palabras clave como \* empleado\*, *insignia*, *ID*, etc.), proximidad de caracteres (la similitud de la evidencia y los caracteres en un patrón determinado) y niveles de confianza.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-106">As an administrator, you can use the [Security & Compliance Center](create-a-custom-sensitive-information-type.md) or [PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) to define a custom sensitive information type based on patterns, evidence (keywords such as *employee*, *badge*, *ID*, and so on), character proximity (how close evidence is to characters in a particular pattern), and confidence levels.</span></span> <span data-ttu-id="dcb0d-107">Estos tipos de información confidencial satisfacen las necesidades de negocio para muchas organizaciones.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-107">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="dcb0d-108">Pero, ¿qué pasa si quiere un tipo de información confidencial que use valores de datos exactos, en lugar de patrones y proximidad?</span><span class="sxs-lookup"><span data-stu-id="dcb0d-108">But what if you wanted a custom sensitive information type that uses exact data values, instead of patterns and proximity?</span></span> <span data-ttu-id="dcb0d-109">Con la clasificación basada en coincidencia exacta de datos (EDM), puede crear un tipo de información confidencial personalizado que está diseñado para:</span><span class="sxs-lookup"><span data-stu-id="dcb0d-109">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>
- <span data-ttu-id="dcb0d-110">ser dinámico y actualizable;</span><span class="sxs-lookup"><span data-stu-id="dcb0d-110">be dynamic and refreshable;</span></span>
- <span data-ttu-id="dcb0d-111">ser más escalable;</span><span class="sxs-lookup"><span data-stu-id="dcb0d-111">be more scalable;</span></span>
- <span data-ttu-id="dcb0d-112">generar menos falsos positivos;</span><span class="sxs-lookup"><span data-stu-id="dcb0d-112">result in fewer false-positives;</span></span>
- <span data-ttu-id="dcb0d-113">funcionar con datos confidenciales estructurados;</span><span class="sxs-lookup"><span data-stu-id="dcb0d-113">work with structured sensitive data;</span></span>
- <span data-ttu-id="dcb0d-114">trabajar con información confidencial de forma más segura; y</span><span class="sxs-lookup"><span data-stu-id="dcb0d-114">handle sensitive information more securely; and</span></span>
- <span data-ttu-id="dcb0d-115">usarse con varios servicios de nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-115">be used with several Microsoft cloud services.</span></span>

![Clasificación basada en EDM](media/EDMClassification.png)

<span data-ttu-id="dcb0d-117">La clasificación basada en EDM le permite crear tipos de información confidencial personalizados que hacen referencia a valores exactos en una base de datos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-117">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="dcb0d-118">La base de datos puede ser actualizada diaria o semanalmente, y puede contener hasta 10 millones de filas de datos.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-118">The database can be refreshed daily or weekly, and it can contain up to 10 million rows of data.</span></span> <span data-ttu-id="dcb0d-119">Así que mientras los empleados, clientes o pacientes van y vienen y cambian los registros, los tipos de información confidencial se mantienen al día y aplicables.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-119">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="dcb0d-120">Y puede usar la clasificación basada en EDM con directivas, como [directivas de prevención de pérdida de datos](data-loss-prevention-policies.md) (DLP) o [directivas de archivo de Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="dcb0d-120">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="dcb0d-121">Permisos y licencias necesarios</span><span class="sxs-lookup"><span data-stu-id="dcb0d-121">Required licenses and permissions</span></span>

- <span data-ttu-id="dcb0d-122">Debe ser un administrador global, administrador de cumplimiento o administrador de Exchange Online para realizar las tareas descritas en este artículo.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-122">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="dcb0d-123">Para obtener más información acerca de los permisos de DLP, consulte [Permisos](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="dcb0d-123">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

- <span data-ttu-id="dcb0d-124">Cuando esté disponible de forma general, la clasificación basada en EDM se incluirá en las siguientes suscripciones:</span><span class="sxs-lookup"><span data-stu-id="dcb0d-124">When generally available, EDM-based classification will be included in the following subscriptions:</span></span>
    - <span data-ttu-id="dcb0d-125">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="dcb0d-125">Office 365 Enterprise E5</span></span>
    - <span data-ttu-id="dcb0d-126">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="dcb0d-126">Microsoft 365 E5</span></span>
    - <span data-ttu-id="dcb0d-127">Cumplimiento y protección de la información de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dcb0d-127">Microsoft 365 Information Protection and Compliance</span></span>
    - <span data-ttu-id="dcb0d-128">Cumplimiento avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="dcb0d-128">Office 365 Advanced Compliance</span></span>

> [!NOTE]
> <span data-ttu-id="dcb0d-129">**Clasificación basada en EDM está actualmente en versión preliminar** para [DLP en Office 365](data-loss-prevention-policies.md) (con Exchange Online y Microsoft Teams) y [Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="dcb0d-129">**EDM-based classification is currently in preview** for [DLP in Office 365](data-loss-prevention-policies.md) (with Exchange Online and Microsoft Teams) and [Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span> <span data-ttu-id="dcb0d-130">Si su organización tiene [funciones DLP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc#data-loss-prevention-dlp), puede probar la clasificación basada en EDM.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-130">If your organization has [DLP capabilities](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc#data-loss-prevention-dlp), you can try EDM-based classification.</span></span> <span data-ttu-id="dcb0d-131">Si no está participando aún en la versión preliminar, [póngase en contacto con Microsoft](https://resources.office.com/us-landing-spe-contactus.html?LCID=EN-US) para empezar.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-131">If you are not already participating in the preview, [contact Microsoft](https://resources.office.com/us-landing-spe-contactus.html?LCID=EN-US) to get started.</span></span> 

## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="dcb0d-132">El flujo de trabajo de un vistazo</span><span class="sxs-lookup"><span data-stu-id="dcb0d-132">The work flow at a glance</span></span>

|<span data-ttu-id="dcb0d-133">Fase</span><span class="sxs-lookup"><span data-stu-id="dcb0d-133">Phase</span></span>  |<span data-ttu-id="dcb0d-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dcb0d-134">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="dcb0d-135">Parte 1: Configurar la clasificación basada en EDM</span><span class="sxs-lookup"><span data-stu-id="dcb0d-135">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="dcb0d-136">(Según sea necesario)</span><span class="sxs-lookup"><span data-stu-id="dcb0d-136">(As needed)</span></span><br/><span data-ttu-id="dcb0d-137">- [Editar el esquema de la base de datos](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="dcb0d-137">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="dcb0d-138">- [Quitar el esquema](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="dcb0d-138">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="dcb0d-139">- Acceso de lectura a los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="dcb0d-139">- Read access to the sensitive data</span></span><br/><span data-ttu-id="dcb0d-140">- Esquema base de datos en formato .xml (ejemplo proporcionado)</span><span class="sxs-lookup"><span data-stu-id="dcb0d-140">- Database schema in .xml format (example provided)</span></span><br/><span data-ttu-id="dcb0d-141">- Paquete de reglas en formato .xml (ejemplo proporcionado)</span><span class="sxs-lookup"><span data-stu-id="dcb0d-141">- Rule package in .xml format (example provided)</span></span><br/><span data-ttu-id="dcb0d-142">- Permisos de administrador para el Centro de seguridad y cumplimiento (con PowerShell)</span><span class="sxs-lookup"><span data-stu-id="dcb0d-142">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="dcb0d-143">Parte 2: Indizar y cargar los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="dcb0d-143">Part 2: Index and upload the sensitive data</span></span>](#part-2-index-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="dcb0d-144">(Según sea necesario)</span><span class="sxs-lookup"><span data-stu-id="dcb0d-144">(As needed)</span></span><br/>[<span data-ttu-id="dcb0d-145">Actualizar los datos</span><span class="sxs-lookup"><span data-stu-id="dcb0d-145">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="dcb0d-146">- Cuenta de usuario y de grupo de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="dcb0d-146">- Custom security group and user account</span></span><br/><span data-ttu-id="dcb0d-147">- Acceso de administrador local en el equipo con el agente de carga EDM</span><span class="sxs-lookup"><span data-stu-id="dcb0d-147">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="dcb0d-148">- Acceso de lectura a los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="dcb0d-148">- Read access to the sensitive data</span></span><br/><span data-ttu-id="dcb0d-149">- Procesar y programar la actualización de los datos</span><span class="sxs-lookup"><span data-stu-id="dcb0d-149">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="dcb0d-150">Parte 3: Usar clasificación basada en EDM con los servicios de nube de Microsoft</span><span class="sxs-lookup"><span data-stu-id="dcb0d-150">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="dcb0d-151">- Suscripción de Office 365 con DLP</span><span class="sxs-lookup"><span data-stu-id="dcb0d-151">- Office 365 subscription with DLP</span></span><br/><span data-ttu-id="dcb0d-152">- Característica de clasificación basada en EDM habilitada (en versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="dcb0d-152">- EDM-based classification feature enabled (in preview)</span></span> |

## <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="dcb0d-153">Parte 1: Configurar la clasificación basada en EDM</span><span class="sxs-lookup"><span data-stu-id="dcb0d-153">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="dcb0d-154">La configuración de la clasificación basada en EDM implica guardar los datos confidenciales en formato .csv, definir un esquema para la base de datos de información confidencial, crear un paquete de reglas y cargar el paquete de reglas y el esquema.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-154">Setting up and configuring EDM-based classification involves saving sensitive data in .csv format, defining a schema for your database of sensitive information, creating a rule package, and then uploading the schema and rule package.</span></span>

### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="dcb0d-155">Definir el esquema de la base de datos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="dcb0d-155">Define the schema for your database of sensitive information</span></span>

1. <span data-ttu-id="dcb0d-156">Identifique la información confidencial que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-156">Identify the KPIs that you want to use.</span></span> <span data-ttu-id="dcb0d-157">Exporte los datos a una aplicación, como Microsoft Excel, y guarde el archivo en formato .csv.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-157">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="dcb0d-158">El archivo de datos puede incluir:</span><span class="sxs-lookup"><span data-stu-id="dcb0d-158">The data file can include:</span></span>

    - <span data-ttu-id="dcb0d-159">Hasta 10 millones de filas de datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="dcb0d-159">Up to 10 million rows of sensitive data</span></span>
    - <span data-ttu-id="dcb0d-160">Hasta 32 columnas (campos) por origen de datos</span><span class="sxs-lookup"><span data-stu-id="dcb0d-160">Up to 32 columns (fields) per data source</span></span>

2. <span data-ttu-id="dcb0d-161">Estructure los datos confidenciales en el archivo .csv de forma que la primera fila incluya los nombres de los campos que se usan para la clasificación basada en EDM.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-161">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="dcb0d-162">En el archivo .csv, puede que tenga nombres de campo, como "NSS", "FechaNacimiento", "Nombre", "Apellido", etc.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-162">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname", and so on.</span></span> <span data-ttu-id="dcb0d-163">Por ejemplo, nuestro archivo .csv se llama *RegistrosPacientes.csv* e incluye las columnas *IdPaciente*, *NEM*, *apellidos*, *Nombre*, *NSS*, etc.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-163">As an example, our .csv file is called *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *lastname*, *FirstName*, *SSN* and more.</span></span>

3. <span data-ttu-id="dcb0d-164">Defina el esquema de la base de datos de información confidencial en formato .xml (similar al ejemplo siguiente).</span><span class="sxs-lookup"><span data-stu-id="dcb0d-164">Define the schema for the database of sensitive information in .xml format (similar to our example below).</span></span> <span data-ttu-id="dcb0d-165">Nombre este archivo de esquema `edm.xml` y configúrelo para que por cada columna de la base de datos haya una línea que use la sintaxis `<Field name="" unique="" searchable=""/>`.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-165">Name this schema file `edm.xml`, and configure it such that for each column in the database, there is a line that uses the syntax `<Field name="" unique="" searchable=""/>`.</span></span> 

    - <span data-ttu-id="dcb0d-166">Use nombres de columna para los valores *Nombre de campo*.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-166">Use column names for *Field name* values.</span></span>
    - <span data-ttu-id="dcb0d-167">Use *unique="true"* para los campos que contienen valores únicos (números de Seguridad Social, números de identificación, etc.); en caso contrario, utilice *unique="false"*.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-167">Use *unique="true"* for the fields that contain unique values (Social Security numbers, identification numbers, etc.); otherwise, use *unique="false"*.</span></span>
    - <span data-ttu-id="dcb0d-168">Use *searchable="true"* para los campos que quiere que se puedan buscar.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-168">Use *searchable="true"* for the fields that you want to be searchable.</span></span> <span data-ttu-id="dcb0d-169">No especifique más de cinco campos que puedan buscarse por base de datos.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-169">Do not specify more than five fields per database to be searchable.</span></span> <span data-ttu-id="dcb0d-170">El resto deben tener *searchable="false"*.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-170">All the rest should have *searchable="false"*.</span></span>  

    <span data-ttu-id="dcb0d-171">Por ejemplo, el siguiente archivo .xml define el esquema para una base de datos de registros de pacientes, con cinco campos especificados para la búsqueda: *IdPaciente*, *NEM*, *NSS*, \* Teléfono\* y *FechaNacimiento*.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-171">As an example, the following .xml file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> 
    
    <span data-ttu-id="dcb0d-172">(Puede copiar, modificar y usar nuestro ejemplo).</span><span class="sxs-lookup"><span data-stu-id="dcb0d-172">(You can copy, modify, and use our example.)</span></span>
    
    <span data-ttu-id="dcb0d-173">\`\`\`<?xml version="1.0" encoding="utf-8"?> <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm"></span><span class="sxs-lookup"><span data-stu-id="dcb0d-173"></span></span>
        <span data-ttu-id="dcb0d-174"><DataStore name="PatientRecords" description="Esquema de registros de pacientes</span><span class="sxs-lookup"><span data-stu-id="dcb0d-174"><DataStore name="PatientRecords" description="Schema for patient records</span></span>" version="1">
            <span data-ttu-id="dcb0d-175"><Field name="PatientID" unique="false" searchable="true" /> <Field name="MRN" unique="false" searchable="true" /></span><span class="sxs-lookup"><span data-stu-id="dcb0d-175"></span></span>
            <Field name="FirstName" unique="false" searchable="false" />
            <Field name="LastName" unique="false" searchable="false" />
            <Field name="SSN" unique="false" searchable="true" />
            <Field name="Phone" unique="false" searchable="true" />
            <Field name="DOB" unique="false" searchable="true" />
            <Field name="Gender" unique="false" searchable="false" />
            <Field name="Address" unique="false" searchable="false" />
        </DataStore>
    </EdmSchema>
    ```

4. [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

5. To upload the database schema, run the following cmdlets, one at a time:

    `$edmSchemaXml=Get-Content .\edm.xml -Encoding Byte -ReadCount 0`

    `New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

    You will be prompted to confirm, as follows:

       Confirm
       Are you sure you want to perform this action?
       New EDM Schema for the data store 'patientrecords' will be imported.
       [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):

    > [!TIP]
    > If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: `New-DlpEdmSchema -FileData $edmSchemaXml`
    
Now that the schema for your database of sensitive information is defined, the next step is to set up a rule package. Proceed to the section [Set up a rule package](#set-up-a-rule-package).

#### Editing the schema for EDM-based classification 

(As needed) If you want to make changes to your edm.xml file, such as changing which fields are used for EDM-based classification, follow these steps:

1. Edit your edm.mxl file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).

2. [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

3. To update your database schema, run the following cmdlets, one at a time:

    `$edmSchemaXml=Get-Content .\edm.xml -Encoding Byte -ReadCount 0`

    `Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

    You will be prompted to confirm, as follows:

       Confirm
       Are you sure you want to perform this action?
       EDM Schema for the data store 'patientrecords' will be updated.
       [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):

    > [!TIP]
    > If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: `Set-DlpEdmSchema -FileData $edmSchemaXml`

#### Removing the schema for EDM-based classification

(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:

1. [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

2. Run the following PowerShell cmdlet, substituting the data store name of "patientrecords" with the one you want to remove:

    `Remove-DlpEdmSchema -Identity patientrecords`

     You will be prompted to confirm, as follows:
    
       Confirm
       Are you sure you want to perform this action?
       EDM Schema for the data store 'patientrecords' will be removed.
       [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):
    
    > [!TIP]
    > If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: `Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false`

### Set up a rule package

1. Create a rule package in .xml format (with Unicode encoding), similar to the following example. (You can copy, modify, and use our example.) 

   Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*. Our example rule package includes those fields and references the database schema file (edm.xml), with one *ExactMatch* items per searchable field. Consider the following ExactMatch item:

   ```
    <span data-ttu-id="dcb0d-176"><ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" > <Pattern confidenceLevel="65"> <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" /> </Pattern> </ExactMatch></span><span class="sxs-lookup"><span data-stu-id="dcb0d-176"></span></span>
   ```

    In this example, note the following:

    - The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.
    - The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.
    - The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**. (In this case, we use the existing sensitive information type of U.S. Social Security Number.)

    When you set up your rule package, make sure to correctly reference your .csv file and edm.xml file. (You can copy, modify, and use our example.) 

    ```<?xml version="1.0" encoding="utf-8"?>
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
    
2. <span data-ttu-id="dcb0d-177">Cargue el paquete de reglas ejecutando los siguientes cmdlets de PowerShell, uno a uno:</span><span class="sxs-lookup"><span data-stu-id="dcb0d-177">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

    `$rulepack=Get-Content .\rulepack.xml -Encoding Byte -ReadCount 0`

    `New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack`

<span data-ttu-id="dcb0d-178">Ya tiene configurada la clasificación basada en EDM.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-178">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="dcb0d-179">El siguiente paso es indexar los datos confidenciales y luego cargar los datos indizados.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-179">The next step is to index the sensitive data, and then upload the indexed data.</span></span> 

## <a name="part-2-index-and-upload-the-sensitive-data"></a><span data-ttu-id="dcb0d-180">Parte 2: Indizar y cargar los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="dcb0d-180">Part 2: Index and upload the sensitive data</span></span>

<span data-ttu-id="dcb0d-181">Durante esta fase, configurará una cuenta de usuario y un grupo de seguridad personalizado y configurará la herramienta de agente de carga de EDM.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-181">During this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="dcb0d-182">Después, usará la herramienta para indexar los datos confidenciales y luego cargar los datos indizados.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-182">Then, you use the tool to index the sensitive data, and upload the indexed data.</span></span>

### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="dcb0d-183">Configuración de la cuenta de usuario y del grupo de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="dcb0d-183">Set up the security group and user account</span></span>

1. <span data-ttu-id="dcb0d-184">Como administrador global, vaya al centro de administración ([https://admin.microsoft.com](https://admin.microsoft.com)) y [cree un grupo de seguridad](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) denominado `EDM_DataUploaders`.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-184">As a global administrator, go to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called `EDM_DataUploaders`.</span></span> 

2. <span data-ttu-id="dcb0d-185">Agregue uno o más usuarios al grupo de seguridad *EDM_DataUploaders*.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-185">Add one or more users to the *EDM_DataUploaders* security group.</span></span> <span data-ttu-id="dcb0d-186">(Estos usuarios administrarán la base de datos de información confidencial).</span><span class="sxs-lookup"><span data-stu-id="dcb0d-186">(These users will manage the database of sensitive information.)</span></span>

3. <span data-ttu-id="dcb0d-187">Asegúrese de que cada usuario que administra la información confidencial es un administrador local en el equipo que usa para el agente de carga de EDM.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-187">Make sure each user who is managing the sensitive data is a local admin on the machine used for the EDM Upload Agent.</span></span>

### <a name="set-up-the-edm-upload-agent"></a><span data-ttu-id="dcb0d-188">Configurar el agente de carga de EDM</span><span class="sxs-lookup"><span data-stu-id="dcb0d-188">Set up the EDM Upload Agent</span></span>

> [!NOTE]
> <span data-ttu-id="dcb0d-189">Antes de comenzar este procedimiento, asegúrese de que es miembro del grupo de seguridad *EDM_DataUploaders* y un administrador local en el equipo.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-189">Before you begin this procedure, make sure that you are a member of the *EDM_DataUploaders* security group and a local admin on your machine.</span></span>

1. <span data-ttu-id="dcb0d-190">Descargue e instale el agente de carga de EDM en [ https://go.microsoft.com/fwlink/?linkid=2088639 ](https://go.microsoft.com/fwlink/?linkid=2088639).</span><span class="sxs-lookup"><span data-stu-id="dcb0d-190">Download and install the EDM Upload Agent at [https://go.microsoft.com/fwlink/?linkid=2088639](https://go.microsoft.com/fwlink/?linkid=2088639).</span></span> <span data-ttu-id="dcb0d-191">De forma predeterminada, la ubicación de instalación debería ser `C:\Program Files\Microsoft\EdmUploadAgent`.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-191">By default, the installation location should be `C:\Program Files\Microsoft\EdmUploadAgent`.</span></span> 

2. <span data-ttu-id="dcb0d-192">Para autorizar al agente de carga de EDM, abra el símbolo de Windows (como administrador) y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="dcb0d-192">To authorize the EDM Upload Agent, open Windows Command Prompt (as an administrator), and then run the following command:</span></span>

    `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="dcb0d-193">Inicie con su cuenta profesional o educativa de Office 365.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-193">Sign in to Office 365 for business with your work or school account.</span></span>

<span data-ttu-id="dcb0d-194">El siguiente paso es usar el agente de carga de EDM para indexar los datos confidenciales y luego cargar los datos indizados.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-194">The next step is to use the EDM Upload Agent to index the sensitive data, and then upload the indexed data.</span></span>

### <a name="index-and-upload-the-sensitive-data"></a><span data-ttu-id="dcb0d-195">Indizar y cargar los datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="dcb0d-195">Index and upload the sensitive data</span></span>

1. <span data-ttu-id="dcb0d-196">Guarde el archivo de datos confidenciales (recuerde que nuestro ejemplo es *RegistroPacientes.csv*) en la unidad local en el equipo.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-196">Save the sensitive data file (recall our example is *PatientRecords.csv*) to the local drive on the machine.</span></span> <span data-ttu-id="dcb0d-197">(Guardamos nuestro archivo de ejemplo *RegistroPacientes.csv* en `C:\Edm\Data`.)</span><span class="sxs-lookup"><span data-stu-id="dcb0d-197">(We saved our example *PatientRecords.csv* file to `C:\Edm\Data`.)</span></span>

2. <span data-ttu-id="dcb0d-198">Para indizar los datos confidenciales, ejecute el siguiente comando en el símbolo de Windows:</span><span class="sxs-lookup"><span data-stu-id="dcb0d-198">To index the sensitive data, run the following command in Windows Command Prompt:</span></span>

    `EdmUploadAgent.exe /CreateHash /DataStoreName <DataStoreName> /DataFile <DataFilePath> /HashLocation <HashedFileLocation>`

    <span data-ttu-id="dcb0d-199">Ejemplo: **EdmUploadAgent.exe /CreateHash /DataStoreName PatientRecords /DataFile C:\Edm\Data\RegistroPacientes.csv HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="dcb0d-199">Example: **EdmUploadAgent.exe /CreateHash /DataStoreName PatientRecords /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span> 

3. <span data-ttu-id="dcb0d-200">Para cargar los datos indizados, ejecute el siguiente comando en el símbolo de Windows:</span><span class="sxs-lookup"><span data-stu-id="dcb0d-200">To upload the indexed data, run the following command in Windows Command Prompt:</span></span>

    `EdmUploadAgent.exe /UploadHash /DataStoreName <DataStoreName> /HashFile <HashedSourceFilePath>`

    <span data-ttu-id="dcb0d-201">Example: **EdmUploadAgent.exe /UploadHash /DataStoreName RegistroPacientes /HashFile C:\Edm\Hash\RegistroPacientes.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="dcb0d-201">Example: **EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\Edm\Hash\PatientRecords.EdmHash**</span></span> 

4. <span data-ttu-id="dcb0d-202">Para comprobar que se han cargado los datos confidenciales, ejecute el siguiente comando en el símbolo de Windows:</span><span class="sxs-lookup"><span data-stu-id="dcb0d-202">To verify your sensitive data has been uploaded, run the following command in Windows Command Prompt:</span></span>

    `EdmUploadAgent.exe /GetDataStore`

    <span data-ttu-id="dcb0d-203">Verá una lista de almacenes de datos y la última vez que se actualizaron, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="dcb0d-203">You'll see a list of data stores and when they were last updated, similar to the following:</span></span> <br/>![Ejemplo de cmdlet GetDataStore y resultados](media/EDM-GetDataStore-example.png)

5. <span data-ttu-id="dcb0d-205">Continúe con el proceso de configuración y programación para [actualizar la base de datos de información confidencial](#refreshing-your-sensitive-information-database).</span><span class="sxs-lookup"><span data-stu-id="dcb0d-205">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="dcb0d-206">En este momento, está listo para usar la clasificación basada en EDM con los servicios de nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-206">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="dcb0d-207">Por ejemplo, puede [configurar una directiva DLP con clasificación basada en EDM](#to-create-a-dlp-policy-with-edm).</span><span class="sxs-lookup"><span data-stu-id="dcb0d-207">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span> 

### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="dcb0d-208">Actualizar la base de datos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="dcb0d-208">Refreshing your sensitive information database</span></span>

<span data-ttu-id="dcb0d-209">Puede actualizar la base de datos de información confidencial de forma diaria o semanal, la herramienta de carga de EDM puede volver a indizar los datos confidenciales y cargar de nuevo los datos indizados.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-209">You can refresh your sensitive information database daily or weekly, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span> 

1. <span data-ttu-id="dcb0d-210">Determine el proceso y la frecuencia (diaria o semanal) para actualizar la base de datos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-210">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="dcb0d-211">Vuelva a exportar los datos confidenciales a una aplicación, como Microsoft Excel, y guarde el archivo en formato .csv.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-211">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="dcb0d-212">Mantenga el mismo nombre de archivo y la ubicación que usó cuando siguió los pasos descritos en [Indizar y cargar los datos confidenciales](#index-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="dcb0d-212">Keep the same file name and location you used when you followed the steps described in [Index and upload the sensitive data](#index-and-upload-the-sensitive-data).</span></span>

    > [!NOTE]
    > <span data-ttu-id="dcb0d-213">Si no hay ningún cambio en la estructura (nombres de campo) del archivo .csv, no necesita realizar cambios en el archivo de esquema de la base de datos al actualizar los datos.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-213">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="dcb0d-214">Pero si necesita realizar cambios, asegúrese de editar el [esquema de la base de datos](#editing-the-schema-for-edm-based-classification) y su [paquete de reglas](#set-up-a-rule-package) consecuentemente.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-214">But if you must make changes, make sure to edit the [database schema](#editing-the-schema-for-edm-based-classification) and your [rule package](#set-up-a-rule-package) accordingly.</span></span>        

3. <span data-ttu-id="dcb0d-215">Use el [Programador de tareas](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) para automatizar los pasos 2 y 3 en el procedimiento [Indizar y cargar los datos confidenciales](#index-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="dcb0d-215">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Index and upload the sensitive data](#index-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="dcb0d-216">Puede programar tareas con varios métodos:</span><span class="sxs-lookup"><span data-stu-id="dcb0d-216">You can schedule tasks using several methods:</span></span>
    
    |<span data-ttu-id="dcb0d-217">Método</span><span class="sxs-lookup"><span data-stu-id="dcb0d-217">Method</span></span>  |<span data-ttu-id="dcb0d-218">Qué hacer</span><span class="sxs-lookup"><span data-stu-id="dcb0d-218">What to do</span></span>  |
    |---------|---------|
    |<span data-ttu-id="dcb0d-219">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dcb0d-219">Windows PowerShell</span></span>     |<span data-ttu-id="dcb0d-220">Consulte la documentación [TareasProgramadas](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) y [script de PowerShell de ejemplo](#example-powershell-script-for-task-scheduler) de este artículo</span><span class="sxs-lookup"><span data-stu-id="dcb0d-220">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span>|
    |<span data-ttu-id="dcb0d-221">API del Programador de tareas</span><span class="sxs-lookup"><span data-stu-id="dcb0d-221">Task Scheduler API</span></span> |<span data-ttu-id="dcb0d-222">Consulte la documentación del [Programador de tareas](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler)</span><span class="sxs-lookup"><span data-stu-id="dcb0d-222">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span> |
    |<span data-ttu-id="dcb0d-223">Interfaz de usuario de Windows</span><span class="sxs-lookup"><span data-stu-id="dcb0d-223">Windows user interface</span></span>     |<span data-ttu-id="dcb0d-224">En Windows, haga clic en **Inicio** y escriba `Task Scheduler`.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-224">In Windows, click **Start**, and type `Task Scheduler`.</span></span> <span data-ttu-id="dcb0d-225">A continuación, en la lista de resultados, haga clic en **Programador de tareas** y **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-225">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>          |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="dcb0d-226">Script de PowerShell de ejemplo para el Programador de tareas</span><span class="sxs-lookup"><span data-stu-id="dcb0d-226">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="dcb0d-227">Esta sección incluye un script de PowerShell de ejemplo que puede usar para programar las tareas de indización de datos y carga de los datos indizados:</span><span class="sxs-lookup"><span data-stu-id="dcb0d-227">This section includes an example PowerShell script you can use to schedule your tasks for indexing data and uploading the indexed data:</span></span>

```powershell
param([string]$dataStoreName,[string]$fileLocation)
# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\$env:USERNAME"
$edminstallpath = 'C:\Program Files\Microsoft\EdmUploadAgent\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\$dataStoreName$csvext"
$hashFile = "$fileLocation\$dataStoreName$edmext"
# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation
$uploadHashArgs = '/UploadHash /DataStoreName ' + $dataStoreName + ' /HashFile ' + $hashFile
# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $createHashArgs -WorkingDirectory $edminstallpath
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadHashArgs -WorkingDirectory $edminstallpath
# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($creds.Password))
# Register the scheduled task
$taskName = 'EDMUpload_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```
## <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="dcb0d-228">Parte 3: Usar clasificación basada en EDM con los servicios de nube de Microsoft</span><span class="sxs-lookup"><span data-stu-id="dcb0d-228">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="dcb0d-229">Puede usar la clasificación basada en EDM con características de protección de información, como [directivas DLP de Office 365](data-loss-prevention-policies.md) y [directivas de archivo de Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="dcb0d-229">You can use EDM-based classification with information protection features, such as [Office 365 DLP policies](data-loss-prevention-policies.md) and [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span> <span data-ttu-id="dcb0d-230">El procedimiento siguiente describe cómo usar EDM con una directiva DLP que se crea en el Centro de seguridad y cumplimiento de Office 365.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-230">The following procedure describes how to use EDM with a DLP policy that is created in the Office 365 Security & Compliance Center.</span></span>

### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="dcb0d-231">Para crear una directiva DLP con EDM</span><span class="sxs-lookup"><span data-stu-id="dcb0d-231">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="dcb0d-232">Vaya al Centro de seguridad y cumplimiento ([https://protection.office.com](https://protection.office.com)).</span><span class="sxs-lookup"><span data-stu-id="dcb0d-232">Go to the Security & Compliance Center</span></span>

2. <span data-ttu-id="dcb0d-233">Haga clic en **Prevención de pérdida de datos** > **Directiva**.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-233">Click **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="dcb0d-234">Elija **Crear una directiva** > **Personalizada** > **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-234">Choose **Create a policy** > **Custom** > **Next**.</span></span>

4. <span data-ttu-id="dcb0d-235">En la pestaña **Nombre de la directiva**, especifique un nombre y una descripción y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-235">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="dcb0d-236">En la pestaña **Elegir ubicaciones**, haga clic en **Permitir elegir ubicaciones concretas** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-236">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span><br/><span data-ttu-id="dcb0d-237">![Opción Elegir ubicaciones](media/DLP-EDM-newpolicy-chooselocations.png)</span><span class="sxs-lookup"><span data-stu-id="dcb0d-237">![Choose locations option](media/DLP-EDM-newpolicy-chooselocations.png)</span></span><br/>

6. <span data-ttu-id="dcb0d-238">En la columna **Estado**, seleccione \*\*correo electrónico de Exchange \*\* y luego elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-238">In the **Status** column, select **Exchange email** only, and then choose **Next**.</span></span> <br/><span data-ttu-id="dcb0d-239">![Directiva EDM solo con Exchange](media/EDM-DLPpolicy-ExchangeOnly.png)</span><span class="sxs-lookup"><span data-stu-id="dcb0d-239">![EDM policy with Exchange only](media/EDM-DLPpolicy-ExchangeOnly.png)</span></span><br/>

7. <span data-ttu-id="dcb0d-240">En la pestaña **Configuración de directiva**, elija **Usar la configuración avanzada** y luego elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-240">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span><br/><span data-ttu-id="dcb0d-241">![Usar la configuración avanzada](media/edm-dlp-policy-advancedsettings.png)</span><span class="sxs-lookup"><span data-stu-id="dcb0d-241">![Use advanced settings](media/edm-dlp-policy-advancedsettings.png)</span></span><br/>

8. <span data-ttu-id="dcb0d-242">Elija **+ nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-242">Choose **+ New rule**.</span></span><br/><span data-ttu-id="dcb0d-243">![Crear una regla](media/edm-dlp-newrule.png)</span><span class="sxs-lookup"><span data-stu-id="dcb0d-243">![Create a query rule</span></span><br/>

9. <span data-ttu-id="dcb0d-244">En la sección **Nombre**, especifique un nombre y una descripción para la regla.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-244">Use the **Name and Description** section to specify a name and description for the category.</span></span><br/><span data-ttu-id="dcb0d-245">![Nuevos campos de regla](media/edm-dlp-newruleform.png)</span><span class="sxs-lookup"><span data-stu-id="dcb0d-245">![New rule fields](media/edm-dlp-newruleform.png)</span></span><br/>

10. <span data-ttu-id="dcb0d-246">En la sección **Condiciones** en la lista **+ Agregar una condición**, elija **El contenido incluye tipo confidencial**.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-246">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span><br/><span data-ttu-id="dcb0d-247">![El contenido incluye tipos de información confidencial](media/edm-dlp-newrule-conditions.png)</span><span class="sxs-lookup"><span data-stu-id="dcb0d-247">![Content contains sensitive info types](media/edm-dlp-newrule-conditions.png)</span></span><br/>

11. <span data-ttu-id="dcb0d-248">Busque el tipo de información confidencial que creó al configurar el paquete de reglas y elija **+ Agregar**.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-248">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span><br/><span data-ttu-id="dcb0d-249">![Busque el tipo de información confidencial](media/edm-dlp-newrulefindsensitiverulepack.png)</span><span class="sxs-lookup"><span data-stu-id="dcb0d-249">![Find the sensitive info type](media/edm-dlp-newrulefindsensitiverulepack.png)</span></span><br/><span data-ttu-id="dcb0d-250">Elija **Hecho**.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-250">Then choose **Done**.</span></span>

12. <span data-ttu-id="dcb0d-251">Termine de seleccionar las opciones para la regla, como **Notificaciones de usuario**, **Invalidaciones de usuario**, **Informes de incidentes**, etc. y luego elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-251">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="dcb0d-252">En la pestaña **Configuración de directiva**, revise las reglas y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-252">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="dcb0d-253">Especifique si quiere activar la directiva inmediatamente, probarla o dejarla desactivada.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-253">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="dcb0d-254">A continuación, elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-254">Then choose the **Next** button.</span></span>

15. <span data-ttu-id="dcb0d-255">En la pestaña **Revisar la configuración**, revise la directiva.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-255">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="dcb0d-256">Realice los cambios necesarios.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-256">Make any needed changes.</span></span> <span data-ttu-id="dcb0d-257">Cuando haya terminado, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-257">When you're ready, choose **Create**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dcb0d-258">Espere aproximadamente una hora para que la nueva directiva DLP pase por el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="dcb0d-258">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="dcb0d-259">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="dcb0d-259">Related articles</span></span>

[<span data-ttu-id="dcb0d-260">Tipos de información confidencial integrados y lo que buscan</span><span class="sxs-lookup"><span data-stu-id="dcb0d-260">Built-in sensitive information types and what they look for</span></span>](what-the-sensitive-information-types-look-for.md)

[<span data-ttu-id="dcb0d-261">Tipos de información confidencial personalizados</span><span class="sxs-lookup"><span data-stu-id="dcb0d-261">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)

[<span data-ttu-id="dcb0d-262">Información general de directivas DLP</span><span class="sxs-lookup"><span data-stu-id="dcb0d-262">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)

[<span data-ttu-id="dcb0d-263">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="dcb0d-263">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)

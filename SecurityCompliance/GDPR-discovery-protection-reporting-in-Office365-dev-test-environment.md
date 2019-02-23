---
title: 'RGPD: Informes, protección y detección de en el entorno de desarrollo y pruebas de Office 365'
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: Aquí se detallan las capacidades del RGPD en Office 365.
ms.openlocfilehash: ec715302a7e17ca3660c31f7143a94f8432d3086
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223869"
---
# <a name="gdpr-discovery-protection-and-reporting-in-the-office-365-devtest-environment"></a><span data-ttu-id="fee7a-103">RGPD: Informes, protección y detección de en el entorno de desarrollo y pruebas de Office 365</span><span class="sxs-lookup"><span data-stu-id="fee7a-103">GDPR discovery, protection, and reporting in the Office 365 dev/test environment</span></span>

 <span data-ttu-id="fee7a-104">**Resumen:** Aquí se detallan las capacidades del RGPD en Office 365.</span><span class="sxs-lookup"><span data-stu-id="fee7a-104">**Summary:** Demonstrate GDPR capabilities in Office 365.</span></span> 
  
<span data-ttu-id="fee7a-105">En este artículo se explica cómo configurar y demostrar las capacidades de informes, protección y detección de la información de identificación personal (DCP) según el Reglamento general de protección de datos (RGPD) en un entorno de desarrollo y pruebas de Office 365.</span><span class="sxs-lookup"><span data-stu-id="fee7a-105">This article describes how you configure and demonstrate personally identifiable information (PII) discovery, protection, and reporting for the General Data Protection Regulation (GDPR) in an Office 365 dev/test environment.</span></span>
  
## <a name="phase-1-create-and-configure-your-trial-office-365-subscription"></a><span data-ttu-id="fee7a-106">Fase 1: Crear y configurar una suscripción de prueba a Office 365</span><span class="sxs-lookup"><span data-stu-id="fee7a-106">Phase 1: Create and configure your trial Office 365 subscription</span></span>

<span data-ttu-id="fee7a-107">Realice primero los pasos de la [fase 2 del artículo sobre el entorno de desarrollo y pruebas de Office 365](https://docs.microsoft.com/Office365/Enterprise/office-365-dev-test-environment#phase-2-create-an-office-365-trial-subscription).</span><span class="sxs-lookup"><span data-stu-id="fee7a-107">First, follow the steps in [Phase 2 of the Office 365 dev/test environment](https://docs.microsoft.com/Office365/Enterprise/office-365-dev-test-environment#phase-2-create-an-office-365-trial-subscription) article.</span></span>

<span data-ttu-id="fee7a-108">Luego, realice los pasos aquí indicados para configurar el Supervisor de eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="fee7a-108">Next, use these steps to configure the eDiscovery manager:</span></span>

1. <span data-ttu-id="fee7a-109">Inicie sesión en su inquilino de prueba de Office 365 con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="fee7a-109">Sign in to your Office 365 trial tenant with your global administrator account.</span></span>
2. <span data-ttu-id="fee7a-110">En la página principal de Office 365, haga clic en **Seguridad y cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-110">From the Office 365 home page, click **Security & Compliance**.</span></span>
3. <span data-ttu-id="fee7a-111">En la pestaña Seguridad y cumplimento, haga clic en **Permisos** > **Administrador de eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-111">From the new Security & Compliance tab, click **Permissions** > **eDiscovery Manager**.</span></span>
4. <span data-ttu-id="fee7a-112">Haga clic en la opción **Editar** del Administrador de eDiscovery y, luego, haga clic en **Elegir administrador de eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-112">Click **Edit** for eDiscovery Manager, and then click **Choose eDiscovery Manager**.</span></span>
5. <span data-ttu-id="fee7a-113">Haga clic en **+ Agregar**, busque el nombre de su cuenta de administrador global y agréguela como Supervisor de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="fee7a-113">Click **+ Add**, search for your global administrator account name and add your global administrator account as an eDiscovery Manager.</span></span>
6. <span data-ttu-id="fee7a-114">Haga clic en **Listo** > **Guardar** > **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-114">Click **Done** > **Save** > **Close**.</span></span>
  
## <a name="phase-2-add-personally-identifiable-information-to-your-tenant"></a><span data-ttu-id="fee7a-115">Fase 2: Agregar información de identificación personal al inquilino</span><span class="sxs-lookup"><span data-stu-id="fee7a-115">Phase 2: Add personally identifiable information to your tenant</span></span>

<span data-ttu-id="fee7a-116">En esta fase, creará un documento con DCP consistente en una serie de números de cuenta bancaria internacional (IBAN) de ejemplo y lo almacenará en un sitio de SharePoint Online de su entorno de desarrollo y pruebas de Office 365.</span><span class="sxs-lookup"><span data-stu-id="fee7a-116">In this phase, you create a document with PII for a set of example International Banking Account Numbers (IBANs) and store it on a SharePoint Online site in your Office 365 dev/test environment.</span></span>

1. <span data-ttu-id="fee7a-117">En el equipo local, abra Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="fee7a-117">On your local computer, open Microsoft Word.</span></span>
2. <span data-ttu-id="fee7a-118">Pegue la siguiente tabla en el archivo de Word y guárdelo como "IBANs.docx" en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="fee7a-118">Paste the following table in the Word file and save it as ‘IBANs.docx’ on your local computer.</span></span>
    
    <span data-ttu-id="fee7a-119">Número</span><span class="sxs-lookup"><span data-stu-id="fee7a-119">Number</span></span>  |<span data-ttu-id="fee7a-120">País</span><span class="sxs-lookup"><span data-stu-id="fee7a-120">Country</span></span>  |<span data-ttu-id="fee7a-121">Código</span><span class="sxs-lookup"><span data-stu-id="fee7a-121">Code</span></span> |<span data-ttu-id="fee7a-122">IBAN</span><span class="sxs-lookup"><span data-stu-id="fee7a-122">IBAN</span></span>  |
    |---------|---------|---------|---------|
    |<span data-ttu-id="fee7a-123">1</span><span class="sxs-lookup"><span data-stu-id="fee7a-123">1</span></span>     |  <span data-ttu-id="fee7a-124">Austria SEPA</span><span class="sxs-lookup"><span data-stu-id="fee7a-124">Austria SEPA</span></span>      | <span data-ttu-id="fee7a-125">AT</span><span class="sxs-lookup"><span data-stu-id="fee7a-125">AT</span></span>            |<span data-ttu-id="fee7a-126">AT611904300234573201</span><span class="sxs-lookup"><span data-stu-id="fee7a-126">AT611904300234573201</span></span>       |
    |<span data-ttu-id="fee7a-127">2</span><span class="sxs-lookup"><span data-stu-id="fee7a-127">2</span></span>     |  <span data-ttu-id="fee7a-128">Bulgaria SEPA</span><span class="sxs-lookup"><span data-stu-id="fee7a-128">Bulgaria SEPA</span></span>       |<span data-ttu-id="fee7a-129">BG</span><span class="sxs-lookup"><span data-stu-id="fee7a-129">BG</span></span>    |<span data-ttu-id="fee7a-130">BG80BNBG96611020345678</span><span class="sxs-lookup"><span data-stu-id="fee7a-130">BG80BNBG96611020345678</span></span>      |
    |<span data-ttu-id="fee7a-131">3</span><span class="sxs-lookup"><span data-stu-id="fee7a-131">3</span></span>     |  <span data-ttu-id="fee7a-132">Dinamarca SEPA</span><span class="sxs-lookup"><span data-stu-id="fee7a-132">Denmark SEPA</span></span>      |   <span data-ttu-id="fee7a-133">DK</span><span class="sxs-lookup"><span data-stu-id="fee7a-133">DK</span></span>      |<span data-ttu-id="fee7a-134">DK5000400440116243</span><span class="sxs-lookup"><span data-stu-id="fee7a-134">DK5000400440116243</span></span>      |
    |<span data-ttu-id="fee7a-135">4</span><span class="sxs-lookup"><span data-stu-id="fee7a-135">4</span></span>     |  <span data-ttu-id="fee7a-136">Finlandia SEPA</span><span class="sxs-lookup"><span data-stu-id="fee7a-136">Finland SEPA</span></span>      |   <span data-ttu-id="fee7a-137">FI</span><span class="sxs-lookup"><span data-stu-id="fee7a-137">FI</span></span>      |<span data-ttu-id="fee7a-138">FI2112345600000785</span><span class="sxs-lookup"><span data-stu-id="fee7a-138">FI2112345600000785</span></span>         |
    |<span data-ttu-id="fee7a-139">5</span><span class="sxs-lookup"><span data-stu-id="fee7a-139">5</span></span>     |  <span data-ttu-id="fee7a-140">Francia SEPA</span><span class="sxs-lookup"><span data-stu-id="fee7a-140">France SEPA</span></span>       |   <span data-ttu-id="fee7a-141">FR</span><span class="sxs-lookup"><span data-stu-id="fee7a-141">FR</span></span>      |<span data-ttu-id="fee7a-142">FR1420041010050500013M02606</span><span class="sxs-lookup"><span data-stu-id="fee7a-142">FR1420041010050500013M02606</span></span>         |
    |<span data-ttu-id="fee7a-143">6</span><span class="sxs-lookup"><span data-stu-id="fee7a-143">6</span></span>     |  <span data-ttu-id="fee7a-144">Alemania SEPA</span><span class="sxs-lookup"><span data-stu-id="fee7a-144">Germany SEPA</span></span>      |   <span data-ttu-id="fee7a-145">DE</span><span class="sxs-lookup"><span data-stu-id="fee7a-145">DE</span></span>      |<span data-ttu-id="fee7a-146">DE89370400440532013000</span><span class="sxs-lookup"><span data-stu-id="fee7a-146">DE89370400440532013000</span></span>         |
    |<span data-ttu-id="fee7a-147">7</span><span class="sxs-lookup"><span data-stu-id="fee7a-147">7</span></span>     |  <span data-ttu-id="fee7a-148">Grecia SEPA</span><span class="sxs-lookup"><span data-stu-id="fee7a-148">Greece SEPA</span></span>       |   <span data-ttu-id="fee7a-149">GR</span><span class="sxs-lookup"><span data-stu-id="fee7a-149">GR</span></span>      |<span data-ttu-id="fee7a-150">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="fee7a-150">GR1601101250000000012300695</span></span>         |
    |<span data-ttu-id="fee7a-151">8</span><span class="sxs-lookup"><span data-stu-id="fee7a-151">8</span></span>     |  <span data-ttu-id="fee7a-152">Italia SEPA</span><span class="sxs-lookup"><span data-stu-id="fee7a-152">Italy SEPA</span></span>       |    <span data-ttu-id="fee7a-153">TI</span><span class="sxs-lookup"><span data-stu-id="fee7a-153">IT</span></span>     |<span data-ttu-id="fee7a-154">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="fee7a-154">GR1601101250000000012300695</span></span>         |
    |<span data-ttu-id="fee7a-155">9</span><span class="sxs-lookup"><span data-stu-id="fee7a-155">9</span></span>     |  <span data-ttu-id="fee7a-156">Países Bajos SEPA</span><span class="sxs-lookup"><span data-stu-id="fee7a-156">Netherlands SEPA</span></span>      |   <span data-ttu-id="fee7a-157">NL</span><span class="sxs-lookup"><span data-stu-id="fee7a-157">NL</span></span>      |    <span data-ttu-id="fee7a-158">NL91ABNA0417164300</span><span class="sxs-lookup"><span data-stu-id="fee7a-158">NL91ABNA0417164300</span></span>     |
    |<span data-ttu-id="fee7a-159">10</span><span class="sxs-lookup"><span data-stu-id="fee7a-159">10</span></span>     | <span data-ttu-id="fee7a-160">Polonia SEPA</span><span class="sxs-lookup"><span data-stu-id="fee7a-160">Poland SEPA</span></span>       |  <span data-ttu-id="fee7a-161">PL</span><span class="sxs-lookup"><span data-stu-id="fee7a-161">PL</span></span>       | <span data-ttu-id="fee7a-162">PL27114020040000300201355387</span><span class="sxs-lookup"><span data-stu-id="fee7a-162">PL27114020040000300201355387</span></span>        |

<span data-ttu-id="fee7a-163">Nota: Este conjunto de datos de ejemplo se obtuvo a partir de información disponible públicamente y solo ha de usarse con fines de pruebas.</span><span class="sxs-lookup"><span data-stu-id="fee7a-163">Note:- This sample data set is derived from publicly available information and is intended to be used for test purposes only.</span></span>

3. <span data-ttu-id="fee7a-164">En una pestaña nueva del explorador, escriba: **https://**\<suNombreDeInquilino\>**.sharepoint.com**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-164">In a new tab of your browser, type:  **https://**\<YourTenantName\>**.sharepoint.com**</span></span>
4. <span data-ttu-id="fee7a-p101">Haga clic en **Documentos** para abrir la biblioteca de documentos de este sitio. Si se le pide realizar un recorrido de experiencia de lista nueva, haga clic en **Siguiente** hasta que finalice.</span><span class="sxs-lookup"><span data-stu-id="fee7a-p101">Click **Documents** to open the document library for this site. If you’re prompted for a new list experience tour, click **Next** until it’s finished.</span></span>
5.  <span data-ttu-id="fee7a-167">Haga clic en **Cargar** > **Archivos** y seleccione el archivo IBANs.docx que creó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="fee7a-167">Click **Upload** > **Files** and select the IBANs.docx you created in step 2.</span></span>

  
## <a name="phase-3-demonstrate-data-discovery"></a><span data-ttu-id="fee7a-168">Fase 3: Demostrar la detección de datos</span><span class="sxs-lookup"><span data-stu-id="fee7a-168">Phase 3: Demonstrate data discovery</span></span>

<span data-ttu-id="fee7a-169">En esta fase, demostrará cómo realizar una búsqueda para encontrar el documento que creó y almacenó en la fase 2 a partir de su contenido de números IBAN.</span><span class="sxs-lookup"><span data-stu-id="fee7a-169">In this phase, you demonstrate search to find the document created and stored in Phase 2, based on its content containing IBANs.</span></span>

1. <span data-ttu-id="fee7a-170">En la pestaña Seguridad y cumplimiento, haga clic en **Inicio** y, después, haga clic en **Búsqueda e investigación** > **Búsqueda de contenido**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-170">From the Security & Compliance tab, click **Home**, and then click **Search & investigation** > **Content search**.</span></span>
2. <span data-ttu-id="fee7a-171">Haga clic en **+** para crear un elemento de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="fee7a-171">Create a new search item by clicking on **+**.</span></span>
3. <span data-ttu-id="fee7a-172">En una ventana nueva, indique la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="fee7a-172">In a new window, provide the following information:</span></span>  
    <span data-ttu-id="fee7a-p102">a. Nombre: Búsqueda de IBAN</span><span class="sxs-lookup"><span data-stu-id="fee7a-p102">a. Name: IBAN Search</span></span>  
    <span data-ttu-id="fee7a-p103">b. ¿Dónde desea que busquemos?: **Elegir los sitios específicos para buscar** (haga clic en **+**) y escriba la dirección URL del sitio: **https://**\<suNombreDeInquilino\>**.sharepoint.com/**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-p103">b. Where do you want us to look?: **Choose specific sites to search** (click **+**), and then enter the site's URL: **https://**\<YourTenantName\>**.sharepoint.com/**</span></span>  
    <span data-ttu-id="fee7a-p104">c. Haga clic en **Agregar** y, luego, haga clic en **Aceptar**. Si ve una advertencia, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-p104">c. Click **Add**, and then click **OK**. If you see a Warning, click **OK**.</span></span>  
    <span data-ttu-id="fee7a-p105">d. Haga clic en **Siguiente** en una ventana **Nueva búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-p105">d. Click **Next** on a **New search** window.</span></span>  
    <span data-ttu-id="fee7a-p106">e. En **¿Qué desea que busquemos?**: **SensitiveType: "Número de cuenta bancaria internacional (IBAN)"** y, después, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-p106">e. For **What do you want us to look for?**: **SensitiveType:"International Banking Account Number (IBAN)"**, and then click **Search**.</span></span>

4. <span data-ttu-id="fee7a-184">Confirme que aparece al menos un elemento en los resultados de la **búsqueda de IBAN**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-184">Make sure you see at least one item listed in the **IBAN Search** results.</span></span>


## <a name="phase-4-create-a-custom-sensitive-information-type-via-powershell"></a><span data-ttu-id="fee7a-185">Fase 4: Crear un tipo de información confidencial a través de PowerShell</span><span class="sxs-lookup"><span data-stu-id="fee7a-185">Phase 4: Create a custom sensitive information type via PowerShell</span></span>

<span data-ttu-id="fee7a-p107">En esta fase, creará un tipo de información confidencial personalizado para la empresa ficticia Contoso Corporation con Microsoft PowerShell. Contoso usa un número de cliente de Contoso (CCN) para distinguir a cada cliente en la base de datos de clientes. Un CCN tiene la siguiente estructura:</span><span class="sxs-lookup"><span data-stu-id="fee7a-p107">In this phase, you create a custom sensitive information type for the fictional Contoso Corporation using Microsoft PowerShell.  Contoso uses a Contoso Customer Number (CCN) to identify each customer in their customer database. A CCN consists of the following structure:</span></span>
- <span data-ttu-id="fee7a-189">Dos dígitos que representan el año en el que se creó el registro.</span><span class="sxs-lookup"><span data-stu-id="fee7a-189">Two digits to represent the year that the record was created.</span></span>
    - <span data-ttu-id="fee7a-190">Contoso fue fundado en 2002, por lo tanto, el valor mínimo posible sería 02.</span><span class="sxs-lookup"><span data-stu-id="fee7a-190">Contoso was founded in 2002; therefore, the earliest possible value would be 02.</span></span> 
- <span data-ttu-id="fee7a-191">Tres dígitos que representan la agencia asociada que creó el registro.</span><span class="sxs-lookup"><span data-stu-id="fee7a-191">Three digits to represent the partner agency that created the record.</span></span>
    - <span data-ttu-id="fee7a-192">Los posibles valores de agencia están comprendidos entre 000 y 999.</span><span class="sxs-lookup"><span data-stu-id="fee7a-192">Possible agency values range from 000 to 999.</span></span> 
- <span data-ttu-id="fee7a-193">Un carácter alfabético que representa la línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="fee7a-193">An alphabetic character to represent the line of business.</span></span>
    - <span data-ttu-id="fee7a-194">Los valores posibles son a-z y se debe distinguir mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="fee7a-194">Possible values are a-z and should be case insensitive.</span></span>
- <span data-ttu-id="fee7a-195">Un número de serie de cuatro dígitos.</span><span class="sxs-lookup"><span data-stu-id="fee7a-195">A four-digit serial number.</span></span> 
    - <span data-ttu-id="fee7a-196">Los posibles valores de número de serie están comprendidos entre 0000 y 9999.</span><span class="sxs-lookup"><span data-stu-id="fee7a-196">Possible serial number values range from 0000 to 9999.</span></span>   

<span data-ttu-id="fee7a-p108">Contoso siempre hace referencia a los clientes usando un CCN en la correspondencia interna, la correspondencia externa, los documentos y otros formularios. En dicha empresa se necesita un tipo de información confidencial personalizado que permita detectar el uso de CCN en el contenido de Office 365 para, así, poder poner en marcha medidas de protección en el uso de esta información de identificación personal.</span><span class="sxs-lookup"><span data-stu-id="fee7a-p108">Contoso always refers to customers by using a CCN in internal correspondence, external correspondence, documents, and other forms. Contoso needs a custom sensitive item type to detect the use of CCNs in Office 365 content so that they may apply protection to the use of this form of personal identifiable information.</span></span>

1. <span data-ttu-id="fee7a-199">Siga las instrucciones del tema [Conectarse al PowerShell del Centro de seguridad y cumplimiento de Office 365 usando la autenticación multifactor](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) y conéctese al Centro de seguridad y cumplimiento con el UPN de su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="fee7a-199">Use the instructions in [Connect to Office 365 Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) and connect to the Security & Compliance Center with UPN of your global administrator account.</span></span>
2. <span data-ttu-id="fee7a-200">Ejecute los siguientes comandos de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fee7a-200">Run the following PowerShell commands.</span></span>

     ```
    #Create & start search for sample data
    $searchName = "Sample Customer Information Search"
    $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
    New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
    Start-ComplianceSearch -Identity $searchName#Create & start search for sample data
    $searchName = "Sample Customer Information Search"
    $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
    New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
    Start-ComplianceSearch -Identity $searchName
    ```
3. <span data-ttu-id="fee7a-201">Ejecute los siguientes comandos de PowerShell y copie los GUID generados (en el orden en que aparecen) en una instancia del Bloc de notas abierta del equipo.</span><span class="sxs-lookup"><span data-stu-id="fee7a-201">Run the following PowerShell commands and copy the generated GUIDs to an open instance of Notepad on your computer in the order in which they are listed.</span></span>
    ```
    #Generate three unique GUIDs
    Write-Host "GUID1 = "([guid]::NewGuid().Guid)
    Write-Host "GUID2 = "([guid]::NewGuid().Guid)
    Write-Host "GUID3 = "([guid]::NewGuid().Guid)
    ```
4. <span data-ttu-id="fee7a-202">En el equipo local, abra otra instancia del Bloc de notas y pegue el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="fee7a-202">On your local computer, open another instance of Notepad and paste in the following content:</span></span>

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce"> 
    <RulePack id="GUID1">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="GUID2" />
    <Details defaultLangCode="en"> 
    <LocalizedDetails langcode="en"> 
    <PublisherName>Contoso Ltd.</PublisherName> 
    <Name>Contoso Rule Package</Name> 
    <Description>Defines Contoso's custom set of classification rules</Description>
    </LocalizedDetails>
    </Details>
    </RulePack>
    <Rules>
    <!-- Contoso Customer Number (CCN) -->
    <Entity id="GUID3" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
    <IdMatch idRef="Regex_contoso_ccn" />
    <Match idRef="Keyword_contoso_ccn" />
    <Match idRef="Regex_eu_date" />
    </Pattern>
    </Entity>
    <Regex id="Regex_contoso_ccn">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</Regex>
    <Keyword id="Keyword_contoso_ccn">
    <Group matchStyle="word">
    <Term caseSensitive="false">customer number</Term>
    <Term caseSensitive="false">customer no</Term>
    <Term caseSensitive="false">customer #</Term>
    <Term caseSensitive="false">customer#</Term>
    <Term caseSensitive="false">Contoso customer</Term>
    </Group>
    </Keyword>
    <Regex id="Regex_eu_date"> (0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)? |feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|apr(ile|il)?|abr(il)?|avril |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)? |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}</Regex>
    <LocalizedStrings>
    <Resource idRef="GUID3">
    <Name default="true" langcode="en-us">Contoso Customer Number (CCN)</Name>
    <Description default="true" langcode="en-us">Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date</Description>
    </Resource>
    </LocalizedStrings>
    </Rules>
    </RulePackage>
    ```
5. <span data-ttu-id="fee7a-203">Reemplace los valores de GUID1, GUID2 y GUID3 del texto XML del paso 4 por sus valores del paso 3 y, después, guarde el contenido en el equipo local con el nombre ContosoCCN.xml.</span><span class="sxs-lookup"><span data-stu-id="fee7a-203">Replace the values of GUID1, GUID2, and GUID3 in the XML text of step 4 with their values from step 3, and then save the contents on your local computer with the name ContosoCCN.xml.</span></span>
6. <span data-ttu-id="fee7a-204">Rellene la ruta de acceso al archivo ContosoCCN.xml y ejecute los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="fee7a-204">Fill in the path to your ContosoCCN.xml file and run the following commands.</span></span>
    ```
    #Create new Sensitive Information Type
    $path="<path to the ContosoCCN.xml file, such as C:\Scripts\ContosoCCN.xml>"
    New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path $path -Encoding Byte -ReadCount 0)
    ```
7. <span data-ttu-id="fee7a-p109">En la pestaña Seguridad y cumplimiento, haga clic en **Clasificaciones** > **Tipos de información confidencial**. El número de cliente de Contoso (CCN) debería figurar en la lista.</span><span class="sxs-lookup"><span data-stu-id="fee7a-p109">From the Security & Compliance tab, click **Classifications** > **Sensitive information types**. You should see the Contoso Customer Number (CCN) in the list.</span></span>

## <a name="phase-5-demonstrate-data-protection"></a><span data-ttu-id="fee7a-207">Fase 5: Demostrar la protección de datos</span><span class="sxs-lookup"><span data-stu-id="fee7a-207">Phase 5: Demonstrate data protection</span></span>

<span data-ttu-id="fee7a-p110">La protección de información personal en Office 365 implica el uso de funciones de prevención de pérdida de datos (DLP). Con las directivas DLP del Centro de seguridad y cumplimiento de Office 365, toda la información confidencial en Office 365 se puede proteger automáticamente.</span><span class="sxs-lookup"><span data-stu-id="fee7a-p110">Protection of personal information in Office 365 includes using data loss prevention (DLP) capabilities.  With DLP policies in the Office 365 Security & Compliance Center, you can automatically protect sensitive information across Office 365.</span></span>

<span data-ttu-id="fee7a-p111">Existen varias formas de aplicar la protección. Un nivel de protección de la información con DLP de Office 365 consiste en instruir y concienciar acerca de dónde se almacenan los datos de los residentes de la UE en su entorno y cómo sus empleados pueden tratar estos datos.</span><span class="sxs-lookup"><span data-stu-id="fee7a-p111">There are multiple ways you can apply the protection. Educating and raising awareness to where EU resident data is stored in your environment and how your employees are permitted to handle it represents one level of information protection using Office 365 DLP.</span></span>

<span data-ttu-id="fee7a-212">En esta fase, creará una directiva DLP y demostrará cómo se aplica al archivo IBANs.docx que almacenó en SharePoint Online en la fase 2 cuando intente enviar un correo electrónico que contiene números IBAN.</span><span class="sxs-lookup"><span data-stu-id="fee7a-212">In this phase, you create a new DLP policy and demonstrate how it gets applied to the IBANs.docx file you stored in SharePoint Online in Phase 2 and when you attempt to send an email containing IBANs.</span></span>

1. <span data-ttu-id="fee7a-213">En la pestaña Seguridad y cumplimiento del explorador, haga clic en **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-213">From the Security & Compliance tab of your browser, click **Home**.</span></span>
2. <span data-ttu-id="fee7a-214">Haga clic en **Prevención de pérdida de datos** > **Directiva**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-214">Click **Data loss prevention** > **Policy**.</span></span>
3. <span data-ttu-id="fee7a-215">Haga clic en **+ Crear una directiva**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-215">Click **+ Create a policy**.</span></span>
4. <span data-ttu-id="fee7a-216">En **Empezar con una plantilla o crear una directiva personalizada**, haga clic en **Personalizada** > **Directiva personalizada** > **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-216">In **Start with a template or create a custom policy**, click **Custom** > **Custom policy** > **Next**.</span></span>
5. <span data-ttu-id="fee7a-p112">En **Dar un nombre a la directiva**, especifique los siguientes detalles y haga clic en **Siguiente**: a. Nombre: **Directiva de DCP de ciudadanos de la UE** b. Descripción: **Proteger la información de identificación personal de los ciudadanos europeos**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-p112">In **Name your policy**, provide the following details and then click **Next**:  a. Name: **EU Citizen PII Policy** b. Description: **Protect the personally identifiable information of European citizens**</span></span>
6. <span data-ttu-id="fee7a-p113">En **Elegir ubicaciones**, seleccione **Todas las ubicaciones en Office 365**. Se incluirá el contenido del correo electrónico de Exchange y de los documentos de OneDrive y SharePoint. Tras esto, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-p113">In **Choose locations**, select **All locations in Office 365**. This will include content in Exchange email and OneDrive and SharePoint documents. And then click **Next**.</span></span>
7. <span data-ttu-id="fee7a-223">En **Personalizar el tipo de contenido que quiere proteger**, haga clic en **Buscar contenido que incluya:** y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-223">In **Customize the type of content you want to protect**, click **Find content that contains:** and then click **Edit**.</span></span>
8. <span data-ttu-id="fee7a-224">En **Elegir los tipos de contenido que se van a proteger**, haga clic en **Agregar** > **Tipos de información confidencial**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-224">In **Choose the types of content to protect**, click **Add** > **Sensitive info types**.</span></span>
9. <span data-ttu-id="fee7a-225">En **Tipos de información confidencial**, haga clic en **+ Agregar**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-225">In **Sensitive info types**, click **+ Add**.</span></span>
10. <span data-ttu-id="fee7a-226">En **Tipos de información confidencial**, busque **IBAN**, active la casilla **Número de cuenta bancaria internacional (IBAN)** y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-226">In **Sensitive info types**, search for **IBAN**, select the check box for **International Banking Account Number (IBAN)**, and then click **Add**.</span></span>
11. <span data-ttu-id="fee7a-227">Compruebe que el tipo de información confidencial **Número de cuenta bancaria internacional (IBAN)** se ha agregado y haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-227">Confirm that the **International Banking Account Number (IBAN)** sensitive information type was added, and then click **Done**.</span></span>
12. <span data-ttu-id="fee7a-228">En **El contenido incluye**, confirme que se han agregado los tipos de información confidencial y, después, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-228">In **Content contains**, confirm that the sensitive information types were added and then click **Save**.</span></span>
13. <span data-ttu-id="fee7a-229">En **Personalizar el tipo de contenido que quiere proteger**, confirme que **Buscar contenido que incluya:** contiene **Número de cuenta bancaria internacional (IBAN)** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-229">In **Customize the type of content you want to protect**, confirm  **Find content that contains:** contains the **International Banking Account Number (IBAN)**, and then click **Next**.</span></span>
14. <span data-ttu-id="fee7a-230">En **Detectar cuándo el contenido compartido incluye:**, cambie el valor de **10** a **1** y, luego, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-230">In **Detect when content that's being shared contains:**, change the value from **10** to **1**, and then click **Next**.</span></span>
15. <span data-ttu-id="fee7a-231">En **¿Desea activar la directiva o probarla primero?**, seleccione las siguientes opciones y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-231">In **Do you want to turn on the policy or test things out first?**, choose the following settings, and then click **Next**.</span></span>  
    <span data-ttu-id="fee7a-p114">a. Seleccione la opción **Me gustaría probarla primero**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-p114">a. Select the option for **I'd like to test it out first**</span></span>  
    <span data-ttu-id="fee7a-p115">b. Active la casilla de verificación **Mostrar sugerencias de directiva durante el modo de prueba**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-p115">b. Select the check box for **Show policy tips while in test mode**</span></span> 
16. <span data-ttu-id="fee7a-p116">En **Revisar la configuración**, revise la configuración y, tras ello, haga clic en **Crear**. Nota: Después de crear una directiva DLP, esta tardará algún tiempo en entrar en vigor.</span><span class="sxs-lookup"><span data-stu-id="fee7a-p116">In **Review your settings**, click **Create** after reviewing the settings. NOTE: After you create a new DLP policy, it will take a while for it to take effect.</span></span>
17. <span data-ttu-id="fee7a-238">En el equipo local, abra una instancia privada del explorador.</span><span class="sxs-lookup"><span data-stu-id="fee7a-238">On your local computer, open a private instance of your browser.</span></span>
18. <span data-ttu-id="fee7a-239">En la barra de direcciones, escriba **https://**\<suNombreDeInquilino\>**.sharepoint.com** e inicie sesión con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="fee7a-239">In the address bar, type **https://**\<YourTenantName\>**.sharepoint.com** and sign in using your global administrator account.</span></span>
19. <span data-ttu-id="fee7a-240">Haga clic en **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-240">Click **Documents**.</span></span>
20. <span data-ttu-id="fee7a-p117">Haga clic en el archivo "IBANs.docx". Debería aparecer "Sugerencia de directiva para IBANs.docx". El archivo IBANs.docx se ha compartido con destinatarios externos, lo cual infringe la directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="fee7a-p117">Click the file named ‘IBANs.docx’. You should see ‘Policy tip for IBANs.docx’.  The IBANs.docx file was shared with external recipients, which violates the DLP policy.</span></span> 
21. <span data-ttu-id="fee7a-244">En la barra de direcciones, escriba: `https://outlook.office365.com`</span><span class="sxs-lookup"><span data-stu-id="fee7a-244">In the address bar, type: `https://outlook.office365.com`</span></span>
22. <span data-ttu-id="fee7a-245">Haga clic en **Nuevo** - **Mensaje de correo electrónico** e indique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fee7a-245">Click **New** - **Email message** and provide the following:</span></span>  
    - <span data-ttu-id="fee7a-246">**Para:** \<dirección de correo electrónico personal\></span><span class="sxs-lookup"><span data-stu-id="fee7a-246">**To:** \<a personal email address\></span></span>  
    - <span data-ttu-id="fee7a-247">**Asunto:** Prueba de RGPD</span><span class="sxs-lookup"><span data-stu-id="fee7a-247">**Subject:** GDPR Test</span></span>  
    - <span data-ttu-id="fee7a-248">**Cuerpo:** Copie esta tabla de valores:</span><span class="sxs-lookup"><span data-stu-id="fee7a-248">**Body:** Copy in the table of values shown below.</span></span>
  
        |<span data-ttu-id="fee7a-249">Número</span><span class="sxs-lookup"><span data-stu-id="fee7a-249">Number</span></span>  |<span data-ttu-id="fee7a-250">País</span><span class="sxs-lookup"><span data-stu-id="fee7a-250">Country</span></span>  |<span data-ttu-id="fee7a-251">Código</span><span class="sxs-lookup"><span data-stu-id="fee7a-251">Code</span></span> |<span data-ttu-id="fee7a-252">IBAN</span><span class="sxs-lookup"><span data-stu-id="fee7a-252">IBAN</span></span>  |
        |---------|---------|---------|---------|
        |<span data-ttu-id="fee7a-253">1</span><span class="sxs-lookup"><span data-stu-id="fee7a-253">1</span></span>     |  <span data-ttu-id="fee7a-254">Austria SEPA</span><span class="sxs-lookup"><span data-stu-id="fee7a-254">Austria SEPA</span></span>      | <span data-ttu-id="fee7a-255">AT</span><span class="sxs-lookup"><span data-stu-id="fee7a-255">AT</span></span>            |<span data-ttu-id="fee7a-256">AT611904300234573201</span><span class="sxs-lookup"><span data-stu-id="fee7a-256">AT611904300234573201</span></span>       |
        |<span data-ttu-id="fee7a-257">2</span><span class="sxs-lookup"><span data-stu-id="fee7a-257">2</span></span>     |  <span data-ttu-id="fee7a-258">Bulgaria SEPA</span><span class="sxs-lookup"><span data-stu-id="fee7a-258">Bulgaria SEPA</span></span>       |<span data-ttu-id="fee7a-259">BG</span><span class="sxs-lookup"><span data-stu-id="fee7a-259">BG</span></span>    |<span data-ttu-id="fee7a-260">BG80BNBG96611020345678</span><span class="sxs-lookup"><span data-stu-id="fee7a-260">BG80BNBG96611020345678</span></span>      |
        |<span data-ttu-id="fee7a-261">3</span><span class="sxs-lookup"><span data-stu-id="fee7a-261">3</span></span>     |  <span data-ttu-id="fee7a-262">Dinamarca SEPA</span><span class="sxs-lookup"><span data-stu-id="fee7a-262">Denmark SEPA</span></span>      |   <span data-ttu-id="fee7a-263">DK</span><span class="sxs-lookup"><span data-stu-id="fee7a-263">DK</span></span>      |<span data-ttu-id="fee7a-264">DK5000400440116243</span><span class="sxs-lookup"><span data-stu-id="fee7a-264">DK5000400440116243</span></span>      |
        |<span data-ttu-id="fee7a-265">4</span><span class="sxs-lookup"><span data-stu-id="fee7a-265">4</span></span>     |  <span data-ttu-id="fee7a-266">Finlandia SEPA</span><span class="sxs-lookup"><span data-stu-id="fee7a-266">Finland SEPA</span></span>      |   <span data-ttu-id="fee7a-267">FI</span><span class="sxs-lookup"><span data-stu-id="fee7a-267">FI</span></span>      |<span data-ttu-id="fee7a-268">FI2112345600000785</span><span class="sxs-lookup"><span data-stu-id="fee7a-268">FI2112345600000785</span></span>         |
        |<span data-ttu-id="fee7a-269">5</span><span class="sxs-lookup"><span data-stu-id="fee7a-269">5</span></span>     |  <span data-ttu-id="fee7a-270">Francia SEPA</span><span class="sxs-lookup"><span data-stu-id="fee7a-270">France SEPA</span></span>       |   <span data-ttu-id="fee7a-271">FR</span><span class="sxs-lookup"><span data-stu-id="fee7a-271">FR</span></span>      |<span data-ttu-id="fee7a-272">FR1420041010050500013M02606</span><span class="sxs-lookup"><span data-stu-id="fee7a-272">FR1420041010050500013M02606</span></span>         |
        |<span data-ttu-id="fee7a-273">6</span><span class="sxs-lookup"><span data-stu-id="fee7a-273">6</span></span>     |  <span data-ttu-id="fee7a-274">Alemania SEPA</span><span class="sxs-lookup"><span data-stu-id="fee7a-274">Germany SEPA</span></span>      |   <span data-ttu-id="fee7a-275">DE</span><span class="sxs-lookup"><span data-stu-id="fee7a-275">DE</span></span>      |<span data-ttu-id="fee7a-276">DE89370400440532013000</span><span class="sxs-lookup"><span data-stu-id="fee7a-276">DE89370400440532013000</span></span>         |
        |<span data-ttu-id="fee7a-277">7</span><span class="sxs-lookup"><span data-stu-id="fee7a-277">7</span></span>     |  <span data-ttu-id="fee7a-278">Grecia SEPA</span><span class="sxs-lookup"><span data-stu-id="fee7a-278">Greece SEPA</span></span>       |   <span data-ttu-id="fee7a-279">GR</span><span class="sxs-lookup"><span data-stu-id="fee7a-279">GR</span></span>      |<span data-ttu-id="fee7a-280">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="fee7a-280">GR1601101250000000012300695</span></span>         |
        |<span data-ttu-id="fee7a-281">8</span><span class="sxs-lookup"><span data-stu-id="fee7a-281">8</span></span>     |  <span data-ttu-id="fee7a-282">Italia SEPA</span><span class="sxs-lookup"><span data-stu-id="fee7a-282">Italy SEPA</span></span>       |    <span data-ttu-id="fee7a-283">TI</span><span class="sxs-lookup"><span data-stu-id="fee7a-283">IT</span></span>     |<span data-ttu-id="fee7a-284">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="fee7a-284">GR1601101250000000012300695</span></span>         |
        |<span data-ttu-id="fee7a-285">9</span><span class="sxs-lookup"><span data-stu-id="fee7a-285">9</span></span>     |  <span data-ttu-id="fee7a-286">Países Bajos SEPA</span><span class="sxs-lookup"><span data-stu-id="fee7a-286">Netherlands SEPA</span></span>      |   <span data-ttu-id="fee7a-287">NL</span><span class="sxs-lookup"><span data-stu-id="fee7a-287">NL</span></span>      |   <span data-ttu-id="fee7a-288">NL91ABNA0417164300</span><span class="sxs-lookup"><span data-stu-id="fee7a-288">NL91ABNA0417164300</span></span>      |
        |<span data-ttu-id="fee7a-289">10</span><span class="sxs-lookup"><span data-stu-id="fee7a-289">10</span></span>     | <span data-ttu-id="fee7a-290">Polonia SEPA</span><span class="sxs-lookup"><span data-stu-id="fee7a-290">Poland SEPA</span></span>       |  <span data-ttu-id="fee7a-291">PL</span><span class="sxs-lookup"><span data-stu-id="fee7a-291">PL</span></span>       | <span data-ttu-id="fee7a-292">PL27114020040000300201355387</span><span class="sxs-lookup"><span data-stu-id="fee7a-292">PL27114020040000300201355387</span></span>        |

<span data-ttu-id="fee7a-293">Nota: Este conjunto de datos de ejemplo se obtuvo a partir de información disponible públicamente y solo ha de usarse con fines de pruebas.</span><span class="sxs-lookup"><span data-stu-id="fee7a-293">Note:- This sample data set is derived from publicly available information and is intended to be used for test purposes only.</span></span>

23. <span data-ttu-id="fee7a-294">Verá que la directiva DLP detecta que el cuerpo del correo contiene números IBAN y proporciona una sugerencia de directiva en la parte superior de la ventana del mensaje.</span><span class="sxs-lookup"><span data-stu-id="fee7a-294">You will see that the DLP policy recognized that body of the email contains IBANs and provides you with the policy tip at the top of the message window.</span></span>
24. <span data-ttu-id="fee7a-295">Cierre la instancia privada del explorador.</span><span class="sxs-lookup"><span data-stu-id="fee7a-295">Close the private instance of your browser.</span></span>


## <a name="phase-6-demonstrate-reporting"></a><span data-ttu-id="fee7a-296">Fase 6: Demostrar la creación de informes</span><span class="sxs-lookup"><span data-stu-id="fee7a-296">Phase 6: Demonstrate reporting</span></span>
 
<span data-ttu-id="fee7a-297">En esta fase, demostrará cómo crear un informe de Office 365 basándose en la directiva DLP configurada en la fase 5.</span><span class="sxs-lookup"><span data-stu-id="fee7a-297">In this phase, you demonstrate Office 365 reporting based on the DLP policy configured in Phase 5.</span></span>

   1. <span data-ttu-id="fee7a-298">En la pestaña Seguridad y cumplimiento del explorador, haga clic en **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-298">From the Security & Compliance tab of your browser, click **Home**.</span></span>
   2. <span data-ttu-id="fee7a-299">Haga clic en **Informes** > **Panel** > **Coincidencias de directivas DLP**.</span><span class="sxs-lookup"><span data-stu-id="fee7a-299">Click **Reports** > **Dashboard** > **DLP policy matches**.</span></span>
   3. <span data-ttu-id="fee7a-p118">La directiva DLP ayuda a detectar y proteger la información confidencial de la organización. Así, por ejemplo, en el informe se reflejará que la directiva ha detectado el documento que contiene números IBAN almacenados en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="fee7a-p118">Your DLP policy helps identify and protect organization's sensitive information. For example, in the report you will see that the policy identified the document that contains IBANs stored in SharePoint Online.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fee7a-302">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fee7a-302">See Also</span></span>

[<span data-ttu-id="fee7a-303">Information Protection de Office 365 para RGPD</span><span class="sxs-lookup"><span data-stu-id="fee7a-303">Office 365 Information Protection for GDPR</span></span>](office-365-information-protection-for-gdpr.md)

[<span data-ttu-id="fee7a-304">RGPD pata Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fee7a-304">GDPR for Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/gdpr?toc=/microsoft-365/enterprise/toc.json)

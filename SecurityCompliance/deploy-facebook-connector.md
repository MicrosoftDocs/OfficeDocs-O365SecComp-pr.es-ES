---
title: Implementar un conector para archivar datos de Facebook en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Los administradores pueden configurar un conector nativo para importar y archivar las páginas de empresa de Facebook a Office 365. Una vez que estos datos se han importado a Office 365, puede usar las características de cumplimiento, como las directivas de retención legal, búsqueda de contenido y retención, para administrar el gobierno de los datos de Facebook de la organización.
ms.openlocfilehash: d90714072bdeb609fe4af14208476bfa2f60b6d7
ms.sourcegitcommit: 63a10dc5ffa9d709fac437d3fc9e554b1bcd826f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2019
ms.locfileid: "33308327"
---
# <a name="deploy-a-connector-to-archive-facebook-data-in-office-365"></a><span data-ttu-id="4e01b-104">Implementar un conector para archivar datos de Facebook en Office 365</span><span class="sxs-lookup"><span data-stu-id="4e01b-104">Deploy a connector to archive Facebook data in Office 365</span></span>

<span data-ttu-id="4e01b-105">Este artículo contiene el proceso paso a paso para implementar un conector que usa el servicio de importación de Office 365 para importar datos de las páginas empresariales de Facebook a Office 365.</span><span class="sxs-lookup"><span data-stu-id="4e01b-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Office 365.</span></span> <span data-ttu-id="4e01b-106">Para obtener una descripción general de este proceso y una lista de los requisitos previos necesarios para implementar un conector de Facebook, consulte [usar conectores de ejemplo para archivar datos de terceros en Office 365](archive-third-party-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="4e01b-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Use sample connectors to archive third-party data in Office 365](archive-third-party-data-with-sample-connector.md).</span></span> 


## <a name="step-1-download-the-package"></a><span data-ttu-id="4e01b-107">Paso 1: descargar el paquete</span><span class="sxs-lookup"><span data-stu-id="4e01b-107">Step 1: Download the package</span></span>

<span data-ttu-id="4e01b-108">Descargue el paquete creado previamente de la sección de lanzamiento del <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>repositorio en.</span><span class="sxs-lookup"><span data-stu-id="4e01b-108">Download the prebuilt package from repository’s Release section at <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>.</span></span> <span data-ttu-id="4e01b-109">En la versión más reciente, descargue el archivo zip denominado **SampleConnector. zip**.</span><span class="sxs-lookup"><span data-stu-id="4e01b-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="4e01b-110">Este archivo comprimido se cargará en Azure en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="4e01b-110">You will upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="4e01b-111">Paso 2: crear una aplicación en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4e01b-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="4e01b-112">Vaya a <https://portal.azure.com> e inicie sesión con las credenciales de una cuenta de administrador global de Office 365.</span><span class="sxs-lookup"><span data-stu-id="4e01b-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

    ![Crear una aplicación en AAD](media/FBCimage1.png)

2. <span data-ttu-id="4e01b-114">En el panel de navegación izquierdo, haga clic en **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="4e01b-114">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![](media/FBCimage2.png)

3. <span data-ttu-id="4e01b-115">En el panel de navegación izquierdo, haga clic en **registros de aplicaciones (versión preliminar)** y, a continuación, haga clic en **nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="4e01b-115">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![](media/FBCimage3.png)

4. <span data-ttu-id="4e01b-116">Registrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4e01b-116">Register the application.</span></span> <span data-ttu-id="4e01b-117">En URI de redireccionamiento, seleccione Web en la lista desplegable tipo de <https://portal.azure.com> aplicación y, a continuación, escriba en el cuadro del URI.</span><span class="sxs-lookup"><span data-stu-id="4e01b-117">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![](media/FBCimage4.png)

5. <span data-ttu-id="4e01b-118">Copie el identificador de la **aplicación (cliente)** y el **directorio (inquilino)** y guárdelos en un archivo de texto u otra ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="4e01b-118">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="4e01b-119">Deberá usar estos identificadores en pasos posteriores.</span><span class="sxs-lookup"><span data-stu-id="4e01b-119">You’ll use these IDs in later steps.</span></span>

   ![](media/FBCimage5.png)

6. <span data-ttu-id="4e01b-120">Vaya a **certificados & secretos para la nueva aplicación.**</span><span class="sxs-lookup"><span data-stu-id="4e01b-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![](media/FBCimage6.png)

7. <span data-ttu-id="4e01b-121">Haga clic en **nuevo secreto de cliente**</span><span class="sxs-lookup"><span data-stu-id="4e01b-121">Click **New client secret**</span></span>

   ![](media/FBCimage7.png)

8. <span data-ttu-id="4e01b-122">Cree un secreto nuevo.</span><span class="sxs-lookup"><span data-stu-id="4e01b-122">Create a new secret.</span></span> <span data-ttu-id="4e01b-123">En el cuadro Descripción, escriba el secreto y, a continuación, elija un período de expiración.</span><span class="sxs-lookup"><span data-stu-id="4e01b-123">In the description box, type the secret and then choose an expiration period.</span></span> 

    ![](media/FBCimage8.png)

9. <span data-ttu-id="4e01b-124">Copie el valor del secreto y guárdelo en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="4e01b-124">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="4e01b-125">Este es el secreto de la aplicación de AAD que usará en pasos posteriores.</span><span class="sxs-lookup"><span data-stu-id="4e01b-125">This is the AAD application secret that you will use in later steps.</span></span>

   ![](media/FBCimage9.png)

10. <span data-ttu-id="4e01b-126">Vaya al **manifiesto** y copie identifieruris a (que también se denomina el URI de la aplicación AAD), tal y como se resalta en la siguiente captura de pantalla.</span><span class="sxs-lookup"><span data-stu-id="4e01b-126">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="4e01b-127">Copie el URI de la aplicación de AAD en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="4e01b-127">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="4e01b-128">Lo usará en el paso 6.</span><span class="sxs-lookup"><span data-stu-id="4e01b-128">You’ll use it in Step 6.</span></span>

   ![](media/FBCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="4e01b-129">Paso 3: crear una cuenta de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="4e01b-129">Step 3: Create an Azure storage account</span></span>

1. <span data-ttu-id="4e01b-130">Vaya a la Página principal de Azure de su organización.</span><span class="sxs-lookup"><span data-stu-id="4e01b-130">Go to the Azure home page for your organization.</span></span>

    ![](media/FBCimage11.png)

2. <span data-ttu-id="4e01b-131">Haga clic en **crear un recurso** y escriba la **cuenta de almacenamiento** en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4e01b-131">Click **Create a resource** and they type **storage account** in the search box.</span></span>

    ![](media/FBCimage12.png)

3. <span data-ttu-id="4e01b-132">Haga clic en **almacenamiento**y, a continuación, en **cuenta de almacenamiento**.</span><span class="sxs-lookup"><span data-stu-id="4e01b-132">Click **Storage**, and then click **Storage account**.</span></span>

    ![](media/FBCimage13.png)

4. <span data-ttu-id="4e01b-133">En la página **crear cuenta de almacenamiento** , en el cuadro suscripción, seleccione **pay-as-go** o **Free Trial** en función del tipo de suscripción de Azure que tenga.</span><span class="sxs-lookup"><span data-stu-id="4e01b-133">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> <span data-ttu-id="4e01b-134">A continuación, seleccione o cree un grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="4e01b-134">Then select or create a resource group.</span></span>

    ![](media/FBCimage14.png)

5. <span data-ttu-id="4e01b-135">Escriba un nombre para la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="4e01b-135">Type a name for the storage account.</span></span>

    ![](media/FBCimage15.png)

6. <span data-ttu-id="4e01b-136">Revise y, a continuación, haga clic en **crear** para crear la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="4e01b-136">Review and then click **Create** to create the storage account.</span></span>

    ![](media/FBCimage16.png)

7. <span data-ttu-id="4e01b-137">Tras unos minutos, haga clic en **Actualizar** y, a continuación, haga clic en **ir a recurso** para navegar a la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="4e01b-137">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

    ![](media/FBCimage17.png)

8. <span data-ttu-id="4e01b-138">Haga clic en **teclas de acceso** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="4e01b-138">Click **Access keys** in the left navigation pane.</span></span>

    ![](media/FBCimage18.png)

9. <span data-ttu-id="4e01b-139">Copiar una **cadena de conexión** y guardarla en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="4e01b-139">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="4e01b-140">Para crear un recurso de aplicación Web, deberá usar esto.</span><span class="sxs-lookup"><span data-stu-id="4e01b-140">You’ll use this when creating a web app resource.</span></span>

    ![](media/FBCimage19.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="4e01b-141">Paso 4: crear un nuevo recurso de aplicación web en Azure</span><span class="sxs-lookup"><span data-stu-id="4e01b-141">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="4e01b-142">En la página **principal** de Azure portal, haga clic en **crear una \> aplicación \> Web de todos los recursos**.</span><span class="sxs-lookup"><span data-stu-id="4e01b-142">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="4e01b-143">En la página **aplicación web** , haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="4e01b-143">On the **Web app** page, click **Create**.</span></span> 

   ![](media/FBCimage20.png)

2. <span data-ttu-id="4e01b-144">ReLlene los detalles (como se muestra a continuación) y, a continuación, cree la aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="4e01b-144">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="4e01b-145">Tenga en cuenta que el nombre que escriba en el cuadro Nombre de la **aplicación** se usará para crear la dirección URL de Azure App Service; por ejemplo FBconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="4e01b-145">Note that the name that you enter in the **App name** box will be used to create the Azure app service URL; for example fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage21.png)

3. <span data-ttu-id="4e01b-146">Vaya al recurso de la aplicación web que acaba de crear y haga clic en configuración de la **aplicación** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="4e01b-146">Go to the newly created web app resource, click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="4e01b-147">En configuración de la aplicación, haga clic en Agregar nuevo valor y agregue las tres opciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="4e01b-147">Under Application settings, click Add new setting and add the following three settings.</span></span> <span data-ttu-id="4e01b-148">Use los valores (que copió en el archivo de texto de los pasos anteriores):</span><span class="sxs-lookup"><span data-stu-id="4e01b-148">Use the values (that you copied to the text file from the previous steps):</span></span> 

    - <span data-ttu-id="4e01b-149">**APISecretKey** : puede escribir cualquier valor como secreto.</span><span class="sxs-lookup"><span data-stu-id="4e01b-149">**APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="4e01b-150">Se usará para acceder a la aplicación web del conector en el paso 7.</span><span class="sxs-lookup"><span data-stu-id="4e01b-150">This will be used to access the connector web app in Step 7.</span></span>

    - <span data-ttu-id="4e01b-151">**StorageAccountConnectionString** : el URI de la cadena de conexión que copió después de crear la cuenta de almacenamiento de Azure en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="4e01b-151">**StorageAccountConnectionString** – The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    - <span data-ttu-id="4e01b-152">**tenantId** : el identificador de inquilino de su organización de Office 365 que copió después de crear la aplicación de conector de Facebook en Azure Active Directory en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="4e01b-152">**tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 2.</span></span>

    ![](media/FBCimage22.png)

4. <span data-ttu-id="4e01b-153">En **Configuración general**, haga clic **en** junto a **AlwaysOn**.</span><span class="sxs-lookup"><span data-stu-id="4e01b-153">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="4e01b-154">Haga clic en **Guardar** en la parte superior de la página para guardar la configuración de la plicada.</span><span class="sxs-lookup"><span data-stu-id="4e01b-154">Click **Save** at the top of the page to save applicaton settings.</span></span>

   ![](media/FBCimage23.png)

5. <span data-ttu-id="4e01b-155">El último paso consiste en cargar el código fuente de la aplicación conector a Azure que ha descargado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="4e01b-155">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="4e01b-156">En un explorador Web, vaya a https://<AzureAppResourceName>. scm.azurewebsites.net/ZipDeployUi.</span><span class="sxs-lookup"><span data-stu-id="4e01b-156">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="4e01b-157">Por ejemplo, si el nombre del recurso de la aplicación de Azure (que se menciona en el paso 2 de esta sección) es **FBconnector**, entonces tendría https://fbconnector.scm.azurewebsites.net/ZipDeployUique hacerlo.</span><span class="sxs-lookup"><span data-stu-id="4e01b-157">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **fbconnector**, then you would go to https://fbconnector.scm.azurewebsites.net/ZipDeployUi.</span></span> 

6. <span data-ttu-id="4e01b-158">Arrastre y coloque el SampleConnector. zip (descargado en el paso 1) en esta página.</span><span class="sxs-lookup"><span data-stu-id="4e01b-158">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="4e01b-159">Una vez que se cargan los archivos y la implementación se realiza correctamente, la página será similar a la siguiente captura de pantalla.</span><span class="sxs-lookup"><span data-stu-id="4e01b-159">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot.</span></span>

   ![](media/FBCimage24.png)

## <a name="step-5-register-the-facebook-app"></a><span data-ttu-id="4e01b-160">Paso 5: registrar la aplicación de Facebook</span><span class="sxs-lookup"><span data-stu-id="4e01b-160">Step 5: Register the Facebook app</span></span>

1. <span data-ttu-id="4e01b-161">Vaya a <https://developers.facebook.com> , inicie sesión con las credenciales de la cuenta de las páginas de empresa de Facebook de su organización y, a continuación, haga clic en **Agregar nueva aplicación**.</span><span class="sxs-lookup"><span data-stu-id="4e01b-161">Go to <https://developers.facebook.com> , log in using the credentials for the account for your organization’s Facebook Business pages, and then click **Add New App**.</span></span>

   ![](media/FBCimage25.png)

2. <span data-ttu-id="4e01b-162">Cree un nuevo identificador de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4e01b-162">Create a new app ID.</span></span>

   ![](media/FBCimage26.png)

3. <span data-ttu-id="4e01b-163">En el panel de navegación izquierdo, haga clic en **Agregar productos** y, a continuación, haga clic en **configurar** en la ventana de **Inicio de sesión de Facebook** .</span><span class="sxs-lookup"><span data-stu-id="4e01b-163">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![](media/FBCimage27.png)

4. <span data-ttu-id="4e01b-164">En la página integrar inicio de sesión de Facebook, haga clic en **Web**.</span><span class="sxs-lookup"><span data-stu-id="4e01b-164">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![](media/FBCimage28.png)

5. <span data-ttu-id="4e01b-165">Agregue la dirección URL de Azure App Service; por ejemplo https://fbconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="4e01b-165">Add the Azure app service URL; for example https://fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage29.png)

6. <span data-ttu-id="4e01b-166">Complete la sección QuickStart de la configuración de inicio de sesión de Facebook.</span><span class="sxs-lookup"><span data-stu-id="4e01b-166">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![](media/FBCimage30.png)

7. <span data-ttu-id="4e01b-167">En el panel de navegación izquierdo, en **Inicio de sesión de Facebook**, haga clic en **configuración**y agregue el URI de redireccionamiento de OAuth en el cuadro URI de redireccionamiento **válido de OAuth** ; Use el formato \*\* \<connectorserviceuri>/views/FacebookOAuth\*\*, donde el valor de connectorserviceuri es la dirección URL de Azure App Service para su organización; por ejemplo https://fbconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="4e01b-167">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box; use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example https://fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage31.png)

8. <span data-ttu-id="4e01b-168">En el panel de navegación izquierdo, haga clic en **Agregar productos** y, a continuación, en webhooks **.**</span><span class="sxs-lookup"><span data-stu-id="4e01b-168">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="4e01b-169">En el menú desplegable **Página** , haga clic en **Página**.</span><span class="sxs-lookup"><span data-stu-id="4e01b-169">In the **Page** pull-down menu, click **Page**.</span></span> 

   ![](media/FBCimage32.png)

9. <span data-ttu-id="4e01b-170">Agregue la dirección URL de devolución de llamada de webhook y agregue un token de comprobación.</span><span class="sxs-lookup"><span data-stu-id="4e01b-170">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="4e01b-171">El formato de la dirección URL de devolución de llamada, use el formato \*\* <connectorserviceuri>/API/FbPageWebhook\*\*, donde el valor de connectorserviceuri es la dirección URL de Azure App Service para su organización; por ejemplo https://fbconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="4e01b-171">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example https://fbconnector.azurewebsites.net.</span></span> 

    <span data-ttu-id="4e01b-172">El token de comprobación debe ser similar a una contraseña segura.</span><span class="sxs-lookup"><span data-stu-id="4e01b-172">The verify token should similar to a strong password.</span></span> <span data-ttu-id="4e01b-173">Copie el token de comprobación en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="4e01b-173">Copy the verify token to a text file or other storage location.</span></span>

     ![](media/FBCimage33.png)

10. <span data-ttu-id="4e01b-174">Pruebe y suscríbase al extremo para la fuente.</span><span class="sxs-lookup"><span data-stu-id="4e01b-174">Test and subscribe to the endpoint for feed.</span></span>

    ![](media/FBCimage34.png)

11. <span data-ttu-id="4e01b-175">Agregue una dirección URL de privacidad, un icono de aplicación y un uso empresarial.</span><span class="sxs-lookup"><span data-stu-id="4e01b-175">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="4e01b-176">Además, copie el identificador de aplicación y el secreto de aplicación en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="4e01b-176">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![](media/FBCimage35.png)

12. <span data-ttu-id="4e01b-177">Hacer que la aplicación sea pública.</span><span class="sxs-lookup"><span data-stu-id="4e01b-177">Make the app public.</span></span>

    ![](media/FBCimage36.png)

13. <span data-ttu-id="4e01b-178">Agregue un usuario al rol de administrador o de evaluador.</span><span class="sxs-lookup"><span data-stu-id="4e01b-178">Add user to the admin or tester role.</span></span>

    ![](media/FBCimage37.png)

14. <span data-ttu-id="4e01b-179">Agregue el permiso de **acceso a contenido público** de la página.</span><span class="sxs-lookup"><span data-stu-id="4e01b-179">Add the **Page Public Content Access** permission.</span></span>

    ![](media/FBCimage38.png)

15. <span data-ttu-id="4e01b-180">Permiso agregar páginas de administración.</span><span class="sxs-lookup"><span data-stu-id="4e01b-180">Add Manage Pages permission.</span></span>

    ![](media/FBCimage39.png)

16. <span data-ttu-id="4e01b-181">Obtenga la aplicación revisada por Facebook.</span><span class="sxs-lookup"><span data-stu-id="4e01b-181">Get the application reviewed by Facebook.</span></span>

    ![](media/FBCimage40.png)

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="4e01b-182">Paso 6: configurar la aplicación web del conector</span><span class="sxs-lookup"><span data-stu-id="4e01b-182">Step 6: Configure the connector web app</span></span>

1. <span data-ttu-id="4e01b-183">Vaya a https://\<AzureAppResourceName>. azurewebsites. net (donde AzureAppResourceName es el nombre del recurso de la aplicación de Azure que ha nombrado en el paso 4), por ejemplo, si el nombre es https://fbconnector.azurewebsites.net **FBconnector**, vaya a.</span><span class="sxs-lookup"><span data-stu-id="4e01b-183">Go to https://\<AzureAppResourceName>.azurewebsites.net (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4) For example, if the name is **fbconnector**, go to https://fbconnector.azurewebsites.net.</span></span> <span data-ttu-id="4e01b-184">La Página principal de la aplicación será similar a la siguiente captura de pantalla.</span><span class="sxs-lookup"><span data-stu-id="4e01b-184">The home page of the app will look like the following screenshot.</span></span>


  ![](media/FBCimage41.png)

2. <span data-ttu-id="4e01b-185">Haga clic en **configurar** para mostrar una página de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="4e01b-185">Click **Configure** to display a sign in page.</span></span>
 
   ![](media/FBCimage42.png)

3. <span data-ttu-id="4e01b-186">En el cuadro identificador de inquilino, escriba o pegue el identificador de inquilino (que obtuvo en el paso 2).</span><span class="sxs-lookup"><span data-stu-id="4e01b-186">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="4e01b-187">En el cuadro contraseña, escriba o pegue el APISecretKey (que obtuvo en el paso 2) y, a continuación, haga clic en **establecer valores de configuración** para mostrar la página Detalles de la **configuración** .</span><span class="sxs-lookup"><span data-stu-id="4e01b-187">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

    ![](media/FBCimage43.png)


4. <span data-ttu-id="4e01b-188">En **detalles de configuración**, especifique las siguientes opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="4e01b-188">Under **Configuration Details**, enter the following configuration settings</span></span> 

   - <span data-ttu-id="4e01b-189">**Identificador** de la aplicación de Facebook: el identificador de la aplicación de Facebook que obtuvo en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="4e01b-189">**Facebook application ID** - The app ID for the Facebook application that you obtained in Step 5.</span></span>
   - <span data-ttu-id="4e01b-190">**Secreto** de la aplicación de Facebook: el secreto de la aplicación de Facebook que obtuvo en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="4e01b-190">**Facebook application secret** - The app secret for the Facebook application that you obtained in Step 5.</span></span>
   - <span data-ttu-id="4e01b-191">**Token de comprobación** de webhooks de Facebook: el token de comprobación que ha creado en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="4e01b-191">**Facebook webhooks verify token** - The verify token that you created in Step 5.</span></span>
   - <span data-ttu-id="4e01b-192">**Identificador** de la aplicación de AAD: el identificador de aplicación de la aplicación de Azure Active Directory que creó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="4e01b-192">**AAD application ID** - The application ID for the Azure Active Directory app that you created in Step 2</span></span>
   - <span data-ttu-id="4e01b-193">**Secreto de la aplicación AAD** : el valor del secreto APISecretKey que creó en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="4e01b-193">**AAD application secret** - The value for the APISecretKey secret that you created in Step 4.</span></span>
   - <span data-ttu-id="4e01b-194">**URI de la aplicación AAD** : el URI de la aplicación AAD obtenido en el paso 2; por ejemplo, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.</span><span class="sxs-lookup"><span data-stu-id="4e01b-194">**AAD application Uri** - The AAD application Uri obtained in Step 2; for example, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.</span></span>
   - <span data-ttu-id="4e01b-195">**Clave de instrumentación de App Insights** : Deje este cuadro en blanco.</span><span class="sxs-lookup"><span data-stu-id="4e01b-195">**App insights instrumentation key** - Leave this box blank.</span></span>

5. <span data-ttu-id="4e01b-196">Haga clic en **Guardar** para guardar la configuración del conector.</span><span class="sxs-lookup"><span data-stu-id="4e01b-196">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="4e01b-197">Paso 7: configurar un conector personalizado en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="4e01b-197">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

1. <span data-ttu-id="4e01b-198">Vaya a <https://protection.office.com> y, a continuación, haga clic en **datos de terceros de importación \> \> de gobierno de datos**.</span><span class="sxs-lookup"><span data-stu-id="4e01b-198">Go to <https://protection.office.com> and then click **Data governance \> Import \> Archive third-party data**.</span></span>

   ![](media/FBCimage44.png)

2.  <span data-ttu-id="4e01b-199">Haga clic en **Agregar un conector** y, a continuación, en **personalizado**.</span><span class="sxs-lookup"><span data-stu-id="4e01b-199">Click **Add a connector** and then click **Custom**.</span></span>

    ![](media/FBCimage46.png)

3.  <span data-ttu-id="4e01b-200">En la página **Agregar aplicación de conector** , escriba la siguiente información y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4e01b-200">On the **Add Connector App** page, enter the following information and then click **Next**.</span></span>

    - <span data-ttu-id="4e01b-201">En el primer cuadro, escriba un nombre para el conector, como **Facebook**.</span><span class="sxs-lookup"><span data-stu-id="4e01b-201">In the first box, type a name for the connector, such as **Facebook**.</span></span>
    - <span data-ttu-id="4e01b-202">En el segundo cuadro, escriba o pegue el valor de APISecretKey que agregó en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="4e01b-202">In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    - <span data-ttu-id="4e01b-203">En el tercer cuadro, escriba pegar la dirección URL de Azure App Service; por ejemplo **https://fbconnector.azurewebsites.net**.</span><span class="sxs-lookup"><span data-stu-id="4e01b-203">In the third box, type of paste the Azure app service URL; for example **https://fbconnector.azurewebsites.net**.</span></span>
    
    ![](media/FBCimage47.png)

4.  <span data-ttu-id="4e01b-204">Haga clic en **iniciar sesión con la aplicación conector**.</span><span class="sxs-lookup"><span data-stu-id="4e01b-204">Click **Login with Connector App**.</span></span>

    ![](media/FBCimage45.png)

5. <span data-ttu-id="4e01b-205">Escriba o pegue el APISecretKey de nuevo y, a continuación, haga clic en **iniciar sesión en el servicio de conector**.</span><span class="sxs-lookup"><span data-stu-id="4e01b-205">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![](media/FBCimage48.png)


6. <span data-ttu-id="4e01b-206">Haga clic en **iniciar sesión con Facebook.**</span><span class="sxs-lookup"><span data-stu-id="4e01b-206">Click **Login with Facebook.**</span></span>

   ![](media/FBCimage49.png)

7. <span data-ttu-id="4e01b-207">En la página **iniciar sesión en Facebook** , inicie sesión con las credenciales de la cuenta de las páginas de empresa de Facebook de su organización.</span><span class="sxs-lookup"><span data-stu-id="4e01b-207">On the **Log in to Facebook** page, log in using the credentials for the account for your organization’s Facebook Business pages.</span></span> <span data-ttu-id="4e01b-208">Asegúrese de que la cuenta de Facebook a la que ha iniciado sesión tenga asignado el rol de administrador de las páginas empresariales de Facebook de su organización.</span><span class="sxs-lookup"><span data-stu-id="4e01b-208">Make sure the Facebook account you logged in to is assigned the admin role for your organization’s Facebook Business pages</span></span>

   ![](media/FBCimage50.png)

8. <span data-ttu-id="4e01b-209">Haga clic en **seleccionar páginas** para elegir las páginas de negocio de su organización que desea archivar en Office 365.</span><span class="sxs-lookup"><span data-stu-id="4e01b-209">Click **Select Pages** to choose your organization’s business pages that you want to archive in Office 365.</span></span>

   ![](media/FBCimage51.png)

9. <span data-ttu-id="4e01b-210">Se muestra una lista de las páginas de negocio administradas por la cuenta de Facebook en la que inició sesión.</span><span class="sxs-lookup"><span data-stu-id="4e01b-210">A list of the Business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="4e01b-211">Seleccione la página que desea archivar y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4e01b-211">Select the page to archive and then click **Save**.</span></span>

    ![](media/FBCimage52.png)

10. <span data-ttu-id="4e01b-212">Haga clic en **Finalizar** para salir de la instalación de la aplicación del servicio conector.</span><span class="sxs-lookup"><span data-stu-id="4e01b-212">Click **Finish** to exit the setup of the connector service app.</span></span>

    ![](media/FBCimage53.png)

11. <span data-ttu-id="4e01b-213">En la página **Establecer filtros** , puede aplicar un filtro para importar (y archivar) los elementos que tengan una antigüedad determinada.</span><span class="sxs-lookup"><span data-stu-id="4e01b-213">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="4e01b-214">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4e01b-214">Click **Next**.</span></span>

    ![](media/FBCimage54.png)

12. <span data-ttu-id="4e01b-215">En la página **establecer cuenta de almacenamiento** , seleccione el buzón de Office 365 en el que se importarán los elementos de las páginas de la empresa de Facebook que seleccionó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4e01b-215">On the **Set Storage Account** page, select the Office 365 mailbox that the items from the Facebook Business pages that you previously selected will be imported to.</span></span>

    ![](media/FBCimage55.png)

13. <span data-ttu-id="4e01b-216">Revise la configuración y, a continuación, haga clic en **Finalizar** para completar la configuración del conector en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="4e01b-216">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![](media/FBCimage56.png)

14. <span data-ttu-id="4e01b-217">Vaya a la página **archivar datos de terceros** para ver el progreso del proceso de importación.</span><span class="sxs-lookup"><span data-stu-id="4e01b-217">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![](media/FBCimage58.png)

---
title: Asignar permisos de exhibición de documentos electrónicos a sitios de OneDrive para la Empresa
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/27/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 422858ff-917b-46d4-9e5b-3397f60eee4d
description: Puede usar el centro de exhibición de documentos electrónicos en SharePoint Online para buscar todos los OneDrive para sitios de profesionales de la organización para ciertas palabras clave, la información confidencial y otros criterios de búsqueda. Cada usuario de la organización es el propietario de su OneDrive para el sitio empresarial, que se encuentra en la colección de sitios con nombre de https://domain-my.sharepoint.com. De forma predeterminada, un administrador global de Office 365 o un administrador de cumplimiento no se puede usar el centro de exhibición de documentos electrónicos en SharePoint Online para buscar cualquier OneDrive para sitios de profesionales. Para buscar un OneDrive para sitio empresarial, los administradores o administradores de cumplimiento debe ser un administrador de colección de sitios para que OneDrive para el sitio de negocio.
ms.openlocfilehash: 48f84dfe21f0f99913ba2c27123d6c0e1f8bc03f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536218"
---
# <a name="assign-ediscovery-permissions-to-onedrive-for-business-sites"></a><span data-ttu-id="7ea0f-106">Asignar permisos de exhibición de documentos electrónicos a sitios de OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="7ea0f-106">Assign eDiscovery permissions to OneDrive for Business sites</span></span>

<span data-ttu-id="7ea0f-p102">Puede usar el centro de exhibición de documentos electrónicos en SharePoint Online para buscar todos los OneDrive para sitios de profesionales de la organización para ciertas palabras clave, la información confidencial y otros criterios de búsqueda. Cada usuario de la organización es el propietario de su OneDrive para el sitio empresarial, que se encuentra en la colección de sitios con nombre de https://domain-my.sharepoint.com. De forma predeterminada, un administrador global de Office 365 o un administrador de cumplimiento no se puede usar el centro de exhibición de documentos electrónicos en SharePoint Online para buscar cualquier OneDrive para sitios de profesionales. Para buscar un OneDrive para sitio empresarial, los administradores o administradores de cumplimiento debe ser un administrador de colección de sitios para que OneDrive para el sitio de negocio.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-p102">You can use the eDiscovery Center in SharePoint Online to search all OneDrive for Business sites in your organization for certain keywords, sensitive information, and other search criteria. Each user in your organization is the owner of their OneDrive for Business site, which is located in the site collection named https://domain-my.sharepoint.com. By default, an Office 365 global administrator or compliance manager can't use the eDiscovery Center in SharePoint Online to search any OneDrive for Business sites. To search a OneDrive for Business site, administrators or compliance managers must be a site collection administrator for that OneDrive for Business site.</span></span> 
  
<span data-ttu-id="7ea0f-111">En este artículo le guiará por los pasos necesarios para hacer que un administrador o cumplimiento Administrador de un administrador de colección de sitios para cada OneDrive para el sitio de negocio en la organización.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-111">This article guides you through the steps to make an administrator or compliance manager a site collection administrator for every OneDrive for Business site in your organization.</span></span> 
  
<span data-ttu-id="7ea0f-112">Vea la sección [obtener más información](#more-information) para obtener sugerencias sobre el uso de la secuencia de comandos en este artículo, incluida la revisión de la secuencia de comandos en el paso 3 para quitar un usuario como un administrador de colección de sitios de OneDrive para sitios de negocio.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-112">See the [More information](#more-information) section for tips about using the script in this article, including revising the script in Step 3 to remove a user as a site collection administrator from OneDrive for Business sites.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="7ea0f-113">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="7ea0f-113">Before you begin</span></span>

- <span data-ttu-id="7ea0f-p103">Instale el shell de administración de SharePoint Online. Para obtener más información, vea [Configurar el entorno de Windows PowerShell del shell de administración de SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=286318).</span><span class="sxs-lookup"><span data-stu-id="7ea0f-p103">Install the SharePoint Online Management Shell. For information, see [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318).</span></span>
    
- <span data-ttu-id="7ea0f-116">Ejecute la secuencia de comandos en el paso 3 cada vez que desea asignar a un usuario como un administrador de colección de sitios a cualquier OneDrive para sitios de profesionales de la organización.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-116">Run the script in Step 3 each time you want to assign a user as a site collection administrator to any OneDrive for Business sites in your organization.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="7ea0f-p104">Un administrador o cumplimiento administrador que es un administrador de colección de sitios para OneDrive para sitios de profesionales pueden abrir OneDrive para los usuarios empresariales para bibliotecas de documentos y realizar las mismas tareas que el propietario. Es importante para el control y el monitor que se haya asignado permisos de exhibición de documentos electrónicos a OneDrive para sitios de profesionales de la organización.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-p104">An administrator or compliance manager who is a site collection administrator for OneDrive for Business sites can open users' OneDrive for Business document libraries and perform the same tasks as the owner. It's important to control and monitor who has been assigned eDiscovery permissions to OneDrive for Business sites in your organization.</span></span> 
  
- <span data-ttu-id="7ea0f-p105">El script de ejemplo proporcionado en este artículo no es compatible con ningún servicio o programa de soporte estándar de Microsoft. El script de ejemplo se proporciona tal cual sin garantía de ningún tipo. Microsoft renuncia a todas las garantías implícitas incluidas, sin limitación, cualquier las garantías implícitas de comerciabilidad o de idoneidad para un fin determinado. Todo el riesgo que pueda surgir por el uso o el rendimiento de la secuencia de comandos de ejemplo y documentación permanece con usted. En ningún caso Microsoft, sus autores o cualquier otro implicado en la creación, producción o entrega de la secuencia de comandos serán responsables de los daños índole (incluidos, pero sin limitarse a, daños por pérdida de beneficios empresariales, interrupción del negocio, pérdida de información de la empresa, o en otras pérdidas de carácter económico) derivado del uso o la incapacidad de usar el script de ejemplo o la documentación, aunque Microsoft haya sido notificado de la posibilidad de dichos daños.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-p105">The sample script provided in this article isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the script be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample script or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-collect-a-list-of-all-onedrive-for-business-sites"></a><span data-ttu-id="7ea0f-124">Paso 1: Recopilar una lista de todos los OneDrive para sitios profesionales</span><span class="sxs-lookup"><span data-stu-id="7ea0f-124">Step 1: Collect a list of all OneDrive for Business sites</span></span>

<span data-ttu-id="7ea0f-p106">El primer paso es crear una lista de todos los OneDrive para sitios de profesionales de la organización. Para obtener instrucciones, vea [crear una lista de todas las ubicaciones de OneDrive en la organización](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). Esta secuencia de comandos en este artículo, crea un archivo de texto que contiene una lista de todos los sitios de OneDrive. La secuencia de comandos que se ejecutan en el paso 3, asigna a un usuario especificado como un administrador de colección de sitios a cada OneDrive para el sitio de negocio que aparecen en el archivo de texto que se crea en este paso. El texto siguiente proporciona un ejemplo de cómo se debe aplicar el formato de la lista de sitios de este archivo. Puede quitar sitios de este archivo si es necesario.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-p106">The first step is to create a list of all OneDrive for Business sites in your organization. For instructions, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). This script in this article creates a text file that contains a list of all OneDrive sites. The script that you run in Step 3 assigns a specified user as a site collection administrator to each OneDrive for Business site listed in the text file that's created in this step. The following text provides an example of how the list of sites in this file should be formatted. You can remove sites from this file if necessary.</span></span>

```
/personal/annb_contoso_onmicrosoft_com/
/personal/carolt_contoso_onmicrosoft_com/
/personal/esterv_contoso_onmicrosoft_com/
/personal/hollyh_contoso_onmicrosoft_com/
/personal/jeffl_contoso_onmicrosoft_com/
/personal/joeh_contoso_onmicrosoft_com/
/personal/kaia_contoso_onmicrosoft_com/
```

## <a name="step-2-connect-sharepoint-online-management-shell-to-your-organization"></a><span data-ttu-id="7ea0f-131">Paso 2: Conectarse a la consola de administración en línea de SharePoint a la organización</span><span class="sxs-lookup"><span data-stu-id="7ea0f-131">Step 2: Connect SharePoint Online Management Shell to your organization</span></span>

1. <span data-ttu-id="7ea0f-132">En el equipo local, abra el shell de administración de SharePoint Online y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="7ea0f-132">On your local computer, open the SharePoint Online Management Shell, and run the following command:</span></span>

    ```
    $credentials = Get-Credential
    ```

2. <span data-ttu-id="7ea0f-133">En el cuadro de diálogo **Solicitud de credenciales para Windows PowerShell**, escriba el nombre de usuario y la contraseña para su cuenta de administrador global de Office 365 y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-133">In the **Windows PowerShell Credential Request** dialog box, type the user name and password for your Office 365 global administrator account, and then click **OK**.</span></span>
    
3. <span data-ttu-id="7ea0f-134">Ejecute el siguiente comando para conectar el shell a la organización de SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="7ea0f-134">Run the following command to connect the Shell to your SharePoint Online organization:</span></span>
    
    ```
    Connect-SPOService -Url https://<your organization name>-admin.sharepoint.com -credential $credentials
    ```
   
4. <span data-ttu-id="7ea0f-135">Para verificar que se ha conectado a su organización de SharePoint Online, ejecute el comando siguiente para obtener una lista de todos los sitios de su organización:</span><span class="sxs-lookup"><span data-stu-id="7ea0f-135">To verify that you are connected to your SharePoint Online organization, run the following command to get a list of all the sites in your organization:</span></span>
    
    ```
    Get-SPOSite
    ```

## <a name="step-3-assign-a-user-as-a-site-collection-administrator-to-onedrive-for-business-sites"></a><span data-ttu-id="7ea0f-136">Paso 3: Asignar un usuario como administrador de una colección de sitios de un sitio de OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="7ea0f-136">Step 3: Assign a user as a site collection administrator to OneDrive for Business sites</span></span>

<span data-ttu-id="7ea0f-p107">El siguiente paso es ejecutar un script que se asigna a un usuario especificado como un administrador de colección de sitios en cada OneDrive para el sitio de negocio de la organización. Esta secuencia de comandos utiliza la lista de OneDrive para los sitios de negocio que creó en el paso 1. Como se señaló anteriormente, tendrá que ejecutar este script cada vez que se desea asignar a un usuario como un administrador de colección de sitios a OneDrive para sitios de negocio.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-p107">The next step is to run a script that assigns a specified user as a site collection administrator in every OneDrive for Business site in your organization. This script uses the list of OneDrive for Business sites that you created in Step 1. As previously stated, you have to run this script each time that you want to assign a user as a site collection administrator to OneDrive for Business sites.</span></span>
  
1. <span data-ttu-id="7ea0f-p108">Pegue el texto siguiente en un documento de Bloc de notas. Por ejemplo, podría guardarlo en un documento con el nombre OD4BAssignSCA.txt.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-p108">Save the following text to a text file. For example, you could save it to a file named OD4BAssignSCA.txt.</span></span>

    ```
    # Start logging, so if this script fails, you can look at the last successful change,
    # remove any OneDrive for Business paths that worked it from the input file, and then rerun the script.

    Start-Transcript

    # URL for your organization's SPO admin service

    $AdminURI = "https://<your organization name>-admin.sharepoint.com"

    # User account for an Office 365 global admin in your organization

    $AdminAccount = "<global admin account>"

    # Compliance manager to be made site collection admin on each MySite

    $eDiscoveryUser = "<eDiscovery user account>"

    # URL for your tenant's MySite domain

    $MySitePrefix = "https://<your organization name>-my.sharepoint.com"

    # Where should we read the list of MySites?
    # This file should contain partial MySite paths formatted as follows, one per line; for example
    # /personal/junminh_contoso_onmicrosoft_com/

    $MySiteListFile = 'C:\Users\<youralias>\Desktop\ListOfMysites.txt'

    # Begin by connecting to the service
    Connect-SPOService -Url $AdminURI -Credential $AdminAccount

    # Make a reader for our list of MySites

    $reader = [System.IO.File]::OpenText($MySiteListFile)

    try {
      for(;;) {

    # Read a line
          $line = $reader.ReadLine()
    # Stop if it doesn't exist
          if ($line -eq $null) { break }

    # Turn the line into a complete SharePoint site path by merging $MySitePrefix
    # Formatted like this: "https://contoso-my.sharepoint.com"
    # ...with each partial MySite path in the file, formatted like this:
    # "/personal/junminh_contoso_onmicrosoft_com/"

          $fullsitepath = "$MySitePrefix$line"

    Write-Host "Operating on $fullsitepath "

    # We need to remove the last "/" to work around an issue.
    # "/personal/junminh_contoso_onmicrosoft_com/"
    # becomes "/personal/junminh_contoso_onmicrosoft_com"

    $fullsitepath = $fullsitepath.trimend("/")

    # Make the specified eDiscovery user a site collection admin on the OneDrive for Business site
    Write-Host "Making $eDiscoveryUser a Site Collection Admin"
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $true
      }
    }
    finally {
      $reader.Close()
    }
    Write-Host "Done!"
    Stop-Transcript
    Write-Host "Log written."
    ```

2. <span data-ttu-id="7ea0f-p109">Editar las siguientes variables al principio del archivo de secuencia de comandos y utilizar información que es específica de la organización. En los ejemplos siguientes se suponen que el nombre de dominio de la organización es contoso.onmicrosoft.com. No olvide rodear los valores de las variables con comillas dobles ("").</span><span class="sxs-lookup"><span data-stu-id="7ea0f-p109">Edit the following variables in the beginning of the script file, and use information that's specific to your organization. The following examples assume that the domain name of your organization is contoso.onmicrosoft.com. Be sure to surround the values for the variables with double-quotation marks (" ").</span></span>
    
    - <span data-ttu-id="7ea0f-145">**$AdminURI** - especifica el URI para el servicio de administración de SharePoint Online, por ejemplo, `"https://contoso-admin.sharepoint.com"`.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-145">**$AdminURI** - This specifies the URI for your SharePoint Online admin service, for example,  `"https://contoso-admin.sharepoint.com"`.</span></span>
    
    - <span data-ttu-id="7ea0f-146">**$AdminAccount** - especifica una cuenta de administrador global de la organización de Office 365, por ejemplo, `"admin@contoso.onmicrosoft.com"`.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-146">**$AdminAccount** - This specifies a global administrator account in your Office 365 organization, for example,  `"admin@contoso.onmicrosoft.com"`.</span></span>
    
    - <span data-ttu-id="7ea0f-147">**$eDiscoveryUser** - especifica la cuenta de usuario de un administrador o administrador de cumplimiento que se le asignen como un administrador de colección de sitios para cada OneDrive para el sitio de negocio de la organización, por ejemplo, `"annb@contoso.onmicrosoft.com"`.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-147">**$eDiscoveryUser** - This specifies the user account of an administrator or compliance manager who will be assigned as a site collection administrator for every OneDrive for Business site in your organization, for example,  `"annb@contoso.onmicrosoft.com"`.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="7ea0f-148">Cambiar la cuenta de usuario especificada por la variable **$eDiscoveryUser** y vuelva a ejecutar la secuencia de comandos para asignar a un usuario diferente como un administrador de colección de sitios a la OneDrive para los sitios de negocio que se especificado por la variable **$MySiteListFile** .</span><span class="sxs-lookup"><span data-stu-id="7ea0f-148">Change the user account specified by the **$eDiscoveryUser** variable and re-run the script to assign a different user as a site collection administrator to the OneDrive for Business sites that are specified by the **$MySiteListFile** variable.</span></span> 
  
    - <span data-ttu-id="7ea0f-p110">**$MySitePrefix** Especifica la dirección URL de dominio de Mi sitio de la organización. Éste es el dominio que contiene la de OneDrive para sitios de profesionales de la organización, por ejemplo, `"https://contoso-my.sharepoint.com"`.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-p110">**$MySitePrefix**This specifies the URL for your organization's MySite domain. This is the domain that contains all the OneDrive for Business sites in your organization, for example,  `"https://contoso-my.sharepoint.com"`.</span></span>
    
    - <span data-ttu-id="7ea0f-p111">**$MySiteListFile** Especifica la ruta de acceso completa del archivo de texto que creó en el paso 1. Este archivo contiene una lista de OneDrive para sitios de profesionales de la organización, por ejemplo, `'C:\Users\<youralias>\Desktop\ListOfMysites.txt'`. Asegúrese de que rodee el valor de esta variable con comillas simples (' '). Tenga en cuenta que debe especificar la ubicación en la que guardó el archivo de texto para en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-p111">**$MySiteListFile**This specifies the full path of the text file that you created in Step 1. This file contains a list of OneDrive for Business sites in your organization, for example,  `'C:\Users\<youralias>\Desktop\ListOfMysites.txt'`. Be sure to surround the value for this variable with single-quotation marks (' '). Note that you should specify the location that you saved the text file to in Step 1.</span></span>
    
3. <span data-ttu-id="7ea0f-p112">Guarde el documento de Bloc de notas como un archivo de script de PowerShell cambiando el sufijo del nombre de archivo por .ps1. Por ejemplo, guarde el archivo OD4BAssignSCA.txt como OD4BAssignSCA.ps1.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-p112">Save the text file as a PowerShell script file by changing the file name suffix to .ps1. For example, save the file OD4BAssignSCA.txt as OD4BAssignSCA.ps1.</span></span>
    
4. <span data-ttu-id="7ea0f-157">En el Shell de administración de SharePoint Online, vaya a la carpeta donde se encuentre el script de PowerShell creado en el paso anterior y ejecútelo, como por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7ea0f-157">In SharePoint Online Management Shell, go to the folder that contains the PowerShell script that you created in the previous step, and then run the script, for example:</span></span>
    
    ```
    .\OD4BAssignSCA.ps1
    ```

    <span data-ttu-id="7ea0f-p113">Se le pedirá que escriba la contraseña para la cuenta de administrador que especificó en la secuencia de comandos. Si la secuencia de comandos ejecuta correctamente, el mensaje `"Making  _\<user specified by $eDiscoveryUser\>_ a Site Collection Admin"` se muestra para cada OneDrive para el sitio de negocio que aparece en el archivo de entrada especificado por **$MySiteListFile**.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-p113">You will be prompted to enter the password for the administrator account that you specified in the script. If the script runs successfully, the message `"Making  _\<user specified by $eDiscoveryUser\>_ a Site Collection Admin"` is displayed for each OneDrive for Business site that's listed in the input file specified by **$MySiteListFile**.</span></span>

## <a name="more-information"></a><span data-ttu-id="7ea0f-160">Más información</span><span class="sxs-lookup"><span data-stu-id="7ea0f-160">More information</span></span>

- <span data-ttu-id="7ea0f-p114">La secuencia de comandos que se ejecutó en el paso 3, usa el cmdlet **Set-SPOUser** para asignar al usuario especificado como un administrador de colección de sitios para cada OneDrive para la empresa que aparece en el archivo especificado por la variable **$MySiteListFile** . Si tiene una organización muy grande con miles de usuarios, tenga en cuenta lo siguiente para que sea más fácil administrar asignar permisos de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-p114">The script that you ran in Step 3 uses the **Set-SPOUser** cmdlet to assign the specified user as a site collection administrator to every OneDrive for Business that's listed in the file specified by the **$MySiteListFile** variable. If you have a very large organization with thousands of users, consider doing the following to make it easier to manage assigning eDiscovery permissions.</span></span> 
    
  - <span data-ttu-id="7ea0f-163">Edite el archivo que creó en el paso 1 que contiene la lista de OneDrive para sitios de profesionales para que incluya sólo los sitios para los usuarios son que participan en casos legales activos.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-163">Edit the file that you created in Step 1 that contains the list of OneDrive for Business sites so that it includes only the sites for users are that are involved in active legal cases.</span></span>
    
  - <span data-ttu-id="7ea0f-p115">Asignar permisos a no más de 2.500 OneDrive para sitios de profesionales por día. Por ejemplo, supongamos que tiene 10.000 OneDrive para sitios de profesionales de la organización. Se pudo crear la lista en el paso 1 para recopilar todos los sitios. A continuación, podría utilizar ese archivo para crear cuatro archivos que contienen los 2.500 usuarios. En el primer día, ejecutaría la secuencia de comandos en el paso 3 para asignar permisos a la OneDrive en primer lugar 2.500 para sitios de negocio. En el segundo día, tendría que ejecutar el script para la siguiente 2.500 OneDrive para sitios de profesionales y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-p115">Assign permissions to no more than 2,500 OneDrive for Business sites per day. For example, let's say you have 10,000 OneDrive for Business sites in your organization. You could create the list in Step 1 to collect all the sites. Then you could use that file to create four files that each contain 2,500 users. On the first day, you would run the script in Step 3 to assign permissions to the first 2,500 OneDrive for Business sites. On the second day, you would run the script for the next 2,500 OneDrive for Business sites, and so on.</span></span>
    
- <span data-ttu-id="7ea0f-p116">Mantener un registro de la OneDrive para los sitios de negocio que se han asignado permisos de exhibición de documentos electrónicos y el usuario que se ha asignado como administrador de la colección de sitios. Por ejemplo, después de asignar permisos, puede guardar el archivo de texto que contiene la lista de OneDrive para sitios profesionales y agregue una línea que identifica al usuario que se ha asignado como administrador de la colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-p116">Keep a record of the OneDrive for Business sites that were assigned eDiscovery permissions and the user who is assigned as the site collection administrator. For example, after you assign permissions, you can save the text file that contains the list of OneDrive for Business sites and add a line to it that identifies the user who is assigned as the site collection administrator.</span></span>
    
- <span data-ttu-id="7ea0f-p117">Los usuarios pueden ver la lista de administradores de colección de sitios para su OneDrive para el sitio de negocio. Debido a que los usuarios son el Administrador de colección de sitios para su propios OneDrive para el sitio de negocio, pueden quitar administradores de colección de sitios. Tenga en cuenta lo siguiente para mitigar la posibilidad de quitar el usuario que se asigna permisos de exhibición de documentos electrónicos a OneDrive para sitios de profesionales de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-p117">Users can view the list of site collection administators for their OneDrive for Business site. Because users are site collection administrator for their own OneDrive for Business site, they can remove site collection administrators. Consider doing the following to mitigate the chance of users removing the user who is assigned eDiscovery permissions to OneDrive for Business sites.</span></span>
    
  - <span data-ttu-id="7ea0f-175">Comunicar a los usuarios que para fines de cumplimiento de normas y exhibición de documentos electrónicos, un agente de cumplimiento se ha asignado como un administrador de colección de sitios a OneDrive para sitios de profesionales de la organización.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-175">Communicate to users that for eDiscovery and compliance purposes, a compliance officer has been assigned as a site collection administrator to OneDrive for Business sites in your organization.</span></span>
    
  - <span data-ttu-id="7ea0f-176">Vuelva a ejecutar la secuencia de comandos en el paso 3, si es necesario, para volver a asignar a un usuario como administrador de la colección de sitios para OneDrive para sitios de negocio.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-176">Re-run the script in Step 3, if necessary, to re-assign a user as the site collection administrator for OneDrive for Business sites.</span></span>
    
- <span data-ttu-id="7ea0f-p118">También puede utilizar la secuencia de comandos que se ejecutó en el paso 3 para quitar un usuario como administrador de la colección de sitios de OneDrive para sitios de negocio. Para quitar un usuario como un administrador de colección de sitios, debe cambiar el siguiente comando (casi al final de la secuencia de comandos) desde:</span><span class="sxs-lookup"><span data-stu-id="7ea0f-p118">You can also use the script that you ran in Step 3 to remove a user as the site collection administrator from OneDrive for Business sites. To remove a user as a site collection administrator, you have to change the following command (near the end of the script) from:</span></span> 

    ```
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $true
    ```

    <span data-ttu-id="7ea0f-179">a:</span><span class="sxs-lookup"><span data-stu-id="7ea0f-179">to:</span></span>
    
    ```
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $false
    ```

    <span data-ttu-id="7ea0f-180">También puede cambiar la línea siguiente del script de:</span><span class="sxs-lookup"><span data-stu-id="7ea0f-180">You can also change the following line in the script from:</span></span>

    ```
    "Making $eDiscoveryUser a Site Collection Admin"
    ```

    <span data-ttu-id="7ea0f-181">a:</span><span class="sxs-lookup"><span data-stu-id="7ea0f-181">to:</span></span>
    
    ```
    "Removing $eDiscoveryUser as a Site Collection Admin"
    ```

    <span data-ttu-id="7ea0f-182">Después de realizar estos cambios, guarde la secuencia de comandos con un nombre diferente, como OD4BRemoveSCA.ps1 y, a continuación, usarla para quitar un usuario como un administrador de colección de sitios de un grupo de OneDrive para sitios de negocio.</span><span class="sxs-lookup"><span data-stu-id="7ea0f-182">After you make these changes, save the script with a different name, such as OD4BRemoveSCA.ps1, and then use it to remove a user as a site collection administrator from a group of OneDrive for Business sites.</span></span>

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
# <a name="assign-ediscovery-permissions-to-onedrive-for-business-sites"></a>Asignar permisos de exhibición de documentos electrónicos a sitios de OneDrive para la Empresa

Puede usar el centro de exhibición de documentos electrónicos en SharePoint Online para buscar todos los OneDrive para sitios de profesionales de la organización para ciertas palabras clave, la información confidencial y otros criterios de búsqueda. Cada usuario de la organización es el propietario de su OneDrive para el sitio empresarial, que se encuentra en la colección de sitios con nombre de https://domain-my.sharepoint.com. De forma predeterminada, un administrador global de Office 365 o un administrador de cumplimiento no se puede usar el centro de exhibición de documentos electrónicos en SharePoint Online para buscar cualquier OneDrive para sitios de profesionales. Para buscar un OneDrive para sitio empresarial, los administradores o administradores de cumplimiento debe ser un administrador de colección de sitios para que OneDrive para el sitio de negocio. 
  
En este artículo le guiará por los pasos necesarios para hacer que un administrador o cumplimiento Administrador de un administrador de colección de sitios para cada OneDrive para el sitio de negocio en la organización. 
  
Vea la sección [obtener más información](#more-information) para obtener sugerencias sobre el uso de la secuencia de comandos en este artículo, incluida la revisión de la secuencia de comandos en el paso 3 para quitar un usuario como un administrador de colección de sitios de OneDrive para sitios de negocio. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Instale el shell de administración de SharePoint Online. Para obtener más información, vea [Configurar el entorno de Windows PowerShell del shell de administración de SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=286318).
    
- Ejecute la secuencia de comandos en el paso 3 cada vez que desea asignar a un usuario como un administrador de colección de sitios a cualquier OneDrive para sitios de profesionales de la organización. 
    
    > [!IMPORTANT]
    > Un administrador o cumplimiento administrador que es un administrador de colección de sitios para OneDrive para sitios de profesionales pueden abrir OneDrive para los usuarios empresariales para bibliotecas de documentos y realizar las mismas tareas que el propietario. Es importante para el control y el monitor que se haya asignado permisos de exhibición de documentos electrónicos a OneDrive para sitios de profesionales de la organización. 
  
- El script de ejemplo proporcionado en este artículo no es compatible con ningún servicio o programa de soporte estándar de Microsoft. El script de ejemplo se proporciona tal cual sin garantía de ningún tipo. Microsoft renuncia a todas las garantías implícitas incluidas, sin limitación, cualquier las garantías implícitas de comerciabilidad o de idoneidad para un fin determinado. Todo el riesgo que pueda surgir por el uso o el rendimiento de la secuencia de comandos de ejemplo y documentación permanece con usted. En ningún caso Microsoft, sus autores o cualquier otro implicado en la creación, producción o entrega de la secuencia de comandos serán responsables de los daños índole (incluidos, pero sin limitarse a, daños por pérdida de beneficios empresariales, interrupción del negocio, pérdida de información de la empresa, o en otras pérdidas de carácter económico) derivado del uso o la incapacidad de usar el script de ejemplo o la documentación, aunque Microsoft haya sido notificado de la posibilidad de dichos daños.
    
## <a name="step-1-collect-a-list-of-all-onedrive-for-business-sites"></a>Paso 1: Recopilar una lista de todos los OneDrive para sitios profesionales

El primer paso es crear una lista de todos los OneDrive para sitios de profesionales de la organización. Para obtener instrucciones, vea [crear una lista de todas las ubicaciones de OneDrive en la organización](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). Esta secuencia de comandos en este artículo, crea un archivo de texto que contiene una lista de todos los sitios de OneDrive. La secuencia de comandos que se ejecutan en el paso 3, asigna a un usuario especificado como un administrador de colección de sitios a cada OneDrive para el sitio de negocio que aparecen en el archivo de texto que se crea en este paso. El texto siguiente proporciona un ejemplo de cómo se debe aplicar el formato de la lista de sitios de este archivo. Puede quitar sitios de este archivo si es necesario.

```
/personal/annb_contoso_onmicrosoft_com/
/personal/carolt_contoso_onmicrosoft_com/
/personal/esterv_contoso_onmicrosoft_com/
/personal/hollyh_contoso_onmicrosoft_com/
/personal/jeffl_contoso_onmicrosoft_com/
/personal/joeh_contoso_onmicrosoft_com/
/personal/kaia_contoso_onmicrosoft_com/
```

## <a name="step-2-connect-sharepoint-online-management-shell-to-your-organization"></a>Paso 2: Conectarse a la consola de administración en línea de SharePoint a la organización

1. En el equipo local, abra el shell de administración de SharePoint Online y ejecute el siguiente comando:

    ```
    $credentials = Get-Credential
    ```

2. En el cuadro de diálogo **Solicitud de credenciales para Windows PowerShell**, escriba el nombre de usuario y la contraseña para su cuenta de administrador global de Office 365 y, a continuación, haga clic en **Aceptar**.
    
3. Ejecute el siguiente comando para conectar el shell a la organización de SharePoint Online:
    
    ```
    Connect-SPOService -Url https://<your organization name>-admin.sharepoint.com -credential $credentials
    ```
   
4. Para verificar que se ha conectado a su organización de SharePoint Online, ejecute el comando siguiente para obtener una lista de todos los sitios de su organización:
    
    ```
    Get-SPOSite
    ```

## <a name="step-3-assign-a-user-as-a-site-collection-administrator-to-onedrive-for-business-sites"></a>Paso 3: Asignar un usuario como administrador de una colección de sitios de un sitio de OneDrive para la Empresa

El siguiente paso es ejecutar un script que se asigna a un usuario especificado como un administrador de colección de sitios en cada OneDrive para el sitio de negocio de la organización. Esta secuencia de comandos utiliza la lista de OneDrive para los sitios de negocio que creó en el paso 1. Como se señaló anteriormente, tendrá que ejecutar este script cada vez que se desea asignar a un usuario como un administrador de colección de sitios a OneDrive para sitios de negocio.
  
1. Pegue el texto siguiente en un documento de Bloc de notas. Por ejemplo, podría guardarlo en un documento con el nombre OD4BAssignSCA.txt.

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

2. Editar las siguientes variables al principio del archivo de secuencia de comandos y utilizar información que es específica de la organización. En los ejemplos siguientes se suponen que el nombre de dominio de la organización es contoso.onmicrosoft.com. No olvide rodear los valores de las variables con comillas dobles ("").
    
    - **$AdminURI** - especifica el URI para el servicio de administración de SharePoint Online, por ejemplo, `"https://contoso-admin.sharepoint.com"`.
    
    - **$AdminAccount** - especifica una cuenta de administrador global de la organización de Office 365, por ejemplo, `"admin@contoso.onmicrosoft.com"`.
    
    - **$eDiscoveryUser** - especifica la cuenta de usuario de un administrador o administrador de cumplimiento que se le asignen como un administrador de colección de sitios para cada OneDrive para el sitio de negocio de la organización, por ejemplo, `"annb@contoso.onmicrosoft.com"`.
    
      > [!NOTE]
      > Cambiar la cuenta de usuario especificada por la variable **$eDiscoveryUser** y vuelva a ejecutar la secuencia de comandos para asignar a un usuario diferente como un administrador de colección de sitios a la OneDrive para los sitios de negocio que se especificado por la variable **$MySiteListFile** . 
  
    - **$MySitePrefix** Especifica la dirección URL de dominio de Mi sitio de la organización. Éste es el dominio que contiene la de OneDrive para sitios de profesionales de la organización, por ejemplo, `"https://contoso-my.sharepoint.com"`.
    
    - **$MySiteListFile** Especifica la ruta de acceso completa del archivo de texto que creó en el paso 1. Este archivo contiene una lista de OneDrive para sitios de profesionales de la organización, por ejemplo, `'C:\Users\<youralias>\Desktop\ListOfMysites.txt'`. Asegúrese de que rodee el valor de esta variable con comillas simples (' '). Tenga en cuenta que debe especificar la ubicación en la que guardó el archivo de texto para en el paso 1.
    
3. Guarde el documento de Bloc de notas como un archivo de script de PowerShell cambiando el sufijo del nombre de archivo por .ps1. Por ejemplo, guarde el archivo OD4BAssignSCA.txt como OD4BAssignSCA.ps1.
    
4. En el Shell de administración de SharePoint Online, vaya a la carpeta donde se encuentre el script de PowerShell creado en el paso anterior y ejecútelo, como por ejemplo:
    
    ```
    .\OD4BAssignSCA.ps1
    ```

    Se le pedirá que escriba la contraseña para la cuenta de administrador que especificó en la secuencia de comandos. Si la secuencia de comandos ejecuta correctamente, el mensaje `"Making  _\<user specified by $eDiscoveryUser\>_ a Site Collection Admin"` se muestra para cada OneDrive para el sitio de negocio que aparece en el archivo de entrada especificado por **$MySiteListFile**.

## <a name="more-information"></a>Más información

- La secuencia de comandos que se ejecutó en el paso 3, usa el cmdlet **Set-SPOUser** para asignar al usuario especificado como un administrador de colección de sitios para cada OneDrive para la empresa que aparece en el archivo especificado por la variable **$MySiteListFile** . Si tiene una organización muy grande con miles de usuarios, tenga en cuenta lo siguiente para que sea más fácil administrar asignar permisos de exhibición de documentos electrónicos. 
    
  - Edite el archivo que creó en el paso 1 que contiene la lista de OneDrive para sitios de profesionales para que incluya sólo los sitios para los usuarios son que participan en casos legales activos.
    
  - Asignar permisos a no más de 2.500 OneDrive para sitios de profesionales por día. Por ejemplo, supongamos que tiene 10.000 OneDrive para sitios de profesionales de la organización. Se pudo crear la lista en el paso 1 para recopilar todos los sitios. A continuación, podría utilizar ese archivo para crear cuatro archivos que contienen los 2.500 usuarios. En el primer día, ejecutaría la secuencia de comandos en el paso 3 para asignar permisos a la OneDrive en primer lugar 2.500 para sitios de negocio. En el segundo día, tendría que ejecutar el script para la siguiente 2.500 OneDrive para sitios de profesionales y así sucesivamente.
    
- Mantener un registro de la OneDrive para los sitios de negocio que se han asignado permisos de exhibición de documentos electrónicos y el usuario que se ha asignado como administrador de la colección de sitios. Por ejemplo, después de asignar permisos, puede guardar el archivo de texto que contiene la lista de OneDrive para sitios profesionales y agregue una línea que identifica al usuario que se ha asignado como administrador de la colección de sitios.
    
- Los usuarios pueden ver la lista de administradores de colección de sitios para su OneDrive para el sitio de negocio. Debido a que los usuarios son el Administrador de colección de sitios para su propios OneDrive para el sitio de negocio, pueden quitar administradores de colección de sitios. Tenga en cuenta lo siguiente para mitigar la posibilidad de quitar el usuario que se asigna permisos de exhibición de documentos electrónicos a OneDrive para sitios de profesionales de los usuarios.
    
  - Comunicar a los usuarios que para fines de cumplimiento de normas y exhibición de documentos electrónicos, un agente de cumplimiento se ha asignado como un administrador de colección de sitios a OneDrive para sitios de profesionales de la organización.
    
  - Vuelva a ejecutar la secuencia de comandos en el paso 3, si es necesario, para volver a asignar a un usuario como administrador de la colección de sitios para OneDrive para sitios de negocio.
    
- También puede utilizar la secuencia de comandos que se ejecutó en el paso 3 para quitar un usuario como administrador de la colección de sitios de OneDrive para sitios de negocio. Para quitar un usuario como un administrador de colección de sitios, debe cambiar el siguiente comando (casi al final de la secuencia de comandos) desde: 

    ```
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $true
    ```

    a:
    
    ```
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $false
    ```

    También puede cambiar la línea siguiente del script de:

    ```
    "Making $eDiscoveryUser a Site Collection Admin"
    ```

    a:
    
    ```
    "Removing $eDiscoveryUser as a Site Collection Admin"
    ```

    Después de realizar estos cambios, guarde la secuencia de comandos con un nombre diferente, como OD4BRemoveSCA.ps1 y, a continuación, usarla para quitar un usuario como un administrador de colección de sitios de un grupo de OneDrive para sitios de negocio.

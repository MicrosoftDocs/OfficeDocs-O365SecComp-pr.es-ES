---
title: Contactos externos de importación masiva a Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: End User
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: Obtenga información sobre cómo los administradores pueden utilizar Exchange Online PowerShell y un archivo CSV a masa importar contactos externos a la lista global de direcciones.
ms.openlocfilehash: 4bde56d49ccf94dc91993df90e1ae693e25c961a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535684"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>Contactos externos de importación masiva a Exchange Online

**En este artículo está dirigido a administradores. ¿Está intentando importar contactos a su propio buzón de correo? Consulte [Importar contactos en Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
¿Su empresa tiene una gran cantidad de contactos profesionales existentes que desee incluir en la libreta de direcciones compartida (también denominada la lista global de direcciones) en Exchange Online? ¿Desea agregar contactos externos como miembros de grupos de distribución, como ocurre con los usuarios dentro de su compañía? Si por lo tanto, puede usar Exchange Online PowerShell y un archivo CSV (valores separados por comas) para masiva importar contactos externos a Exchange Online. Es un proceso de tres pasos:
  
[Paso 1: Crear un archivo CSV que contiene información acerca de los contactos externos](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[Paso 2: Crear los contactos externos con PowerShell](#step-2-create-the-external-contacts-with-powershell) 

[Paso 3: Agregar información a las propiedades de los contactos externos](#step-3-add-information-to-the-properties-of-the-external-contacts)

Después de completar estos pasos para importar los contactos, puede realizar estas tareas adicionales:
  
- [Agregar contactos externos más](bulk-import-external-contacts.md#AddMore)
  
- [Ocultar los contactos externos de la libreta de direcciones compartida](bulk-import-external-contacts.md#Hide)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>Paso 1: Crear un archivo CSV que contiene información acerca de los contactos externos

El primer paso es crear un archivo CSV que contiene información acerca de cada contacto externo que desea importar a Exchange Online. 
  
1. Copie el siguiente texto en un archivo de texto en el Bloc de notas y guárdelo en el escritorio como un archivo CSV mediante el uso de un sufijo de nombre de archivo de .csv; Por ejemplo, ExternalContacts.csv.
    
    > [!TIP]
    > Si su idioma contiene caracteres especiales (por ejemplo, **ö** en sueco, **ä**y **å**) guardar el archivo CSV con UTF-8 u otra codificación Unicode cuando guarde el archivo en el Bloc de notas. 
  
    ```
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park 
    ```

    La primera fila o la fila de encabezado, del archivo CSV se enumera las propiedades de los contactos que se pueden usar al importar a Exchange Online. Cada nombre de la propiedad viene separada por una coma. Cada fila debajo de la fila de encabezado representa los valores de propiedad para la importación de un solo contacto externo. 
    
    > [!NOTE]
    > Este texto incluye datos de ejemplo, que se puede eliminar. Pero no elimine o cambie la primera fila (encabezado). Contiene todas las propiedades para los contactos externos. 
  
2. Abra el archivo CSV en Microsoft Excel para editar el archivo CSV porque es mucho más sencillo utilizar Excel para editar el archivo CSV.
    
3. Crear una fila para cada contacto que desea importar a Exchange Online. Rellenar como muchas de las celdas como sea posible. Esta información se mostrará en la libreta de direcciones compartida para cada contacto. 
    
    > [!IMPORTANT]
    >  Las siguientes propiedades (que son los cuatro primeros elementos en la fila de encabezado) son necesarias para crear un contacto externo y se debe rellenar en el archivo CSV: **ExternalEmailAddress**, **nombre**, **FirstName**, **LastName (apellidos)**. El comando de PowerShell que se ejecutan en el paso 2 usará los valores de estas propiedades para crear los contactos. 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>Paso 2: Crear los contactos externos con PowerShell

El siguiente paso consiste en usar el archivo CSV que creó en el paso 1 y PowerShell a masiva importar los contactos externos que aparecen en el archivo CSV a Exchange Online. 
  
1.  Conectarse PowerShell a la organización de Exchange Online. Para obtener instrucciones detalladas, vea [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). Asegúrese de usar el nombre de usuario y la contraseña de la cuenta de administrador global de Office 365 al conectarse a Exchange Online PowerShell. 
    
2. Tras conectarse a Exchange Online PowerShell, vaya a la carpeta escritorio donde guardó el archivo CSV en el paso 1. Por ejemplo `C:\Users\Administrator\desktop`.
    
3. Ejecute el siguiente comando para crear los contactos externos:

    ```
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    Puede tardar unos momentos para crear nuevos contactos, dependiendo de cuántos va a importar. Cuando finalice el comando Ejecutar, PowerShell, muestra una lista de los nuevos contactos que se crearon. 
    
4. Para ver los nuevos contactos externos, vaya al centro de administración de Exchange (EAC) y, a continuación, haga clic en **destinatarios** \> **contactos**. 
    
    > [!TIP]
    > Para obtener instrucciones para conectar con el CEF, vea el [Centro de administración de Exchange en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197). 
  
5. Si es necesario, haga clic en **Actualizar** ![icono de actualización](media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la lista y ver los contactos externos a los que se han importado. 
    
    Los contactos importados aparecerán en la libreta de direcciones compartida en Outlook y Outlook en el web.
    
    > [!NOTE]
    > También puede ver los contactos en el centro de administración de Office 365 yendo a **los usuarios** \> **contactos**. 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>Paso 3: Agregar información a las propiedades de los contactos externos

Después de ejecutar el comando en el paso 2, se crean los contactos externos, pero que no contienen la información de contacto o la organización, que es la información de la mayoría de las celdas en el archivo CSV. Esto es debido a que al crear nuevos contactos externos, se rellenan sólo las propiedades necesarias. No se preocupe si no dispone de toda la información que se rellena en el archivo CSV. Si no es así, no se agregará.
  
1.  Conectarse PowerShell a la organización de Exchange Online. Para obtener instrucciones detalladas, vea [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Vaya a la carpeta escritorio donde guardó el archivo CSV en el paso 1. Por ejemplo `C:\Users\Administrator\desktop`.
    
3. Ejecute los dos comandos siguientes para agregar las demás propiedades del archivo CSV a los contactos externos a los que ha creado en el paso 2.
    
    ```
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > El parámetro _Manager_ podría ser un inconveniente. Si la celda está en blanco en el archivo CSV, recibirá un error y ninguno de los datos de propiedad se agregarán al contacto. Si no es necesario especificar un administrador, a continuación, simplemente elimine ` -Manager $_.Manager ` desde el anterior comando de PowerShell. 
  
    Una vez más, puede tardar unos momentos para actualizar los contactos, dependiendo de cuántos ha importado en el paso 1. 
    
4. Para comprobar que se han agregado las propiedades a los contactos: 
    
1. En el EAC, vaya a **Destinatarios** \> **Contactos**.
    
2. Haga clic en un contacto y, a continuación, haga clic en **Editar** ![icono Editar](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) para mostrar las propiedades del contacto. 
    
¡Eso es todo! Los usuarios pueden ver los contactos y la información adicional en la libreta de direcciones de Outlook y Outlook en el web.
  
## <a name="add-more-external-contacts"></a>Agregar contactos externos más

Repita los pasos del 1 al paso 3 para agregar contactos externos nuevos en Exchange Online. Usted o los usuarios de su compañía sólo pueden agregar una nueva fila en el archivo CSV para el nuevo contacto. A continuación, puede ejecutar los comandos de PowerShell de paso 2 y paso 3 para crear y agregar información a los nuevos contactos.
  
> [!NOTE]
> Cuando se ejecuta el comando para crear nuevos contactos, es posible que obtenga un error que indica que los contactos a los que se crearon anteriormente ya existen. Pero se crea cualquier contacto nuevo que se agrega al archivo CSV. 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>Ocultar los contactos externos de la libreta de direcciones compartida >

Algunas compañías pueden utilizar los contactos externos solo por lo que se pueden agregar como miembros de grupos de distribución. En este escenario, desean ocultar a los contactos externos de la libreta de direcciones compartida. Aquí es cómo:
  
1.  Conectarse PowerShell a la organización de Exchange Online. Para obtener instrucciones detalladas, vea [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Para ocultar un solo contacto externo, ejecute el siguiente comando.
    
    ```
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```
 
    Por ejemplo, para ocultar Pilar Pinilla desde la libreta de direcciones compartida, ejecute este comando:

    ```
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```
   
3. Para ocultar todos los contactos externos de la libreta de direcciones compartida, ejecute este comando:

    ```
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

Después de ocultar ellos, contactos externos no se muestran en la libreta de direcciones compartida, pero puede agregarla como miembros de un grupo de distribución.

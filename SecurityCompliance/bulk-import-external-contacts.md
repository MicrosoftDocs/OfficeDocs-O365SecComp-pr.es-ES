---
title: Importación masiva de contactos externos a Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: Obtenga información sobre cómo los administradores pueden usar Exchange Online PowerShell y un archivo CSV para importar de forma masiva contactos externos a la lista global de direcciones.
ms.openlocfilehash: a38565d5cbff61a954914bf156fb1bac0814c815
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215920"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>Importación masiva de contactos externos a Exchange Online

**Este artículo está destinado a los administradores. ¿Está intentando importar contactos a su propio buzón? Consulte [Importar contactos a Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
¿Su empresa tiene muchos contactos profesionales existentes que desea incluir en la libreta de direcciones compartida (también denominada lista global de direcciones) en Exchange Online? ¿Desea agregar contactos externos como miembros de grupos de distribución, exactamente igual que con los usuarios de su compañía? Si es así, puede usar Exchange Online PowerShell y un archivo CSV (valores separados por comas) para importar de forma masiva contactos externos en Exchange Online. Se trata de un proceso de tres pasos:
  
[Paso 1: crear un archivo CSV que contenga información sobre los contactos externos](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[Paso 2: crear los contactos externos con PowerShell](#step-2-create-the-external-contacts-with-powershell) 

[Paso 3: agregar información a las propiedades de los contactos externos](#step-3-add-information-to-the-properties-of-the-external-contacts)

Después de completar estos pasos para importar contactos, puede realizar estas tareas adicionales:
  
- [Agregar más contactos externos](bulk-import-external-contacts.md#AddMore)
  
- [Ocultar contactos externos de la libreta de direcciones compartida](bulk-import-external-contacts.md#Hide)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>Paso 1: crear un archivo CSV que contenga información sobre los contactos externos

El primer paso consiste en crear un archivo CSV que contenga información sobre cada contacto externo que desee importar a Exchange Online. 
  
1. Copie el siguiente texto en un archivo de texto en el Bloc de notas y guárdelo en el escritorio como un archivo CSV con un sufijo de nombre de archivo de. csv; por ejemplo, ExternalContacts. csv.
    
    > [!TIP]
    > Si el idioma contiene caracteres especiales (como **å**, **ä**y **ö** en sueco), guarde el archivo CSV con codificación UTF-8 u otra codificación Unicode al guardar el archivo en el Bloc de notas. 
  
    ```
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park 
    ```

    En la primera fila, o fila de encabezado, del archivo CSV se enumeran las propiedades de los contactos que se pueden usar al importarlos a Exchange Online. Cada nombre de propiedad está separado por una coma. Cada fila situada debajo de la fila de encabezado representa los valores de propiedad para importar un solo contacto externo. 
    
    > [!NOTE]
    > Este texto incluye datos de ejemplo, que se pueden eliminar. Pero no elimine ni cambie la primera fila (de encabezado). Contiene todas las propiedades de los contactos externos. 
  
2. Abra el archivo CSV en Microsoft Excel para editar el archivo CSV porque es mucho más fácil usar Excel para editar el archivo CSV.
    
3. Cree una fila para cada contacto que desee importar a Exchange Online. ReLlenar tantas celdas como sea posible. Esta información se mostrará en la libreta de direcciones compartida para cada contacto. 
    
    > [!IMPORTANT]
    >  Las siguientes propiedades (que son los primeros cuatro elementos de la fila de encabezado) son necesarias para crear un contacto externo y deben rellenarse en el archivo CSV: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**. El comando de PowerShell que ejecutó en el paso 2 usará los valores de estas propiedades para crear los contactos. 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>Paso 2: crear los contactos externos con PowerShell

El siguiente paso es usar el archivo CSV que creó en el paso 1 y PowerShell para importar de forma masiva los contactos externos que aparecen en el archivo CSV a Exchange Online. 
  
1.  Conecte PowerShell a la organización de Exchange Online. Para obtener instrucciones paso a paso, consulte [conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). Asegúrese de usar el nombre de usuario y la contraseña de su cuenta de administrador global de Office 365 cuando se conecte a Exchange Online PowerShell. 
    
2. Después de conectar PowerShell a Exchange Online, vaya a la carpeta escritorio donde guardó el archivo CSV en el paso 1; por ejemplo `C:\Users\Administrator\desktop`.
    
3. Ejecute el siguiente comando para crear los contactos externos:

    ```
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    Puede tardar un rato en crear los nuevos contactos, en función del número de importaciones que va a importar. Cuando el comando termina de ejecutarse, PowerShell muestra una lista de los nuevos contactos que se crearon. 
    
4. Para ver los nuevos contactos externos, vaya al centro de administración de Exchange (EAC) y, a **** \> continuación, haga clic en destinatarios y **contactos**. 
    
    > [!TIP]
    > Para obtener instrucciones sobre cómo conectar con el EAC, vea [centro de administración de Exchange en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197). 
  
5. Si es necesario, **** ![haga clic en](media/O365-MDM-Policy-RefreshIcon.gif) actualizar icono de actualización para actualizar la lista y ver los contactos externos que se importaron. 
    
    Los contactos importados aparecerán en la libreta de direcciones compartida en Outlook y Outlook en la Web.
    
    > [!NOTE]
    > también puede ver los contactos en el centro de administración de Office 365 yendo a **** \> **contactos**de usuarios. 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>Paso 3: agregar información a las propiedades de los contactos externos

Después de ejecutar el comando en el paso 2, se crean los contactos externos, pero no contienen ninguna información de contacto u organización, que es la información de la mayoría de las celdas en el archivo CSV. Esto se debe a que, al crear nuevos contactos externos, solo se rellenan las propiedades necesarias. No se preocupe si no tiene toda la información rellenada en el archivo CSV. Si no está allí, no se agregará.
  
1.  Conecte PowerShell a la organización de Exchange Online. Para obtener instrucciones paso a paso, consulte [conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Vaya a la carpeta escritorio donde guardó el archivo CSV en el paso 1; por ejemplo `C:\Users\Administrator\desktop`.
    
3. Ejecute los dos comandos siguientes para agregar otras propiedades desde el archivo CSV a los contactos externos que creó en el paso 2.
    
    ```
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > El parámetro _Manager_ puede ser problemático. Si la celda está en blanco en el archivo CSV, recibirá un error y no se agregará ninguna información de la propiedad al contacto. Si no necesita especificar un administrador, simplemente elimine ` -Manager $_.Manager ` del comando de PowerShell anterior. 
  
    Una vez más, puede tardar un rato en actualizar los contactos, en función de cuánto se importó en el paso 1. 
    
4. Para comprobar que las propiedades se agregaron a los contactos: 
    
1. En el EAC, vaya a **Destinatarios** \> **Contactos**.
    
2. Haga clic en un contacto y, a continuación](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) , haga clic en **Editar** ![icono Editar para mostrar las propiedades del contacto. 
    
Esto es todo. Los usuarios pueden ver los contactos y la información adicional en la libreta de direcciones de Outlook y Outlook en la Web.
  
## <a name="add-more-external-contacts"></a>Agregar más contactos externos

Puede repetir los pasos del 1 al paso 3 para agregar nuevos contactos externos en Exchange Online. Usted o los usuarios de su empresa solo pueden agregar una nueva fila en el archivo CSV para el nuevo contacto. A continuación, puede ejecutar los comandos de PowerShell desde el paso 2 y el paso 3 para crear y agregar información a los nuevos contactos.
  
> [!NOTE]
> Al ejecutar el comando para crear nuevos contactos, es posible que reciba un error que indica que los contactos que se crearon anteriormente ya existen. Sin embargo, se creará un nuevo contacto agregado al archivo CSV. 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>Ocultar contactos externos de la dirección compartida book>

Es posible que algunas empresas solo usen contactos externos para que puedan agregarse como miembros de los grupos de distribución. En este escenario, es posible que quiera ocultar los contactos externos de la libreta de direcciones compartida. Esta es la manera de hacerlo:
  
1.  Conecte PowerShell a la organización de Exchange Online. Para obtener instrucciones paso a paso, consulte [conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Para ocultar un solo contacto externo, ejecute el siguiente comando.
    
    ```
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```
 
    Por ejemplo, para ocultar Pilar Pinilla de la libreta de direcciones compartida, ejecute este comando:

    ```
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```
   
3. Para ocultar todos los contactos externos de la libreta de direcciones compartida, ejecute este comando:

    ```
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

Después de ocultarlos, los contactos externos no se muestran en la libreta de direcciones compartida, pero puede agregarlos como miembros de un grupo de distribución.

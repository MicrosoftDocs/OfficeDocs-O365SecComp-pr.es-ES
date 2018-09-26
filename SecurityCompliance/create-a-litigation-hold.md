---
title: Crear una suspensión por litigio en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
ms.openlocfilehash: aa78d12046108aa1f1b974f01c02ff923b99b97b
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "25037963"
---
# <a name="create-a-litigation-hold-in-office-365"></a>Crear una suspensión por litigio en Office 365

Puede colocar un buzón de correo en juicio para conservar todos los buzones de correo contenido, incluidos los elementos eliminados y las versiones originales de los elementos modificados. Al colocar un buzón de usuario en suspensión por litigio, contenido en el buzón de archivo del usuario (si está habilitada) también se conserva. Cuando se crea una suspensión, puede especificar una duración de espera (también llamada una *retención basada en tiempo*) para que eliminen y elementos modificados se conservan durante un período especificado y, a continuación, elimina de manera permanente el buzón de correo. O simplemente puede conservar contenido indefinidamente (denominado una *espera infinita*) o hasta que se quite la suspensión por litigio. Si especifica un período de duración de retención, se calcula a partir de la fecha se recibe un mensaje o se crea un elemento de buzón de correo. 
  
Aquí es lo que sucede cuando se crea un juicio.
  
- Los elementos que se eliminan permanentemente por el usuario se conservan en la carpeta elementos recuperables en el buzón del usuario para la duración de la suspensión.
    
- Se conservan los elementos que se purgan de la carpeta elementos recuperables por el usuario para la duración de la suspensión.
    
- La cuota de almacenamiento de la carpeta elementos recuperables se incrementó de 30 GB a 110 GB.
    
- Se conservan los elementos de principal del usuario y los buzones de correo de archivo
    
## <a name="before-you-begin"></a>Antes de empezar

- Para poner un buzón de Exchange Online en juicio, se debe asignar una licencia de Exchange Online Plan 2. Si un buzón se asigna una licencia de Exchange Online Plan 1, tendría asignarla a una licencia independiente de archivado de Exchange Online para poner en espera.
    

## <a name="place-a-mailbox-on-litigation-hold-in-the-office-365-admin-center"></a>Colocar un buzón en suspensión por litigio en el centro de administración de Office 365

Estos son los pasos para colocar un buzones en suspensión por litigio mediante el centro de administración de Office 365.

1. Vaya a https://portal.office.com/adminportal/home e iniciar sesión con su cuenta de administrador global.
2. Haga clic en **usuarios** > **usuarios activos** en el panel de navegación izquierdo.
3. Seleccione el usuario cuyo buzón de correo que desea colocar en suspensión por litigio.
4. En la página emergentes, haga clic en **configuración de correo**y, a continuación, haga clic en **Editar** junto a **la suspensión por litigio**.
5. En la página **juicio** , haga clic en la alternancia para activar la suspensión por litigio y completar la siguiente configuración opcional que se muestra:
 
    ![O365_LitigationHold1.png](media/O365-LitigationHold1.png)

    r. **duración de la retención (días)** -Utilice este cuadro para crear una suspensión basada en tiempo y especifique cuánto tiempo se conservan los elementos del buzón de correo cuando el buzón de correo se coloca en suspensión por litigio. La duración se calcula a partir la fecha de un elemento de buzón de correo se ha recibido o creado. Si deja este cuadro en blanco, se conservan los elementos indefinidamente o hasta que se ha quitado la suspensión. Use días para especificar la duración.
    
    b. **Nota** - Utilice este cuadro para informar al usuario su buzón se encuentra en suspensión por litigio. La nota aparecerá en la página de información de la cuenta en el buzón del usuario si está utilizando Outlook 2010 o posterior. Para obtener acceso a esta página, los usuarios pueden hacer clic en el **archivo** en Outlook.
     
    c. **página Web** - Utilice este cuadro para dirigir al usuario a un sitio Web para obtener más información acerca de la suspensión por litigio. Esta dirección URL aparece en la página de información de la cuenta en el buzón del usuario si usan Outlook 2010 o posterior. Para obtener acceso a esta página, los usuarios pueden hacer clic en el **archivo** en Outlook.
 
6. Haga clic en **Guardar** para crear el juicio.

Después de crear la suspensión, se muestra la configuración de correo en la página emergentes que juicio está activado para el usuario seleccionado.

![O365_LitigationHold2.png](media/O365-LitigationHold2.png)

Para obtener más información sobre la creación y administración de retenciones para litigios con y uso de Exchange Online PowerShell para creación masiva de retenciones para litigios con, vea [colocar un buzón en suspensión por litigio](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold).

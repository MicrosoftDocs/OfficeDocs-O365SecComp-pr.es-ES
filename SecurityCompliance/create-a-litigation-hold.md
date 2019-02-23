---
title: Crear una retención por juicio en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
ms.openlocfilehash: f2d3793eac84e8f80158842c833c30986b0549c5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218660"
---
# <a name="create-a-litigation-hold-in-office-365"></a>Crear una retención por juicio en Office 365

Puede poner un buzón en retención por juicio para retener todo el contenido del buzón, incluidos los elementos eliminados y las versiones originales de los elementos modificados. Cuando se pone un buzón de usuario en retención por juicio, también se conserva el contenido del buzón de archivo del usuario (si está habilitado). Al crear una suspensión, puede especificar una duración de retención (también denominada *retención basada en tiempo*) para que los elementos eliminados y modificados se conserven durante un período específico y, a continuación, se eliminen de forma permanente del buzón. O bien solo puede retener el contenido indefinidamente (denominado una *retención infinita*) o hasta que se quite la retención por juicio. Si especifica un período de duración de retención, se calcula a partir de la fecha en que se recibe un mensaje o se crea un elemento de buzón de correo. 
  
Esto es lo que sucede cuando se crea una retención por juicio.
  
- Los elementos eliminados de forma permanente por el usuario se conservan en la carpeta elementos recuperables del buzón del usuario durante toda la retención.
    
- Los elementos purgados de la carpeta elementos recuperables por el usuario se conservan durante toda la retención.
    
- La cuota de almacenamiento de la carpeta elementos recuperables se ha incrementado de 30 GB a 110 GB.
    
- Se conservan los elementos del buzón principal del usuario y los buzones de archivo.
    
## <a name="before-you-begin"></a>Antes de empezar

- Para poner un buzón de correo de Exchange online en retención por juicio, se le debe asignar una licencia de Exchange Online (plan 2). Si un buzón tiene asignada una licencia de Exchange Online (plan 1), tendrá que asignarle una licencia de archivado de Exchange Online independiente para ponerla en espera.
    

## <a name="place-a-mailbox-on-litigation-hold-in-the-office-365-admin-center"></a>Poner un buzón en retención por juicio en el centro de administración de Office 365

Estos son los pasos para poner un Maibox en retención por juicio mediante el centro de administración de Office 365.

1. Vaya a https://portal.office.com/adminportal/home e inicie sesión con su cuenta de administrador global.
2. Haga clic en usuarios**activos** de **usuarios** > en el panel de navegación izquierdo.
3. Seleccione el usuario cuyo buzón quiera poner en retención por juicio.
4. En la página emergente, haga clic en **configuración de correo**y, a continuación, haga clic en **Editar** junto a retención por **juicio**.
5. En la página **retención por juicio** , haga clic en el botón de alternancia para activar la retención por juicio y complete los siguientes parámetros opcionales que se muestran:
 
    ![O365_LitigationHold1. png](media/O365-LitigationHold1.png)

    duración de **retención (días)** : Use este cuadro para crear una retención basada en tiempo y especificar cuánto tiempo se conservarán los elementos del buzón cuando el buzón de correo se coloca en retención por juicio. La duración se calcula a partir de la fecha en que se recibe o se crea un elemento de buzón. Si deja este cuadro en blanco, los elementos se conservan indefinidamente o hasta que se quite la retención. Use días para especificar la duración.
    
    b. **Nota** : Use este cuadro para informar al usuario de que su buzón de correo está en retención por juicio. La nota aparecerá en la página de información de cuenta del buzón de correo del usuario si usa Outlook 2010 o posterior. Para tener acceso a esta página, los usuarios pueden hacer clic en **archivo** en Outlook.
     
    c. **Página Web** : Use este cuadro para dirigir al usuario a un sitio web para obtener más información sobre la retención por juicio. Esta dirección URL aparece en la página de información de cuenta del buzón del usuario si usa Outlook 2010 o posterior. Para tener acceso a esta página, los usuarios pueden hacer clic en **archivo** en Outlook.
 
6. Haga clic en **Guardar** para crear la retención por juicio.

Después de crear la retención, la configuración de correo de la página emergente muestra que la retención por juicio está activada para el usuario seleccionado.

![O365_LitigationHold2. png](media/O365-LitigationHold2.png)

Para obtener más información sobre la creación y la administración de suspensiones por juicio y el uso de Exchange Online PowerShell para crear de forma masiva reTenciones por juicio, vea [poner un buzón en retención por juicio](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold).

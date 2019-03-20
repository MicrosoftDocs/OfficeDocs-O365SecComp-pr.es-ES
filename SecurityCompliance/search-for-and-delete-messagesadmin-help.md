---
title: 'Buscar y eliminar mensajes: Ayuda para administradores'
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/20/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8c36bb03-e716-4fdd-9958-4aa7a2a1db42
description: Los administradores pueden usar el cmdlet Search-Mailbox para buscar en buzones de usuario y, después, eliminar mensajes de un buzón.
ms.openlocfilehash: abf7e7f39fe719ecc6c23565e284c01aed8822ee
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693489"
---
# <a name="search-for-and-delete-messages---admin-help"></a>Buscar y eliminar mensajes: Ayuda para administradores
  
Los administradores pueden usar el cmdlet **Search-Mailbox** para buscar en buzones de usuario y, después, eliminar mensajes de un buzón. 
  
Para buscar y eliminar los mensajes en un solo paso, ejecute el cmdlet **Search-Mailbox** con el modificador  _DeleteContent_. Sin embargo, cuando hace esto, no puede previsualizar los resultados de la búsqueda ni generar un registro de mensajes que será devuelto por la búsqueda y puede eliminar mensajes accidentalmente que pretendía conservar. Para previsualizar un registro de mensajes encontrados en la búsqueda antes de que se eliminen, ejecute el cmdlet **Search-Mailbox** con el modificador  _LogOnly_. 
  
Como una protección adicional, primero puede copiar los mensajes en otro buzón con los parámetros  _TargetMailbox_ y  _TargetFolder_. Al hacer esto, guarda una copia de los mensajes eliminados en caso de que necesite obtener acceso a ellos nuevamente. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Tiempo estimado para finalizar: 10 minutos. El tiempo real puede variar en función del tamaño del buzón y la consulta de búsqueda.
    
- No puede usar el Centro de administración de Exchange (EAC) para realizar estos procedimientos. Debe usar el Shell.
    
- Tiene que tener asignados los siguientes roles de administración para buscar y eliminar los mensajes en los buzones de correo de los usuarios:
    
  - **Búsqueda**en buzones: este rol permite buscar mensajes en varios buzones de la organización. Los administradores no tienen asignado este rol de forma predeterminada. Para asignarse a sí mismo este rol para poder buscar en buzones, agréguese como miembro del grupo de rol de administración de la detección. Vea [Add a User to the Discovery Management Role Group](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx).
    
  - **Importación y exportación** de buzones: este rol permite eliminar mensajes del buzón de un usuario. De forma predeterminada, este rol no está asignado a ningún grupo de roles. Para eliminar mensajes de los buzones de los usuarios, puede agregar el rol de importación o exportación de buzones al grupo de roles de administración de la organización. Para obtener más información, consulte la sección "agregar un rol a un grupo de roles" en [Manage role Groups](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx) . 
    
- Si el buzón desde el cual desea eliminar los mensajes tiene la recuperación de un solo elemento habilitada, primero debe deshabilitar la función. Para obtener más información, consulte [Habilitar o deshabilitar la recuperación de elementos individuales de un buzón de correo](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx).
    
- Si el buzón del que desea eliminar los mensajes está en espera, le recomendamos que se ponga en contacto con su departamento jurídico o de administración de registros antes de eliminar la espera y eliminar el contenido del buzón. Después de obtener la aprobación, siga los pasos que se indican en el tema [Clean up the recoverAble items Folder](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx).
    
- Puede buscar en un máximo de 10 000 buzones con el cmdlet **Search-Mailbox**. Si es Exchange Online de una organización y tiene más de 10 000 buzones, puede usar la característica Búsqueda de cumplimiento (o el cmdlet **New-ComplianceSearch** correspondiente) para buscar en un número ilimitado de buzones. Después, puede usar el cmdlet **New-ComplianceSearchAction** para eliminar los mensajes encontrados por una búsqueda de cumplimiento. Para obtener más información, vea [Buscar y eliminar mensajes de correo electrónico de la organización de Office 365](https://go.microsoft.com/fwlink/p/?LinkId=786856).
    
- Si incluye una consulta de búsqueda (utilizando el parámetro  *SearchQuery*  ), el cmdlet **Search-Mailbox** devolverá un máximo de 10 000 elementos en los resultados de búsqueda. Por tanto, si incluye una consulta de búsqueda, es posible que deba ejecutar el comando **Search-Mailbox** varias veces para eliminar más de 10 000 elementos. 
    
- También se explorará el buzón de archivo del usuario cuando se ejecuta el cmdlet **Search-Mailbox**. Asimismo, se eliminarán los elementos del buzón principal del archivo al usar el cmdlet **Search-Mailbox** con el cambio  _DeleteContent_. Para evitarlo, puede incluir el cambio  *DoNotIncludeArchive*  . Además, se recomienda no usar el modificador _DeleteContent_ para eliminar los mensajes de los buzones de Exchange online que tienen habilitado el archivado de expansión automática porque se puede producir una pérdida de datos inesperada. 
    
## <a name="search-messages-and-log-the-search-results"></a>Buscar mensajes y registrar los resultados de la búsqueda

En este ejemplo, se buscan mensajes que contengan la frase "Su extracto bancario" en el campo Asunto en el buzón de correo de April Stewart y se registra el resultado en la carpeta SearchAndDeleteLog en el buzón de correo del administrador. Los mensajes no se copian ni eliminar en el buzón de correo de destino.
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

Este ejemplo busca en todos los buzones de la organización los mensajes que tienen cualquier tipo de archivo adjunto que contiene la palabra "Troyano" en el nombre de archivo y envía un mensaje de registro al buzón del administrador.
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery attachment:trojan* -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).
  
 
## <a name="search-and-delete-messages"></a>Buscar y eliminar mensajes

En este ejemplo, se buscan mensajes que contengan la frase "Su extracto bancario" en el asunto en el buzón de correo de Yolanda Sánchez y se eliminan los mensajes del buzón de correo de origen. Como se explicó anteriormente, tiene que tener asignado el rol de administración Importar o exportar buzones para eliminar los mensajes del buzón de un usuario.
  
> [!IMPORTANT]
> Cuando usa el cmdlet **Search-Mailbox** con el modificador  _DeleteContent_, los mensajes se eliminan permanentemente del buzón origen. Antes de eliminar permanentemente los mensajes, le recomendamos que use el modificador  _LogOnly_ para generar un registro de los mensajes encontrados en la búsqueda antes de que se eliminen o que copie los mensajes en otro buzón antes de eliminarlo desde el buzón origen. 
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -DeleteContent
```

En este ejemplo, se buscan mensajes que contengan la frase "Su extracto bancario" en el campo Asunto en el buzón de correo de April Stewart, se copian los resultados de la búsqueda en la carpeta AprilStewart-DeletedMessages en el buzón BackupMailbox y se eliminan los mensajes del buzón de April.
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox "BackupMailbox" -TargetFolder "AprilStewart-DeletedMessages" -LogLevel Full -DeleteContent
```

Este ejemplo busca en todos los buzones de la organización los mensajes con el asunto "Descargar este archivo" y, a continuación, los elimina de forma definitiva. 
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery 'Subject:"Download this file"' -DeleteContent
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).

## <a name="using-the--loglevel-full-parameter"></a>Usar el parámetro -LogLevel Full

En algunos de los ejemplos anteriores, el parámetro  _LogLevel_ (con el valor  `Full`) se usa para registrar información detallada sobre los resultados encontrados por el cmdlet **Search-Mailbox**. Al incluir este parámetro, se crea un mensaje de correo electrónico y se envía al buzón especificado por el parámetro  _TargetMailbox_. El archivo de registro (que es un archivo con formato CSV llamado Search Results.csv) se adjunta a este mensaje de correo electrónico y se guarda en la carpeta especificada por el parámetro  _TargetFolder_. El archivo de registro contiene una fila por cada mensaje incluido en los resultados de la búsqueda al ejecutar el cmdlet **Search-Mailbox**. 

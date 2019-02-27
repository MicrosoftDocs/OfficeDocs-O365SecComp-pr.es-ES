---
title: Poner un buzón en retención por juicio
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2016
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: ''
ms.assetid: adee4621-3626-4aec-aa53-00b35ff0d0b0
description: 'Coloque un buzón en retención por juicio para conservar todo el contenido del buzón, incluidos los elementos eliminados y las versiones originales de los elementos modificados. '
ms.openlocfilehash: b2d2a60fddb51aa310d01a765c1ebbbf127ecd19
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296983"
---
# <a name="place-a-mailbox-on-litigation-hold"></a>Poner un buzón en retención por juicio
 
Coloque un buzón en retención por juicio para conservar todo el contenido del buzón, incluidos los elementos eliminados y las versiones originales de los elementos modificados. Al colocar el buzón de correo de un usuario en retención por juicio, el contenido del buzón de archivo del usuario (si está habilitado) también se coloca en retención. Los elementos eliminados y modificados se conservan durante un período especificado o hasta que se elimina la retención por juicio del buzón. Todos los elementos del buzón de correo se devuelven en una búsqueda de [In-Place eDiscovery](http://technet.microsoft.com/library/6377cb7a-3416-4e15-8571-c45d2160fc6f.aspx). 
  
> [!IMPORTANT]
> La retención por juicio conserva los elementos de la carpeta elementos recuperables del buzón de correo del usuario. Según el número y el tamaño de los elementos eliminados o modificados, el tamaño de la carpeta elementos recuperables del buzón de correo puede aumentar rápidamente. De forma predeterminada, la carpeta elementos recuperables está configurada con una cuota alta. En Exchange Online, esta cuota aumenta automáticamente cuando se pone un buzón de correo en retención por juicio. En Exchange Server 2013, se recomienda supervisar semanalmente los buzones que se colocan en retención por juicio para asegurarse de que no alcanzan los límites de las cuotas de elementos recuperables. 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?
<a name="sectionSection0"> </a>

- Tiempo estimado para finalizar: 5 minutos
    
- La configuración de la retención por juicio puede tardar hasta 60 minutos en surtir efecto.
    
- Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "Conservación local" en el tema [Permisos de directivas de mensajería y conformidad](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx). 
    
- Para poner un buzón de correo de Exchange online en retención por juicio, se le debe asignar una licencia de Exchange Online (plan 2). Si un buzón tiene asignada una licencia de Exchange Online (plan 1), tendrá que asignar una licencia de archivado de Exchange Online independiente para ponerla en espera.
    
- Como se ha explicado anteriormente, cuando se coloca una retención por juicio en el buzón de un usuario, el contenido del buzón de archivo del usuario también se coloca en retención. Si coloca una retención por juicio en un buzón principal local en una implementación híbrida de Exchange, el buzón de archivo basado en la nube (si está habilitado) también se coloca en retención.
    
- En Exchange Online, la cuota de la carpeta elementos recuperables aumenta automáticamente a 100 GB cuando se pone un buzón de correo en retención por juicio. El tamaño predeterminado de esta carpeta es 30 GB.
    
- La retención por juicio conserva los elementos eliminados y conserva las versiones originales de los elementos modificados hasta que se quite la retención. Opcionalmente, puede especificar una duración de retención, que conserva un elemento de buzón durante el período de duración especificado. Si especifica un período de duración de retención, se calcula a partir de la fecha en que se recibe un mensaje o se crea un elemento de buzón de correo. Para conservar los elementos que cumplan los criterios especificados, use una conservación local para crear una retención basada en consulta. Para obtener más información, consulte [crear o quitar una conservación local](http://technet.microsoft.com/library/9d5d8d37-a053-4830-9cb1-6e1ede25e963.aspx).
    
- Para usar el shell para poner un buzón de correo de Exchange online en suspensión, debe usar Exchange Online PowerShell. Para obtener más información, vea [conectarse a Exchange online mediante PowerShell remoto](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx).
    
- No se admite la creación de una retención por juicio en un buzón de carpeta pública. Tendrá que usar la conservación local para crear una retención en las carpetas públicas.
    
## <a name="use-the-eac-to-place-a-mailbox-on-litigation-hold"></a>Usar el EMC para colocar un buzón en retención por juicio
<a name="sectionSection1"> </a>

1. Vaya a **Destinatarios** \> **Buzones de correo**.
    
2. En la lista de buzones de usuario, haga clic en el buzón que desea poner en retención por juicio y, a **** ![continuación, haga](media/ITPro-EAC-EditIcon.gif)clic en Editar icono de edición.
    
3. En la página de propiedades del buzón, haga clic en **características de buzón.**
    
4. En **Retención por juicio: Deshabilitado**, haga clic en **Habilitar** para colocar el buzón en Retención por juicio. 
    
5. En la página **Retención por juicio**, especifique la siguiente información opcional: 
    
  - **Duración de retención por juicio (días):** Utilice este cuadro para especificar cuánto tiempo se conservarán los elementos del buzón cuando este se ponga en retención por juicio. La duración se calcula desde la fecha en que un elemento de buzón se recibe o se crea. Si deja este cuadro en blanco, los elementos se conservan indefinidamente o hasta que se elimine la retención. Use días para especificar la duración. 
    
  - **Nota:** Use este cuadro para informar al usuario de que su buzón de correo está en retención por juicio. La nota aparecerá en el buzón de correo del usuario si está usando Outlook 2010 o posterior. 
    
  - **Dirección URL** Use este cuadro para dirigir al usuario a un sitio web para obtener más información sobre la retención por juicio. Esta dirección URL aparece en el buzón de correo del usuario si usa Outlook 2010 o posterior. 
    
6. Haga clic en **Guardar** en la página **Retención por juicio** y, después, haga clic en **Guardar** en la página de propiedades del buzón. 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-indefinitely"></a>Usar el Shell para colocar un buzón en retención por juicio indefinidamente
<a name="sectionSection2"> </a>

En este ejemplo, se coloca el buzón bsuneja@contoso.com en retención por juicio. Los elementos del buzón se conservan indefinidamente o hasta que se elimine la retención.
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true
```

> [!NOTE]
> Al colocar un buzón en retención por juicio indefinidamente (sin especificar una duración), el valor de la propiedad  _LitigationHoldDuration_ del buzón se establece en  `Unlimited`. 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-and-preserve-items-for-a-specified-duration"></a>Usar el Shell para colocar un buzón en retención por juicio y conservar los elementos durante un tiempo especificado
<a name="sectionSection3"> </a>

Este ejemplo coloca el buzón bsuneja@contoso.com en retención por juicio y conserva los elementos durante 2555 días (aproximadamente 7 años). 
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true -LitigationHoldDuration 2555
```

## <a name="use-the-shell-to-place-all-mailboxes-on-litigation-hold-for-a-specified-duration"></a>Usar el Shell para colocar todos los buzones en retención por juicio durante un tiempo especificado
<a name="sectionSection4"> </a>

Su organización puede necesitar que los datos de todos los buzones se conserven durante un período determinado. Antes de colocar todos los buzones de una organización en retención por juicio, tenga en cuenta lo siguiente:
  
En este ejemplo todos los buzones de usuario de la organización se colocan en retención por juicio durante un año (365 días).
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -LitigationHoldEnabled $true -LitigationHoldDuration 365
```

El ejemplo usa el cmdlet [Get-Mailbox](http://technet.microsoft.com/library/8a5a6eb9-4a75-47f9-ae3b-a3ba251cf9a8.aspx) para recuperar todos los buzones de la organización, especifica un filtro de destinatarios para incluir todos los buzones de usuario y, después, canaliza la lista de buzones al cmdlet [Set-Mailbox](http://technet.microsoft.com/library/a0d413b9-d949-4df6-ba96-ac0906dedae2.aspx) para habilitar la retención por juicio y la duración de la retención. 
  
Para colocar todos los buzones de usuario en una retención indefinida, ejecute el comando anterior pero no incluya el parámetro  _LitigationHoldDuration_. 
  
Consulte la sección [Más información](#moreinfo.md) para ver ejemplos de cómo usar otras propiedades de destinatarios en un filtro para incluir o excluir uno o más buzones. 
  
## <a name="use-the-shell-to-remove-a-mailbox-from-litigation-hold"></a>Usar el Shell para quitar un buzón de la retención por juicio
<a name="sectionSection5"> </a>

En este ejemplo, se quita el buzón de correo bsuneja@contoso.com de la retención por juicio.
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $false
```

P
## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se completó correctamente?
<a name="sectionSection6"> </a>

Para comprobar que un buzón se ha colocado correctamente en retención por juicio, realice unas de estas acciones:
  
- En el EAC:
    
1. Vaya a **Destinatarios** \> **Buzones de correo**.
    
2. En la lista de buzones de usuario, haga clic en el buzón para el que desea comprobar la configuración de retención por juicio y, a](media/ITPro-EAC-EditIcon.gif)continuación, haga clic en **Editar** ![icono de edición.
    
3. En la página de propiedades del buzón, haga clic en **características de buzón.**
    
4. En **Retención por juicio**, compruebe que la retención está habilitada.
    
5. Haga clic en **Ver detalles** para comprobar cuándo se colocó el buzón en retención por juicio y quién lo hizo. También puede comprobar o cambiar los valores de las casillas opcionales **Duración de retención por juicio (días)**, **Nota** y **Dirección URL**. 
    
- En el Shell, ejecute uno de los siguientes comandos:
    
  ```
  Get-Mailbox <name of mailbox> | FL LitigationHold*
  ```

    o
    
  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,LitigationHold*
  ```

    Si un buzón se coloca en retención por juicio indefinidamente, el valor de la propiedad del buzón  _LitigationHoldDuration_ se establece en  `Unlimited`.
    
## <a name="more-information"></a>Más información
<a name="moreinfo"> </a>

- Si su organización requiere que los datos de todos los buzones se conserven durante un período de tiempo específico, considere lo siguiente antes de poner todos los buzones de una organización en retención por juicio.
    
  - Cuando se usa el comando anterior para aplicar una retención a todos los buzones de una organización (o a un subconjunto de buzones que coinciden con un filtro de destinatarios especificado), solo se retienen los buzones que existen en el momento en que se ejecuta el comando. Si crea nuevos buzones más adelante, tiene que ejecutar el comando de nuevo para poner los nuevos buzones en retención. Si crea nuevos buzones con frecuencia, puede ejecutar el comando como una tarea programada con la frecuencia que necesite.
    
  - Poner todos los buzones en retención por juicio puede afectar significativamente al tamaño de los buzones. En una organización de Exchange Server 2013, planifique el almacenamiento adecuado para satisfacer los requisitos de conservación de su organización.
    
  - La carpeta elementos recuperables tiene su propio límite de almacenamiento, por lo que los elementos de la carpeta no se cuentan para el límite de almacenamiento del buzón. Como se explicó anteriormente, la preservación de los datos de buzones durante un largo período de tiempo tendrá como resultado el crecimiento de la carpeta elementos recuperables del buzón y el archivo de un usuario. Para adaptarse a este aumento en Exchange Online, la cuota de la carpeta elementos recuperables aumenta automáticamente de 30 GB a 100 GB cuando se pone un buzón de correo en retención por juicio. 
    
    En Exchange Server 2013, el límite de almacenamiento predeterminado para la carpeta elementos recuperables es también 30 GB. Le recomendamos que supervise periódicamente el tamaño de esta carpeta para asegurarse de que no llegue al límite. Para obtener más información, vea [carpeta elementos recuperables](http://technet.microsoft.com/library/efc48fb4-2ed8-4d05-93af-f3505fbc389d.aspx).
    
- El comando anterior para colocar una retención en todos los buzones utiliza un filtro de destinatarios que devuelve todos los buzones de usuario. Puede usar otras propiedades de destinatarios para devolver una lista de buzones específicos que puede canalizar después al cmdlet **Set-Mailbox** para poner esos buzones en retención por juicio. 
    
    Estos son algunos ejemplos de cómo usar los cmdlets **Get-Mailbox** y **Get-Recipient** para obtener un subconjunto de buzones en función de propiedades de usuarios o buzones. En estos ejemplos se da por hecho que las propiedades de buzón relevantes (como  _CustomAttributeN_ o  _Department_) se han rellenado.
    
  ```
  Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'CustomAttribute15 -eq "OneYearLitigationHold"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'Department -eq "HR"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'PostalCode -eq "98052"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'StateOrProvince -eq "WA"'
  ```

  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -ne "DiscoveryMailbox"}
  ```

    Puede usar otras propiedades de buzón de usuario en un filtro para incluir o excluir buzones de correo. Para obtener información detallada, vea [Filterable Properties for the -Filter Parameter](http://technet.microsoft.com/library/b02b0005-2fb6-4bc2-8815-305259fa5432.aspx).
    


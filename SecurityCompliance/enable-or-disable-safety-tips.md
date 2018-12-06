---
title: Habilitar o deshabilitar las sugerencias de seguridad en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7
description: Indica cómo habilitar y deshabilitar las sugerencias de seguridad en los mensajes de correo electrónico de los administradores de Office 365 y elevación de privilegios.
ms.openlocfilehash: 8e5d8bf1d2f831b5d74ca3accd8b434519bfeaab
ms.sourcegitcommit: 204fb0269b5c10b63941055824e863d77e3e9b02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2018
ms.locfileid: "27180860"
---
# <a name="enable-or-disable-safety-tips-in-office-365"></a>Habilitar o deshabilitar las sugerencias de seguridad en Office 365

Agrega Exchange Online Protection (EOP) o marcas, una seguridad sugerencia a los mensajes de correo electrónico que ofrece. Estas sugerencias de seguridad proporcionan los destinatarios con una forma rápida y visual para determinar si es un mensaje de forma segura comprobado remitente, si el mensaje se ha marcado como correo no deseado por Office 365, si el mensaje contiene algo sospechosos como un estafas de suplantación de identidad, o bien, si dispone de imágenes externas se ha bloqueado. Office 365 y los administradores de EOP independiente pueden modificar la configuración de directiva spam para habilitar o deshabilitar sugerencias de seguridad que no se muestren en el correo electrónico en Outlook y otros clientes de correo electrónico de escritorio. 
  
Office 365 permite sugerencias de seguridad para la organización de forma predeterminada y se recomienda que deje de ellos habilita para ayudar a combatir los ataques de correo no deseado y suplantación de identidad. No se puede deshabilitar sugerencias de seguridad para Outlook en el web.
  
Para ver ejemplos y para obtener más información acerca de la información que se muestra en sugerencias de seguridad, vea [sugerencias de seguridad en los mensajes de correo electrónico en Office 365.](safety-tips-in-office-365.md)
  
En este tema:
  
- [Para habilitar o deshabilitar sugerencias de seguridad mediante el uso de la seguridad de Office 365 &amp; centro de cumplimiento](enable-or-disable-safety-tips.md#SandCCsafetytip)
    
- [Para habilitar o deshabilitar sugerencias de seguridad mediante el uso de PowerShell](enable-or-disable-safety-tips.md#pshellsafetytip)
    
## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a>Para habilitar o deshabilitar sugerencias de seguridad mediante el uso de la seguridad de Office 365 &amp; centro de cumplimiento
<a name="SandCCsafetytip"> </a>

1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. Elija **administración de amenaza** \> **Directiva**. 
    
4. En la página **Directiva** , elija **contra correo no deseado**.
    
    ![Esta captura de pantalla muestra cómo llegar a la página de configuración contra correo no deseado en la seguridad &amp; centro de cumplimiento.](media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)
  
5. En la página **configuración de correo no deseado** , elija la ficha **personalizado** . 
    
    ![Esta captura de pantalla muestra la ubicación de la ficha personalizada en la página de configuración contra correo no deseado en la seguridad &amp; centro de cumplimiento.](media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)
  
6. Si es necesario, elija el modificador de **configuración personalizada** para activar la configuración personalizada. Si el modificador de configuración personalizada está establecido en **desactivado**, no podrá modificar directivas de filtro de correo no deseado.
    
    ![Esta captura de pantalla muestra los filtros contra correo no deseado personalizados desactivado de configuración de la directiva.](media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)
  
7. Expanda la directiva de correo que desea modificar y, a continuación, elija **Editar directiva**. Por ejemplo, elija la flecha hacia abajo junto a **spam predeterminada filtrar la directiva**. O bien, si lo desea, puede crear una nueva directiva mediante la opción **Agregar una directiva**.
    
8. Expanda acciones de **correo no deseado y masiva** . 
    
9. Para habilitar sugerencias de seguridad, en la sección **Sugerencias de seguridad**, active la casilla de verificación **en** . Para deshabilitar sugerencias de seguridad, desactive la casilla de verificación **en** . 
    
10. Elija **Guardar**.
    
## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a>Para habilitar o deshabilitar sugerencias de seguridad mediante el uso de PowerShell
<a name="pshellsafetytip"> </a>

Los administradores pueden utilizar Exchange Online PowerShell para habilitar o deshabilitar sugerencias de seguridad. Use el cmdlet Set-HostedContentFilterPolicy para habilitar o deshabilitar sugerencias de seguridad en una directiva de filtro de spam.
  
1. Conectarse a Exchange Online PowerShell. Para obtener información, vea [Connect to Exchange Online PowerShell](http://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Ejecute el cmdlet Set-HostedContentFilterPolicy para habilitar o deshabilitar sugerencias de seguridad:
    
  ```
  Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true|$false>
  ```

Donde:
    
  -  *nombre de la directiva* es el nombre de la directiva que desea modificar, por ejemplo **predeterminada**.
    
  -  `$true`permite sugerencias de seguridad para la directiva de filtro de spam. 
    
  -  `$false`deshabilita las sugerencias de seguridad para la directiva de filtro de spam. 
    
    Por ejemplo, para deshabilitar sugerencias de seguridad para la directiva de filtro de spam de forma predeterminada, ejecute el siguiente comando:
    
  ```
  PS C:\> Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
  ```

Para obtener más información acerca de este cmdlet, vea [Set-HostedContentFilterPolicy](https://technet.microsoft.com/library/jj200781.aspx).
    
## <a name="still-need-help"></a>¿Aún necesita ayuda?
<a name="pshellsafetytip"> </a>

Si deshabilita las sugerencias de seguridad, pero son todavía los ver en los mensajes de correo electrónico, compruebe estas cosas:
  
- No se puede deshabilitar sugerencias de seguridad para Outlook en el web. Intente ver el correo electrónico mismo en otro cliente, como Outlook.
    
- Sugerencias de seguridad se encuentran en de forma predeterminada para cada uno que usa EOP, esto incluye todas las personas que tiene Office 365. Con el fin de deshabilitar sugerencias de seguridad no se muestren en el correo electrónico, debe deshabilitar mediante una directiva de filtro de spam, tal como se describe en este tema. Una vez que ha configurado la directiva, asegúrese de que esté habilitado. Para obtener información acerca de cómo habilitar directivas de filtro de correo no deseado, consulte [configurar sus directivas de filtro de correo no deseado](https://technet.microsoft.com/library/jj200684.aspx).
    
Para que obtener más métodos combatir el correo no deseado y suplantación de identidad, consulte [Protección contra correo no deseado de Office 365 correo](anti-spam-protection.md).
  


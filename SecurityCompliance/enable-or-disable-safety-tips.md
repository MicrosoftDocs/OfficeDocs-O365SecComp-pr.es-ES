---
title: Habilitar o deshabilitar las sugerencias de seguridad en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7
description: Indica a Office 365 y a los administradores de EOP cómo habilitar y deshabilitar las sugerencias de seguridad en los mensajes de correo electrónico.
ms.openlocfilehash: f4e85b45c1483111d9edeb39d00d3f2cbafbf3ab
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215560"
---
# <a name="enable-or-disable-safety-tips-in-office-365"></a>Habilitar o deshabilitar las sugerencias de seguridad en Office 365

Exchange Online Protection (EOP) agrega o marca una sugerencia de seguridad a los mensajes de correo electrónico que entrega. Estas sugerencias de seguridad proporcionan a los destinatarios una forma rápida y visual de determinar si un mensaje proviene de un remitente protegido seguro, si el mensaje ha sido marcado como correo no deseado por Office 365, si el mensaje contiene algo sospechoso, como una estafa de suplantación de identidad (phishing), o si las imágenes externas tienen se ha bloqueado. Office 365 y EOP: los administradores independientes pueden editar una configuración de directiva de correo no deseado para habilitar o deshabilitar las sugerencias de seguridad para que no se muestren en el correo electrónico en Outlook y en otros clientes de correo electrónico de escritorio. 
  
Office 365 habilita sugerencias de seguridad de forma predeterminada para su organización y le recomendamos que las deje habilitadas para luchar contra el correo no deseado y los ataques de suplantación de identidad. No puede deshabilitar las sugerencias de seguridad para Outlook en la Web.
  
Para ver ejemplos y obtener información sobre la información que se muestra en sugerencias de seguridad, vea [sugerencias de seguridad en los mensajes de correo electrónico en Office 365.](safety-tips-in-office-365.md)
  
En este tema:
  
- [Para habilitar o deshabilitar las sugerencias de seguridad mediante el centro &amp; de seguridad y cumplimiento de Office 365](enable-or-disable-safety-tips.md#SandCCsafetytip)
    
- [Para habilitar o deshabilitar las sugerencias de seguridad con PowerShell](enable-or-disable-safety-tips.md#pshellsafetytip)
    
## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a>Para habilitar o deshabilitar las sugerencias de seguridad mediante el centro &amp; de seguridad y cumplimiento de Office 365
<a name="SandCCsafetytip"> </a>

1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. Elija **** \> **Directiva**de administración de amenazas. 
    
4. En la página **Directiva** , elija **anti-spam**.
    
    ![En esta captura de pantalla se muestra cómo obtener acceso a la página Configuración de correo &amp; no deseado en el centro de seguridad y cumplimiento.](media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)
  
5. En la página **configuración contra correo no deseado,** elija la pestaña **personalizado** . 
    
    ![Esta captura de pantalla muestra la ubicación de la pestaña personalizada en la página Configuración contra correo no deseado &amp; del centro de seguridad y cumplimiento.](media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)
  
6. Si es necesario, elija el modificador de **configuración personalizado** para activar la configuración personalizada. Si el modificador de configuración personalizado está **** desactivado, no podrá modificar las directivas de filtro de correo no deseado.
    
    ![Esta captura de pantalla muestra la configuración de directiva de filtro contra correo no deseado personalizada desactivada.](media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)
  
7. ExPanda la Directiva de correo no deseado que desea modificar y, a continuación, elija **Editar Directiva**. Por ejemplo, seleccione la flecha abajo junto a **Directiva de filtro de correo no deseado predeterminada**. O bien, si lo desea, puede crear una nueva Directiva eligiendo **Agregar una directiva**.
    
8. ExPanda **correo no deseado y** acciones en masa. 
    
9. Para habilitar las sugerencias de seguridad, en **sugerencias de seguridad**, active la casilla **de verificación activado** . Para deshabilitar las sugerencias de seguridad, desactive la casilla **de verificación activado** . 
    
10. Elija **Guardar**.
    
## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a>Para habilitar o deshabilitar las sugerencias de seguridad con PowerShell
<a name="pshellsafetytip"> </a>

Los administradores pueden usar Exchange Online PowerShell para habilitar o deshabilitar las sugerencias de seguridad. Use el cmdlet Set-HostedContentFilterPolicy para habilitar o deshabilitar las sugerencias de seguridad en una directiva de filtro de correo no deseado.
  
1. Conéctese a Exchange Online PowerShell. Para obtener más información, vea [conectarse a Exchange Online PowerShell](http://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Ejecute el cmdlet Set-HostedContentFilterPolicy para habilitar o deshabilitar las sugerencias de seguridad:
    
  ```
  Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true|$false>
  ```

Donde:
    
  -  *nombre de directiva* es el nombre de la Directiva que desea modificar; por ejemplo, **default**.
    
  -  `$true`habilita las sugerencias de seguridad para la Directiva de filtro de correo no deseado. 
    
  -  `$false`deshabilita las sugerencias de seguridad para la Directiva de filtro de correo no deseado. 
    
    Por ejemplo, para deshabilitar las sugerencias de seguridad para la Directiva de filtro de correo no deseado predeterminada, ejecute el siguiente comando:
    
  ```
  PS C:\> Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
  ```

Para obtener más información sobre este cmdlet, vea [set-HostedContentFilterPolicy](https://technet.microsoft.com/library/jj200781.aspx).
    
## <a name="still-need-help"></a>¿Aún necesita ayuda?
<a name="pshellsafetytip"> </a>

Si ha deshabilitado las sugerencias de seguridad, pero sigue apareciendo en los mensajes de correo electrónico, compruebe lo siguiente:
  
- No puede deshabilitar las sugerencias de seguridad para Outlook en la Web. Pruebe a ver el mismo correo electrónico en otro cliente, como Outlook.
    
- Las sugerencias de seguridad están habilitadas de forma predeterminada para cada uno que usa EOP, esto incluye a todos los usuarios que tienen Office 365. Para deshabilitar las sugerencias de seguridad y que no se muestren en el correo electrónico, debe deshabilitarlas mediante una directiva de filtro de correo no deseado, como se describe en este tema. Una vez configurada la Directiva, asegúrese de que está habilitada. Para obtener información sobre cómo habilitar las directivas de filtro de correo no deseado, consulte [configurar las directivas de filtro de correo no deseado](https://technet.microsoft.com/library/jj200684.aspx).
    
Para obtener más información sobre cómo combatir el correo no deseado y el phishing, consulte [Office 365 email anti-spam protection](anti-spam-protection.md).
  


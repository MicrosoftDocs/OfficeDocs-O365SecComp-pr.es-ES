---
title: Instalar el complemento de notificación de correo no deseado para Microsoft Outlook
ms.author: MSFTTracyP
author: tracyp
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8dcc752f-e22e-44ce-a104-4cc4d7e439f3
ms.collection:
- M365-security-compliance
description: En esta articleSupported LanguagesInstall el informe de correo electrónico no deseado Add-inUninstall el complemento de notificación de correo no deseado Add-inFor más información
ms.openlocfilehash: b29bd367ca168ff45d983796b8ae6e68ee9df297
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276310"
---
# <a name="install-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>Instalar el complemento de notificación de correo no deseado para Microsoft Outlook
  
En este tema se describe cómo instalar y desinstalar el complemento de notificación de correo no deseado de Microsoft para Outlook en los equipos cliente de una organización. La versión actual del complemento (enero de 2016) incluye soporte para Outlook 2016, Outlook 2013, Outlook 2010 y Outlook 2007. 
  
El complemento (para todos los idiomas admitidos) permite notificar el correo electrónico no deseado directamente desde la cinta de Outlook. La versión en inglés del complemento incluye opciones adicionales para notificar problemas relacionados con el correo electrónico a Microsoft, directamente desde la cinta de opciones:
  
-   Notificar los correos de suplantación de identidad (phishing) recibidos 
    
- Notificar los correos electrónicos identificados incorrectamente como correo no deseado.
    
## <a name="supported-languages"></a>Idiomas admitidos
<a name="sectionSection0"> </a>

El complemento de notificación de correo no deseado admite los siguientes idiomas: 
  
- chino simplificado
    
- chino tradicional
    
- Holandés
    
- Inglés
    
- Francés
    
- Alemán
    
- Italiano
    
- Japonés
    
- Coreano
    
- Portugués
    
- Portugués (Brasil)
    
- Español
    
## <a name="install-the-junk-email-reporting-add-in"></a>Instalar el complemento de notificación de correo no deseado
<a name="sectionSection1"> </a>

Puede instalar el complemento de notificación de correo no deseado:
  
- Mediante la ejecución del paquete de Windows Installer, al igual que con cualquier otro archivo .msi. Al instalar el complemento, se abre una interfaz gráfica de usuario que le guía por los pasos a través de las pantallas de instalación. Para obtener más información, consulte [Instalar el complemento de notificación de correo no deseado mediante el Asistente para instalación](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#BKMK_InstalltheJunkEmailReportingAdd-InUsingtheSetupWizard). O BIEN
    
- Mediante la ejecución de una instalación silenciosa que suprime la interfaz de usuario de la instalación. Otro método consiste en especificar las opciones de la línea de comandos que ejecutan un script de instalación. Al instalar el complemento, aparecen otras opciones de configuración que no están disponibles a través de la interfaz gráfica de usuario. Para obtener más información, consulte [Instalar el complemento de notificación de correo no deseado en modo silencioso](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#BKMK_InstalltheJunkEmailReportingAdd-IninSilentMode).
    
### <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

La instalación del complemento de notificación de correo no deseado de Microsoft para Microsoft Outlook requiere:
  
- Uno de los siguientes sistemas operativos: Windows 10, Windows 8.1, Windows 8, Windows 7 Service Pack 1, Windows 10 Server, Windows Server 2012 R2, Windows Server 2012 o Windows Server 2008 R2
    
- Outlook 2016, Outlook 2013, Outlook 2010 o Outlook 2007 (Service Pack 2 o posterior)
    
- Ensamblados de interoperabilidad primarios de Microsoft Office: 
    
  - Para descargar los ensamblados de interoperabilidad primarios para Microsoft Office 2010 o posterior, vaya al [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/?LinkID=166026).
    
  - Para descargar los ensamblados de interoperabilidad primarios para Microsoft Office 2007, vaya al [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/?LinkId=72637).
    
- Microsoft .NET Framework [versión 2.0](https://go.microsoft.com/fwlink/?LinkID=208706).
    
> [!NOTE]
> Debe tener permisos de administrador en el equipo en el que vaya a instalar el complemento. 
  
### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>Instalar el complemento de notificación de correo no deseado mediante el Asistente para instalación
<a name="BKMK_InstalltheJunkEmailReportingAdd-InUsingtheSetupWizard"> </a>

1. En el equipo, cierre Outlook.
    
2. Vaya a la página del Centro de descarga de Microsoft del complemento de notificación de correo no deseado de Microsoft para Microsoft Outlook [https://go.microsoft.com/fwlink/?LinkID=147248](https://go.microsoft.com/fwlink/?LinkID=147248) y descargue el archivo .msi. 
    
3. Haga doble clic en el archivo .msi. 
    
4. En la página de **bienvenida a la instalación del complemento de notificación de correo no deseado de Microsoft**, haga clic en **Siguiente**. 
    
5. Lea el contrato de licencia y, a continuación, haga clic en **Acepto los términos del contrato de licencia** si acepta los términos de la instalación (necesario para continuar con la instalación). Haga clic en **Siguiente** para continuar. 
    
6. Cuando el asistente se haya completado, haga clic en **Finalizar**. 
    
7. Inicie Outlook.
    
8. Busque el botón **Correo no deseado** en la cinta de Outlook. Ahora podrá notificar mensajes de correo no deseado a Microsoft seleccionando los mensajes de correo no deseado en la Bandeja de entrada y haciendo clic en el botón de **Informar de correo no deseado**. 
    
9. Elija la flecha abajo que aparece junto a **Correo no deseado** para ver más opciones, como **Notificar como suplantación de identidad (phishing)** si desea informar a Microsoft sobre correos de suplantación de identidad (phishing). En la carpeta de correo no deseado, también puede seleccionar **Notificar como correo deseado** si un correo electrónico se ha identificado incorrectamente como correo no deseado. 
    
### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>Instalar el complemento de notificación de correo no deseado en modo silencioso
<a name="BKMK_InstalltheJunkEmailReportingAdd-IninSilentMode"> </a>

1. En el equipo, cierre Outlook.
    
2. Abra un símbolo del sistema.
    
3. Si desea instalar el complemento de forma directa, sin parámetros opcionales, especifique lo siguiente:
    
  - Equipos que ejecuten Outlook x86:  `msiexec /qn /i JunkReportingAdd-in.x86-en.msi`
    
  - Equipos que ejecuten Outlook x64:  `msiexec /qn /i JunkReportingAdd-in.x64-en.msi`
    
    También puede especificar los parámetros opcionales MaxMessageSelection y BccEmailAddress:
    
  - MaxMessageSelection Permite a los administradores definir el número máximo de mensajes que los usuarios pueden seleccionar para el envío con un solo clic. El intervalo oscila entre 1 y 50 mensajes, y el valor predeterminado es 10 mensajes.
    
    Ejemplo: Si desea establecer el número máximo de mensajes que los usuarios pueden seleccionar para el envío con un solo clic en 16, use la siguiente opción como parte del comando de instalación:  `MaxMessageSelection=16`
    
  - BccEmailAddress Permite a los administradores configurar un buzón para recibir una copia de los envíos de los usuarios mediante la especificación de una dirección de correo electrónico en el cuadro CCO. Una vez configurado el buzón, se envía una copia de todos los correos electrónicos enviados a BccEmailAddress. En caso contrario, la configuración predeterminada es no tener ninguna dirección de correo electrónico en el cuadro CCO.
    
    Ejemplo: Si desea usar junkReports@contoso.com como la dirección de correo electrónico del cuadro CCO para todos los envíos, utilice el siguiente comando:  `BccEmailAddress="junkReports@contoso.com"`
    
    > [!NOTE]
    > Para establecer varias direcciones de correo electrónico CCO, sepárelas mediante punto y coma. Ejemplo:  `BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"`
  
    Para agregar ambos parámetros opcionales en función de los ejemplos anteriores, especifique lo siguiente para un equipo que ejecute Outlook x86: 
    
  ```
  msiexec /qn /i JunkReportingAdd-in.x86-en.msi. MaxMessageSelection=16 BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"
  ```

4. Después de completar la instalación, inicie Outlook.
    
5. Busque el botón **Correo no deseado** en la cinta de Outlook. Ahora podrá notificar mensajes de correo no deseado a Microsoft seleccionando los mensajes de correo no deseado en la Bandeja de entrada y haciendo clic en el botón de **Informar de correo no deseado**. 
    
6. Elija la flecha abajo que aparece junto a **Correo no deseado** para ver más opciones, como **Notificar como suplantación de identidad (phishing)** si desea informar a Microsoft sobre correos de suplantación de identidad (phishing). En la carpeta de correo no deseado, también puede seleccionar **Notificar como correo deseado** si un correo electrónico se ha identificado incorrectamente como correo no deseado. 
    
## <a name="uninstall-the-junk-email-reporting-add-in"></a>Desinstalar el complemento de notificación de correo no deseado
<a name="sectionSection2"> </a>

Use una de estas opciones para desinstalar el complemento de notificación de correo no deseado:
  
- Quite el complemento mediante el Panel de control de Windows. Para obtener más información, consulte [Desinstalar el complemento de notificación de correo no deseado desde el Panel de control](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#BKMK_UninstalltheJunkEmailReportingAdd-infromControlPanel). O BIEN
    
- Ejecute el paquete de Windows Installer y seleccione la opción de desinstalar. Para obtener más información, consulte [Desinstalar el complemento de notificación de correo no deseado mediante la ejecución del paquete de Windows Installer](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#BKMK_UninstalltheJunkEmailReportingAddinbyRunningtheWindowsInstallerPackage). O BIEN
    
- Ejecute una instalación silenciosa mediante la opción de desinstalar. Para obtener más información, consulte [Desinstalar el complemento de notificación de correo no deseado en modo silencioso](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#MK_UninstalltheJunkEmailReportingAdd-ininSilentMode).
    
> [!NOTE]
> Debe tener permisos de administrador en el equipo en el que vaya a desinstalar el complemento. 
  
### <a name="uninstall-the-junk-email-reporting-add-in-from-control-panel"></a>Desinstalar el complemento de notificación de correo no deseado desde el Panel de control
<a name="BKMK_UninstalltheJunkEmailReportingAdd-infromControlPanel"> </a>

1. En el equipo, cierre Outlook.
    
2. En el menú Inicio del equipo, seleccione **Panel de control**.
    
3. Seleccione **Programas y características**.
    
4. Seleccione el **complemento de notificación de correo no deseado de Microsoft para Microsoft Office Outlook**.
    
5. Elija **Desinstalar**.
    
6. Inicie Outlook de nuevo para comprobar que el complemento ya no aparece en la cinta de Outlook.
    
### <a name="uninstall-the-junk-email-reporting-add-in-by-running-the-windows-installer-package"></a>Desinstalar el complemento de notificación de correo no deseado mediante la ejecución del paquete de Windows Installer
<a name="BKMK_UninstalltheJunkEmailReportingAddinbyRunningtheWindowsInstallerPackage"> </a>

1. En el equipo, cierre Outlook.
    
    > [!NOTE]
    > Si se ejecuta Outlook durante el proceso de desinstalación, deberá reiniciarlo para que el complemento se desinstale por completo. 
  
2. Vuelva a ejecutar el archivo .msi que ejecutó anteriormente para instalar el complemento. 
    
    (Vaya a la página del Centro de descarga de Microsoft del complemento de notificación de correo no deseado de Microsoft para Microsoft Outlook [https://go.microsoft.com/fwlink/?LinkId=147248](https://go.microsoft.com/fwlink/?LinkId=147248), descargue el archivo .msi y, a continuación, haga doble clic en él.) 
    
3. Siga las instrucciones para desinstalar el complemento.
    
4. Inicie Outlook de nuevo para comprobar que el complemento ya no aparece en la cinta de Outlook.
    
### <a name="uninstall-the-junk-email-reporting-add-in-in-silent-mode"></a>Desinstalar el complemento de notificación de correo no deseado en modo silencioso
<a name="MK_UninstalltheJunkEmailReportingAdd-ininSilentMode"> </a>

1. En el equipo, cierre Outlook.
    
    > [!NOTE]
    > Si se ejecuta Outlook durante el proceso de desinstalación, deberá reiniciarlo para que el complemento se desinstale por completo. 
  
2. Abra un símbolo del sistema.
    
3. Especifique el siguiente parámetro de la línea de comandos:
    
    Equipos que ejecuten Outlook x86:  `msiexec /x JunkReportingAdd-in.x86-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`
    
    Equipos que ejecuten Outlook x64:  `msiexec /x JunkReportingAdd-in.x64-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`
    
4. Inicie Outlook de nuevo para comprobar que el complemento ya no aparece en la cinta de Outlook.
    
## <a name="for-more-information"></a>Más información
<a name="sectionSection3"> </a>

[Informar a Microsoft de los mensajes de correo electrónico no deseado](report-junk-email-messages-to-microsoft.md)
  
[Solución de problemas e información de soporte técnico](troubleshooting-and-support-information.md)
  


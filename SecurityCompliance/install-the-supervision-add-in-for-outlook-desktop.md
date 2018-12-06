---
title: Instalar el complemento de supervisión de Outlook para escritorio
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- ZOL160
ms.assetid: 6c5620e6-aba3-4910-8f3a-b55451656ff7
description: Instalar el complemento de supervisión de Office 365 para la versión de escritorio de Outlook
ms.openlocfilehash: b0cb0d78ab5f8887628528dd53b49fb15de44126
ms.sourcegitcommit: 204fb0269b5c10b63941055824e863d77e3e9b02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2018
ms.locfileid: "27180870"
---
# <a name="install-the-supervision-add-in-for-outlook-desktop"></a>Instalar el complemento de supervisión de Outlook para escritorio

Para revisar las comunicaciones identificadas por una directiva de supervisión, uso de revisores el complemento de supervisión para Outlook y Outlook web app. El complemento se instala automáticamente en Outlook web app para todos los revisores especificados en la directiva. Sin embargo, deben ejecutar los revisores a través de algunos pasos para instalar en la versión de escritorio de Outlook.
  
> [!NOTE]
> Los usuarios supervisados por las directivas de supervisión deben tener una licencia de acceso E3 Enterprise de Office 365 con el complemento de cumplimiento avanzadas o estar incluidos en una suscripción a Office 365 Enterprise E5. Si no tiene un plan de empresa E5 existente y desea probar supervisión, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).
  
## <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a>Paso 1: Copiar la dirección para el buzón de supervisión

Para instalar el complemento para escritorio de Outlook, necesitará la dirección para el buzón de supervisión que se creó como parte de la configuración de directiva de supervisión.
  
> [!NOTE]
> Si otra persona creó la directiva, debe obtener esta dirección de ellas para instalar el complemento.
 
 **Para buscar la dirección del buzón de correo de supervisión**
  
1. Inicie sesión en la [seguridad &amp; centro de cumplimiento](https://protection.office.com) uso de credenciales para una cuenta de administrador de la organización de Office 365.
    
2. Vaya a la **gobernanza de datos** \> **supervisión**.
    
3. Haga clic en la directiva de supervisión que está recopilando a las comunicaciones que desee revisar.
    
4. En la directiva se detallan emergente, en ** buzón supervisión **, copie la dirección.<br/>![La sección 'Buzón de correo de supervisión' de emergente de detalles de una directiva de supervisión que muestra la dirección del buzón de correo de supervisión resaltada](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
## <a name="step-2-configure-the-supervision-mailbox-for-outlook-desktop-access"></a>Paso 2: Configurar el buzón de supervisión para el acceso al escritorio de Outlook

A continuación, los revisores tendrá que ejecutar los comandos de PowerShell en Exchange Online un par para que puedan conectarse a Outlook en el buzón de supervisión.
  
1. Conectarse a Exchange Online PowerShell. [¿Cómo hacerlo?](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)
    
2. Ejecute los comandos siguientes, donde *SupervisoryReview{GUID}@domain.onmicrosoft.com* es la dirección que copió en el paso 1 más arriba, y el *usuario* es el nombre del revisor que van a conectar con el buzón de correo de supervisión en el paso 3.
    - ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```<br/>
    - ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```
    
3. Espere al menos una hora antes de pasar al paso 3 por debajo.
    
## <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a>Paso 3: Crear un perfil de Outlook para conectar con el buzón de supervisión

Para el paso final, revisores será necesario crear un perfil de Outlook para conectar con el buzón de supervisión.
 
> [!NOTE]
> Para crear un nuevo perfil de Outlook, usará la configuración de correo en el Panel de Control de Windows. La ruta de acceso que hay que realizar para tener acceso a estas opciones es posible que dependen de qué sistema operativo de Windows (Windows 7, Windows 8 o Windows 10) utiliza y se instala la versión de Outlook.
  
1. Abra el Panel de Control y, en el cuadro de **búsqueda** en la parte superior de la ventana, escriba **correo**.<br/>¿(No está seguro de cómo obtener el panel de Control? Vea [donde es el Panel de Control?](https://support.microsoft.com/help/13764/windows-where-is-control-panel))
  
2. Abra la aplicación de **correo** .
    
3. En la **Configuración de correo - Outlook**, haga clic en **Mostrar perfiles**.<br/>![La 'configuración de correo - Outlook' cuadro de diálogo con el botón 'Mostrar perfiles' resaltado](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)
  
4. En **correo**, haga clic en **Agregar**. A continuación, en **Nuevo perfil**, escriba un nombre para el buzón de correo de supervisión (por ejemplo, **supervisión**).<br/>![El cuadro de diálogo 'Nuevo perfil' que muestra el nombre 'Supervisión' en el cuadro Nombre del perfil](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)
  
5. En **Outlook conectarse a Office 365**, haga clic en **Conectar a una cuenta diferente**.<br/>![El mensaje 'Outlook conectarse a Office 365' con el vínculo 'Conectar con una cuenta diferente' resaltado](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)
  
6. En la **Configuración automática de cuenta**, elija **el programa de instalación Manual o tipos de servidores adicionales**y, a continuación, haga clic en **siguiente**.
    
7. En **Elija el tipo de cuenta**, elija **Office 365**. A continuación, en el cuadro **Dirección de correo electrónico** , escriba la dirección del buzón de supervisión que copió anteriormente.<br/>![La página 'Elija su tipo de cuenta' del cuadro de diálogo 'Agregar cuenta' en Outlook que muestra el cuadro 'Dirección de correo electrónico' resaltado.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)
  
8. Cuando se le solicite, escriba sus credenciales de Office 365.
    
9. Si tiene éxito, verá el **supervisión - \<nombre de la directiva\> ** carpeta que aparecen en la vista lista de carpetas de Outlook.
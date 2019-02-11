---
title: Administrar el cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
description: Una vez que haya terminado la configuración de seguridad de Office 365 Message Encryption (OME), puede personalizar la configuración de la implementación en un número de formas. Por ejemplo, puede configurar si se debe habilitar códigos de acceso única, mostrar el botón Proteger en Outlook en el web y mucho más. Las tareas en este artículo se describen cómo.
ms.openlocfilehash: 6a9eddae2d3d166d96979d88b15845c3b7379bd9
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29696234"
---
# <a name="manage-office-365-message-encryption"></a>Administrar el cifrado de mensajes de Office 365

Una vez que haya terminado la configuración de seguridad de Office 365 Message Encryption (OME), puede personalizar la configuración de la implementación en un número de formas. Por ejemplo, puede configurar si se debe habilitar códigos de acceso única, mostrar el botón **proteger** en Outlook en el web y mucho más. Las tareas en este artículo se describen cómo.
  
||
|:-----|
|En este artículo es parte de una serie de artículos sobre Office 365 Message Encryption más grande. En este artículo está destinada a los administradores y profesionales de TI. Si sólo está buscando información en enviar o recibir un mensaje cifrado, vea la lista de los artículos de [Office 365 Message Encryption (OME)](ome.md) y busque el artículo que mejor se adapte a sus necesidades. |
||

## <a name="managing-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Administración de si los destinatarios de Google, Yahoo y Account de Microsoft pueden utilizar estas cuentas para iniciar sesión en el portal de cifrado de mensajes de Office 365

De forma predeterminada, al configurar las nuevas capacidades de cifrado de mensajes de Office 365, los usuarios de su organización pueden enviar mensajes a los destinatarios que están fuera de su organización de Office 365. Si el destinatario usa un *identificador sociales* como una cuenta de Google, Yahoo cuenta o cuenta de Microsoft, el destinatario puede iniciar sesión en el portal de OME con el identificador sociales. Si lo desea, puede elegir no permitir a los destinatarios usar los identificadores de sociales para iniciar sesión en el portal de OME.
  
### <a name="to-manage-whether-or-not-to-allow-recipients-to-use-social-ids-to-sign-in-to-the-ome-portal"></a>Para administrar si o no permitir a los destinatarios usar los identificadores de sociales para iniciar sesión en el portal de OME
  
1. [Conectarse a Exchange Online mediante PowerShell remoto](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).

2. Ejecute el cmdlet Set-OMEConfiguration con el parámetro SocialIdSignIn como sigue:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -SocialIdSignIn <$true | $false>
   ```

   Por ejemplo, para deshabilitar los identificadores sociales:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   Para habilitar los identificadores sociales:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="managing-the-use-of-one-time-pass-codes-for-signing-in-to-the-office-365-message-encryption-portal"></a>Administrar el uso de códigos de acceso única para iniciar sesión en el portal de cifrado de mensajes de Office 365

De forma predeterminada, si el destinatario de un mensaje cifrado por OME no utiliza Outlook, independientemente de la cuenta utilizada por el destinatario, el destinatario recibe un vínculo de la vista web de tiempo limitado que les permite leer el mensaje. Esto incluye un código de acceso única. Como administrador, puede administrar independientemente de si o no códigos de acceso única pueden usarse para iniciar sesión en el portal de OME.
  
### <a name="to-manage-whether-or-not-one-time-pass-codes-are-generated-for-ome"></a>Para administrar o si no se generan códigos de acceso única para OME
  
1. Uso de una cuenta de trabajo o escuela que tiene permisos de administrador global de la organización de Office 365, iniciar una sesión de Windows PowerShell y conectarse a Exchange Online. Para obtener instrucciones, vea [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Ejecute el cmdlet Set-OMEConfiguration con el parámetro OTPEnabled:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   Por ejemplo, para deshabilitar los códigos de acceso única:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   Para habilitar códigos de acceso única:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="managing-the-display-of-the-protect-button-in-outlook-on-the-web"></a>Administración de la visualización del botón Protect en Outlook en la web

De forma predeterminada, no está habilitado el botón **proteger** en Outlook en el web al configurar OME. Como administrador, puede administrar si se deben mostrar en este botón para los usuarios finales.
  
### <a name="to-manage-whether-or-not-the-protect-button-appears-in-outlook-on-the-web"></a>Para administrar si aparece o no el botón Proteger en Outlook en el web
  
1. Uso de una cuenta de trabajo o escuela que tiene permisos de administrador global de la organización de Office 365, iniciar una sesión de Windows PowerShell y conectarse a Exchange Online. Para obtener instrucciones, vea [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Ejecute el cmdlet Set-IRMConfiguration con el parámetro - SimplifiedClientAccessEnabled:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   Por ejemplo, para deshabilitar el botón **proteger** :

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   Para habilitar el botón **proteger** :

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>Habilitar el descifrado del servicio de mensajes de correo electrónico para los usuarios de aplicación de correo de iOS

La aplicación de correo de iOS no puede descifrar mensajes protegidos con cifrado de mensajes de Office 365. Como administrador de Office 365, puede aplicar el descifrado del servicio para los mensajes entregados a la aplicación de correo de iOS. Cuando se decide hacer esto, el servicio envía una copia del mensaje descifrada al dispositivo iOS. El mensaje se almacena descifrar en el dispositivo de cliente. El mensaje también conserva información acerca de los derechos de uso, aunque la aplicación de correo de iOS no aplica los derechos de uso de lado cliente para el usuario. Esto significa que el usuario puede copiar o imprimir el mensaje incluso si originalmente no tiene los derechos necesarios para hacerlo. Sin embargo, si el usuario intenta para llevar a cabo una acción que requiere el servidor de correo de Office 365, como reenviar el mensaje, el servidor no permitirá la acción si el usuario no tenía originalmente el derecho de uso para hacerlo. Sin embargo, los usuarios finales pueden evitar restricción de uso no reenviar por reenviar el mensaje desde una cuenta diferente en su aplicación de correo de iOS independientemente de si configurado la descifrado del servicio de correo, los datos adjuntos para cifrar y derechos de correo protegido no pueden verse en la aplicación de correo de iOS.
  
Si decide no permitir que los mensajes descifrados se envíen a usuarios de la aplicación de correo de iOS, los usuarios reciben un mensaje que indica que no tienen derechos para ver el mensaje. De forma predeterminada, no está habilitado el descifrado del servicio de mensajes de correo electrónico.
  
Para obtener más información y para una vista de la experiencia del cliente, vea [vista cifra los mensajes en su iPhone o iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).
  
### <a name="to-manage-whether-or-not-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>Para administrar usuarios de la aplicación de correo de iOS o no puede ver los mensajes protegidos por el cifrado de mensajes de Office 365
  
1. Uso de una cuenta de trabajo o escuela que tiene permisos de administrador global de la organización de Office 365, iniciar una sesión de Windows PowerShell y conectarse a Exchange Online. Para obtener instrucciones, vea [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Ejecute el cmdlet Set-ActiveSyncOrganizations con el parámetro AllowRMSSupportForUnenlightenedApps:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   Por ejemplo, para configurar el servicio para descifrar los mensajes antes de que se envíen a las aplicaciones unenlightened como iOS aplicación de correo:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   O bien, para configurar el servicio para que no envíe mensajes descifrados a las aplicaciones unenlightened:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Habilitar descifrado del servicio de datos adjuntos de correo electrónico para los clientes de correo de explorador web

Normalmente, cuando se usa el cifrado de mensajes de Office 365, automáticamente se cifran los datos adjuntos. Como administrador de Office 365, puede aplicar el descifrado del servicio para los datos adjuntos de correo electrónico que los usuarios descargar desde un explorador web.
  
Si opta por hacer esto, el servicio envía una copia descifrada del archivo en el dispositivo. El mensaje aún está cifrado. Los datos adjuntos de correo electrónico también conserva información acerca de los derechos de uso, aunque el explorador no se aplican los derechos de uso de lado cliente para el usuario. Esto significa que el usuario puede copiar o imprimir los datos adjuntos de correo electrónico incluso si originalmente no tiene los derechos necesarios para hacerlo. Sin embargo, si el usuario intenta para llevar a cabo una acción que requiere que el servidor de correo de Office 365, como la transferencia de los datos adjuntos, el servidor no permitirá la acción si el usuario no tenía originalmente el derecho de uso para hacerlo.
  
Independientemente de si configurado descifrado del servicio de datos adjuntos, los datos adjuntos al cifran y correo protegido con derechos no pueden verse en la aplicación de correo de iOS.
  
Si decide no permitir datos adjuntos de correo electrónico descifrado, que es el valor predeterminado, los usuarios reciben un mensaje que indica que no tienen derechos para ver los datos adjuntos.
  
Para obtener más información acerca de cómo Office 365 implementa el cifrado de mensajes de correo electrónico y datos adjuntos de correo electrónico con la opción sólo cifrar, vea [opción sólo cifrar para los correos electrónicos.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-or-not-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>Para administrar o no los datos adjuntos de correo electrónico se descifran al descargarlos desde un explorador web
  
1. Uso de una cuenta de trabajo o escuela que tiene permisos de administrador global de la organización de Office 365, iniciar una sesión de Windows PowerShell y conectarse a Exchange Online. Para obtener instrucciones, vea [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Ejecute el cmdlet Set-IRMConfiguration con el parámetro DecryptAttachmentFromPortal:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   Por ejemplo configurar el servicio para descifrar los datos adjuntos de correo electrónico cuando un usuario para descargarlas desde un explorador web:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   Para configurar el servicio para dejar los datos adjuntos de correo electrónico cifrado, tal y como están al descargar:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="customizing-the-appearance-of-email-messages-and-the-ome-portal"></a>Personalizar la apariencia de los mensajes de correo electrónico y el portal de OME

Para obtener información detallada acerca de cómo se puede personalizar OME para su organización, vea [Agregar marca de su organización a los mensajes cifrados](add-your-organization-brand-to-encrypted-messages.md).
  
## <a name="disabling-the-new-capabilities-for-ome"></a>Deshabilitación de las nuevas capacidades para OME

Esperamos que no se incluyen a ella, pero si es necesario, deshabilitar las nuevas capacidades para OME es muy sencillo. En primer lugar, necesitará quitar las reglas de flujo de correo se ha creado que utilice las nuevas capacidades OME. Para obtener información sobre cómo quitar las reglas de flujo de correo, vea [Administrar reglas de flujo de correo](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx). A continuación, siga estos pasos en Exchange Online PowerShell.
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>Para deshabilitar las nuevas capacidades para OME
  
1. Uso de una cuenta de trabajo o escuela que tiene permisos de administrador global de la organización de Office 365, iniciar una sesión de Windows PowerShell y conectarse a Exchange Online. Para obtener instrucciones, vea [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Si se habilita el botón **proteger** de Outlook en la web, deshabilitar, ejecute el cmdlet Set-IRMConfiguration con el parámetro SimplifiedClientAccessEnabled. De lo contrario, omita este paso.

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. Deshabilitar las nuevas capacidades para OME, ejecute el cmdlet Set-IRMConfiguration con el parámetro AzureRMSLicensingEnabled establecido en false:

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```

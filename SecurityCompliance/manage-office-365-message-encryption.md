---
title: Administrar el cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Una vez que haya terminado de configurar el cifrado de mensajes de Office 365 (OME), puede personalizar la configuración de la implementación de varias maneras. Por ejemplo, puede configurar si desea habilitar códigos de paso de una sola vez, mostrar el botón proteger en Outlook en la web y más. Las tareas de este artículo describen cómo hacerlo.
ms.openlocfilehash: 1afaaea3cd744878630598acd3f02dc7dc70e9cb
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2019
ms.locfileid: "33834929"
---
# <a name="manage-office-365-message-encryption"></a>Administrar el cifrado de mensajes de Office 365

Una vez que haya terminado de configurar el cifrado de mensajes de Office 365 (OME), puede personalizar la configuración de la implementación de varias maneras. Por ejemplo, puede configurar si desea habilitar códigos de paso de una sola vez, mostrar el botón **proteger** en Outlook en la web y más. Las tareas de este artículo describen cómo hacerlo.

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Administrar si los destinatarios de cuentas de Google, Yahoo y Microsoft pueden usar estas cuentas para iniciar sesión en el portal de cifrado de mensajes de Office 365

Cuando se configuran las nuevas capacidades de cifrado de mensajes de Office 365, los usuarios de la organización pueden enviar mensajes a destinatarios que están fuera de la organización de Office 365. Si el destinatario usa un *identificador social* , como una cuenta de Google, una cuenta de Yahoo o una cuenta de Microsoft, el destinatario puede iniciar sesión en el portal de OME con un identificador social. Si lo desea, puede optar por no permitir que los destinatarios usen identificadores sociales para iniciar sesión en el portal de OME.
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>Para administrar si los destinatarios pueden usar identificadores sociales para iniciar sesión en el portal de OME
  
1. [Conéctese a Exchange online mediante PowerShell remoto](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).

2. Ejecute el cmdlet Set-OMEConfiguration con el parámetro SocialIdSignIn de la siguiente manera:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   Por ejemplo, para deshabilitar los identificadores sociales:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   Para habilitar los identificadores sociales:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>Administrar el uso de códigos de paso de una sola vez para el portal de cifrado de mensajes de Office 365

Si el destinatario de un mensaje cifrado por OME no usa Outlook, independientemente de la cuenta usada por el destinatario, el destinatario recibe un vínculo de vista Web limitado que les permite leer el mensaje. Este vínculo incluye un código de paso único. Como administrador, puede decidir si los destinatarios pueden usar códigos de paso único para iniciar sesión en el portal de OME.
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>Para administrar si OME genera códigos de paso de un solo tiempo
  
1. Use una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365 e inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Ejecute el cmdlet Set-OMEConfiguration con el parámetro OTPEnabled:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   Por ejemplo, para deshabilitar los códigos de paso de una sola vez:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   Para habilitar los códigos de paso de una sola vez:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-protect-button-in-outlook-on-the-web"></a>Administrar la presentación del botón proteger en Outlook en la web

El botón **proteger** de Outlook en la web está deshabilitado al configurar OME. Como administrador, puede administrar si se muestra este botón a los usuarios finales.
  
### <a name="to-manage-whether-the-protect-button-appears-in-outlook-on-the-web"></a>Para administrar si el botón proteger aparece en Outlook en la web
  
1. Use una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365 e inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Ejecute el cmdlet Set-IRMConfiguration con el parámetro-SimplifiedClientAccessEnabled:

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

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>Habilitar el descifrado del servicio de mensajes de correo electrónico para los usuarios de la aplicación de correo de iOS

La aplicación de correo de iOS no puede descifrar mensajes protegidos con el cifrado de mensajes de Office 365. Como administrador de Office 365, puede aplicar el descifrado del servicio para los mensajes que se entregan a la aplicación de correo de iOS. Cuando elige usar el descifrado del lado del servicio, el servicio envía una copia descifrada del mensaje al dispositivo iOS. El dispositivo cliente almacena una copia descifrada del mensaje. El mensaje también retiene información sobre los derechos de uso, aunque la aplicación de correo de iOS no aplica derechos de uso del lado cliente al usuario. El usuario puede copiar o imprimir el mensaje incluso si originalmente no tenía los derechos necesarios. Sin embargo, si el usuario intenta completar una acción que requiere el servidor de correo de Office 365, como reenviar el mensaje, el servidor no permitirá la acción si el usuario no tuvo originalmente el permiso de uso para hacerlo. Sin embargo, los usuarios finales pueden evitar la restricción de uso "no reenviar" reenviando el mensaje desde una cuenta diferente dentro de la aplicación de correo de iOS. Independientemente de si configura el descifrado del lado del servicio del correo, los datos adjuntos a correo cifrado y protegido con derechos no se pueden ver en la aplicación de correo de iOS.
  
Si opta por no permitir que se envíen mensajes descifrados a los usuarios de la aplicación de correo de iOS, los usuarios recibirán un mensaje que indica que no tienen derechos para ver el mensaje. De forma predeterminada, el descifrado del servicio de mensajes de correo electrónico no está habilitado.
  
Para obtener más información y para obtener una vista de la experiencia del cliente, consulte [Ver mensajes cifrados en su iPhone o iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>Para administrar si los usuarios de la aplicación de correo de iOS pueden ver los mensajes protegidos por el cifrado de mensajes de Office 365
  
1. Use una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365 e inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Ejecute el cmdlet Set-ActiveSyncOrganizations con el parámetro AllowRMSSupportForUnenlightenedApps:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   Por ejemplo, para configurar el servicio para descifrar mensajes antes de que se envíen a aplicaciones no habilitadas, como la aplicación de correo de iOS:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   O bien, para configurar el servicio para que no envíe mensajes descifrados a aplicaciones no habilitadas:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Habilitar el descifrado del servicio de datos adjuntos de correo electrónico para clientes de correo del explorador Web

Normalmente, cuando se usa el cifrado de mensajes de Office 365, los datos adjuntos se cifran automáticamente. Como administrador de Office 365, puede aplicar el descifrado del servicio para los datos adjuntos de correo electrónico que los usuarios descarguen desde un explorador Web.
  
Cuando se usa el descifrado del servicio, el servicio envía una copia descifrada del archivo al dispositivo. El mensaje sigue cifrado. Los datos adjuntos de correo electrónico también conservan información sobre los derechos de uso, aunque el explorador no aplica al usuario los derechos de uso del lado del cliente. El usuario puede copiar o imprimir los datos adjuntos de correo electrónico incluso si no tienen los derechos necesarios. Sin embargo, si el usuario intenta completar una acción que requiere el servidor de correo de Office 365, como reenviar los datos adjuntos, el servidor no permitirá la acción si el usuario no tuvo originalmente el permiso de uso para hacerlo.
  
Independientemente de si se configura el descifrado del lado del servicio de los datos adjuntos, los usuarios no pueden ver los datos adjuntos en mensajes cifrados y protegidos por derechos en la aplicación de correo de iOS.
  
Si opta por no permitir datos adjuntos de correo electrónico descifrados, que es la opción predeterminada, los usuarios reciben un mensaje que indica que no tienen derechos para ver los datos adjuntos.
  
Para obtener más información acerca de cómo Office 365 implementa el cifrado de mensajes de correo electrónico y datos adjuntos con la opción de solo cifrado, vea la [opción de solo cifrado para los correos electrónicos.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>Para administrar si los datos adjuntos de correo electrónico se descifran al descargarlos desde un explorador Web
  
1. Use una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365 e inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Ejecute el cmdlet Set-IRMConfiguration con el parámetro DecryptAttachmentFromPortal:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   Por ejemplo, para configurar el servicio para descifrar los datos adjuntos de correo electrónico cuando un usuario los descarga desde un explorador Web:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   Para configurar el servicio para dejar datos adjuntos de correo electrónico cifrados tal como están al descargarlos:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail--office-365-advanced-message-encryption-only"></a>Asegurarse de que todos los destinatarios externos usan el portal OME para leer el correo cifrado: solo el cifrado de mensajes avanzado de Office 365

Si tiene el cifrado de mensajes avanzado de Office 365, puede usar plantillas de personalización de marca personalizadas para obligar a los destinatarios a recibir un correo de contenedor que les dirija a leer el correo electrónico cifrado en el portal de OME en lugar de usar Outlook o Outlook en la Web. Es posible que desee hacer esto si usa un mayor control sobre la forma en que los destinatarios usan el correo que reciben. Por ejemplo, si los destinatarios externos ven el correo electrónico en el portal web, puede establecer una fecha de expiración para el correo electrónico, y puede revocar el correo electrónico. Estas características solo se admiten a través del portal OME. Puede usar la opción cifrar y la opción no reenviar al crear reglas de flujo de correo.

### <a name="create-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email-to-be-revocable-and-expire-in-7-days"></a>Cree una plantilla personalizada para forzar que todos los destinatarios externos usen el portal OME y el correo electrónico cifrado sea revocable y expire en 7 días.

1. Use una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365 e inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Ejecute el cmdlet New-OMEConfiguration:

   ```powershell
   New-OMEConfiguration -Identity "<template name>" -ExternalMailExpiryInDays 7
   ```

   donde `template name` es el nombre que desea usar para la plantilla de personalización de marca personalizada de cifrado de mensajes de Office 365. For example,

   ```powershell
   New-OMEConfiguration -Identity "<One week expiration>" -ExternalMailExpiryInDays 7
   ```

3. Ejecute el cmdlet New-TransportRule:

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    donde:

   - `mail flow rule name`es el nombre que desea usar para la nueva regla de flujo de correo.

   - `option name`es `Encrypt` o `Do Not Forward`.

   - `template name`es el nombre que dio a la plantilla de personalización de marca `One week expiration`personalizada, por ejemplo,.

   Para cifrar todo el correo electrónico externo con la plantilla "expiración de una semana" y aplicar la opción de solo cifrado:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

   Para cifrar todo el correo electrónico externo con la plantilla "expiración de una semana" y aplicar la opción no reenviar:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>Personalizar la apariencia de los mensajes de correo electrónico y del portal de OME

Para obtener información detallada acerca de cómo puede personalizar OME para su organización, vea [Agregar la marca de su organización a los mensajes cifrados](add-your-organization-brand-to-encrypted-messages.md).
  
## <a name="disable-the-new-capabilities-for-ome"></a>Deshabilitar las nuevas funciones para OME

Esperamos que no se encuentre, pero, si es necesario, deshabilitar las nuevas capacidades de OME es muy sencilla. En primer lugar, debe quitar todas las reglas de flujo de correo que haya creado y que usen las nuevas funciones de OME. Para obtener información sobre cómo eliminar reglas de flujo de correo, consulte [Manage mail Flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx). A continuación, complete estos pasos en Exchange Online PowerShell.
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>Para deshabilitar las nuevas funciones de OME
  
1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Si ha habilitado el botón **proteger** en Outlook en la web, deshabilítelo mediante la ejecución del cmdlet Set-IRMConfiguration con el parámetro SimplifiedClientAccessEnabled. De lo contrario, omita este paso.

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. Deshabilite las nuevas funciones para OME ejecutando el cmdlet Set-IRMConfiguration con el parámetro AzureRMSLicensingEnabled establecido en false:

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```

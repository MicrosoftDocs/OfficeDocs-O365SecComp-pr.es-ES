---
title: Agregar la marca de organización a los mensajes cifrados
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- M365-security-compliance
description: Como administrador de Exchange, puede aplicar la personalización de marca de su organización a los mensajes de correo electrónico cifrados de la organización y el contenido del portal de cifrado.
ms.openlocfilehash: 237824890d2b519e36cf5205a1f5c3dcc0fe830a
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213340"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>Agregar la marca de su organización a los mensajes cifrados

Como administrador de Exchange online o Exchange Online Protection, puede aplicar la personalización de marca de la empresa para personalizar la apariencia de los mensajes de correo electrónico de cifrado de mensajes de Office 365 de la organización y el contenido del portal de cifrado. Con los cmdlets de Windows PowerShell Get-OMEConfiguration y set-OMEConfiguration, puede personalizar los siguientes aspectos de la experiencia de visualización para los destinatarios de los mensajes de correo electrónico cifrados:
  
- Texto de introducción del correo electrónico que contiene el mensaje cifrado
- Texto de aviso de declinación de responsabilidades del correo electrónico que contiene el mensaje cifrado
- Texto que aparece en el portal de OME
- Logotipo que aparece en el portal de mensajes de correo electrónico y OME
- Color de fondo en el portal de mensajes de correo electrónico y OME

También puede volver a la apariencia predeterminada en cualquier momento.

Si desea tener más control, puede crear varias plantillas para los mensajes de correo electrónico cifrados que se originan en la organización. Mediante el uso de estas plantillas, puede controlar algo más que la apariencia de los mensajes de correo electrónico, pero también controlar partes de la experiencia del usuario final. Por ejemplo, puede especificar si desea o no que los destinatarios de correo que tengan esta plantilla aplicada y que usen cuentas de Google, Yahoo y Microsoft puedan usar estas cuentas para iniciar sesión en el portal de cifrado de mensajes de Office 365. Puede usar plantillas para cumplir varios casos de uso, como:

- Plantillas para cada departamento, como finanzas, ventas, etc.
- Plantillas para diferentes productos
- Plantillas para diferentes regiones geográficas o países

Una vez que haya creado las plantillas, puede aplicarlas a los correos electrónicos cifrados mediante las reglas de flujo de correo de Exchange. Se pueden revocar todos los mensajes de personalización de marca con estas plantillas.
  
||
|:-----|
|Este artículo forma parte de una amplia serie de artículos sobre el cifrado de mensajes de Office 365. Este artículo está destinado a los administradores y ITPros. Si solo está buscando información sobre cómo enviar o recibir un mensaje cifrado, vea la lista de artículos en el cifrado de [mensajes de Office 365 (OME)](ome.md) y busque el artículo que mejor se adapte a sus necesidades.|
||

## <a name="create-branding-templates"></a>Crear plantillas de personalización de marca

Puede crear plantillas de personalización de marca para su organización en Windows PowerShell con el cmdlet New-OMEConfiguration. Una vez que haya creado la plantilla, defina las partes de la plantilla mediante el cmdlet Set-OMEConfiguration. Puede crear varias plantillas.

![Elementos de correo electrónico personalizables](media/ome-template-breakout.png)
  
1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Use el cmdlet New-OMEConfiguration para crear una nueva plantilla.

   ```powershell
   New-OMEConfiguration -Identity <OMEConfigurationIdParameter>
   ```
   Por ejemplo,

   ```powershell
   New-OMEConfiguration -Identity <Branding template 1>
   ```
3. Defina las personalizaciones para la plantilla que acaba de definir con el cmdlet Set-OMEConfiguration tal como se describe en [set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration) o use la siguiente tabla para obtener instrucciones.

|**Para personalizar esta característica de la experiencia de cifrado**|**Use estos comandos**|
|:-----|:-----|
|Color de fondo|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"`|
|Logotipo|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Formatos de archivo compatibles: .png, .jpg, .bmp o .tiff  <br/> Tamaño óptimo del archivo de logotipo: inferior a 40 KB  <br/> Tamaño óptimo de la imagen de logotipo: 170 x 70 píxeles|
|Texto junto al nombre y la dirección de correo electrónico del remitente|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -IntroductionText "<String up to 1024 characters>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|Texto que aparece en el botón "leer mensaje"|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -ReadButtonText "<String up to 1024 characters>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|Texto que aparece por debajo del botón "leer mensaje"|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|Aviso de declinación de responsabilidades en el correo electrónico que contiene el mensaje cifrado|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|Texto que aparece en la parte superior del portal de visualización de correo cifrado|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|Para habilitar o deshabilitar la autenticación con un código de paso único para esta plantilla personalizada|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -OTPEnabled <$true|$false>` <br/> **Ejemplos:** <br/>Para habilitar los códigos de acceso de una sola vez para esta plantilla personalizada <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> Para deshabilitar los códigos de acceso de un solo uso para esta plantilla personalizada <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|Para habilitar o deshabilitar la autenticación con identidades de Microsoft, Google o Yahoo para esta plantilla personalizada|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -SocialIdSignIn <$true|$false>` <br/> **Ejemplos:** <br/>Para habilitar identificadores sociales para esta plantilla personalizada <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> Para deshabilitar los identificadores sociales de esta plantilla personalizada <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="to-remove-brand-customizations-from-the-ome-portal-and-email-messages-encrypted-by-ome"></a>Para quitar personalizaciones de marca del portal de OME y mensajes de correo electrónico cifrados por OME
  
1. [Conexión a PowerShell de Exchange Online](https://aka.ms/exopowershell).

2. Use el cmdlet **set-OMEConfiguration** como se describe en [set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration). Para quitar las personalizaciones de marca de la organización de los valores de DisclaimerText, EmailText y PortalText, establezca el valor en una cadena vacía `""`. Para todos los valores de imagen, como el logotipo, establezca el `"$null"`valor en.

**Opciones de personalización de cifrado**

**Para hacer que esta característica de la experiencia de cifrado vuelva a los valores de texto e imagen predeterminados**|**Use estos comandos**|
|:-----|:-----|
|Texto predeterminado que acompaña a los mensajes de correo electrónico cifrado  <br/> El texto predeterminado aparece por encima de las instrucciones para ver los mensajes cifrados|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
|Aviso de declinación de responsabilidades en el correo electrónico que contiene el mensaje cifrado|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
|Texto que aparece en la parte superior del portal de visualización de correo cifrado|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **Ejemplo de volver a su valor predeterminado:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
|Logotipo|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **Ejemplo de volver a su valor predeterminado:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
|Color de fondo|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **Ejemplo de volver a su valor predeterminado:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="create-an-exchange-mail-flow-rule-that-applies-custom-branding-to-encrypted-emails"></a>Crear una regla de flujo de correo de Exchange que aplique la personalización de marca a los correos electrónicos cifrados

Una vez que haya creado una plantilla de personalización de marca, puede crear reglas de flujo de correo de Exchange para aplicar esa marca personalizada según ciertas condiciones. Dicha regla aplicará la personalización de marca personalizada en los siguientes escenarios:

- Si el usuario ha cifrado el correo electrónico manualmente desde los clientes de Outlook o Outlook en la web (anteriormente conocido como Outlook Web App)
- Si el correo electrónico se cifró automáticamente mediante una regla de flujo de correo de Exchange o una directiva de prevención de pérdida de datos de Office 365

Para obtener información sobre cómo crear una regla de flujo de correo de Exchange que aplique cifrado, vea [definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md).

1. En un explorador Web, con una cuenta profesional o educativa a la que se le han concedido permisos de administrador global, [inicie sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Elija el icono **Administración** .

3. En el Centro de administración de Office 365, elija **Centros de administración** \> **Exchange**.

4. En el EAC, vaya a **** \> **reglas** de flujo de correo **** ![y seleccione nuevo](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> icono nuevo para **crear una nueva regla**. Para obtener más información acerca del uso de EAC, consulte [centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. En **nombre**, escriba un nombre para la regla, como la personalización de marca del Departamento de ventas.

6. En **aplicar esta regla si** selecciona una condición, seleccione la condición que **el remitente se encuentra dentro de la organización** , así como las demás condiciones que desee en la lista de condiciones disponibles. Por ejemplo, es posible que desee aplicar una plantilla de personalización de marca determinada a:

     - Todos los mensajes de correo electrónico cifrados enviados desde miembros del Departamento de finanzas
     - Mensajes de correo electrónico cifrados enviados con una palabra clave determinada, como "external" o "Partner"
     - Mensajes de correo electrónico cifrados enviados a un dominio en particular

7. En **hacer lo siguiente**, seleccione **modificar la seguridad** > de mensajes aplicar personalización de**marca personalizada a los mensajes OME**. A continuación, en la lista desplegable, seleccione una plantilla de personalización de marca de las que ha creado.
8. Opcional Si desea que la regla de flujo de correo también aplique el cifrado además de la personalización de marca, desde **haga lo siguiente**, seleccione **modificar la seguridad de los mensajes** y, a continuación, elija aplicar el cifrado de **mensajes de Office 365 y la protección de derechos**. Seleccione una plantilla RMS de la lista, elija **Guardar**y, después, haga clic en **Aceptar**.
  
     La lista de plantillas incluye todas las plantillas y opciones predeterminadas, así como las plantillas personalizadas que haya creado para su uso por parte de Office 365. Si la lista está vacía, asegúrese de haber configurado el cifrado de mensajes de Office 365 con las nuevas funciones, tal como se describe en [set up New Office 365 Message Encryption Capabilities](set-up-new-message-encryption-capabilities.md). Para obtener información sobre las plantillas predeterminadas, vea [Configuring and Managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Para obtener información sobre **** la opción no reenviar, vea la opción no reenviar [para los correos electrónicos](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Para obtener información sobre la opción **solo cifrar** , vea la [opción cifrar solo para los correos electrónicos](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

     Puede elegir **Agregar acción** si desea especificar otra acción.

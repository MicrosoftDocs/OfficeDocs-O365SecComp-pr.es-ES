---
title: Agregar marca de su organización a los mensajes cifrados
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
description: Como administrador de Exchange, puede aplicar la personalización de marca de su organización a los mensajes de correo electrónico cifrado de la organización y el contenido del portal de cifrado.
ms.openlocfilehash: 4b22b72a8b77c2978a7cf25166978759119c272c
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29696224"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>Agregar la marca de su organización a los mensajes cifrados

Como administrador de Exchange Online o Exchange Online Protection, puede aplicar su compañía para personalizar la apariencia de los mensajes de correo electrónico de cifrado de mensajes de Office 365 de su organización y el contenido del portal de cifrado de personalización de marca. Mediante los cmdlets Get-OMEConfiguration y Set-OMEConfiguration Windows PowerShell, puede personalizar los siguientes aspectos de la experiencia de visualización para los destinatarios de los mensajes de correo electrónico cifrado:
  
- Texto de introducción del correo electrónico que contiene el mensaje cifrado
- Texto de aviso de declinación de responsabilidades del correo electrónico que contiene el mensaje cifrado
- Texto que aparece en el portal de OME
- Logotipo que aparece en el mensaje de correo electrónico y portal OME
- Color de fondo en el mensaje de correo electrónico y portal OME

También puede volver a la apariencia predeterminada en cualquier momento.

Si desea obtener más control, puede crear varias plantillas para mensajes de correo electrónico cifrados que se originan desde la organización. Uso de estas plantillas, puede controlar algo más que la apariencia de los mensajes de correo electrónico, pero también controlar elementos de la experiencia del usuario final. Por ejemplo, puede especificar si los destinatarios de correo que tienen aplicada esta plantilla y que usan Microsoft Accounts, Yahoo y Google pueden usar estas cuentas para iniciar sesión en el portal de cifrado de mensajes de Office 365. Puede usar plantillas para cumplir con varios casos de uso, tales como:

- Plantillas para cada departamento, por ejemplo, finanzas, ventas, etcetera.
- Plantillas para distintos productos
- Plantillas para diferentes regiones geográficas o países

Una vez que ha creado las plantillas, se puede aplicar a los mensajes de correo electrónico cifrados mediante el uso de reglas de flujo de correo de Exchange. Todos los mensajes de correo que se marca mediante el uso de estas plantillas pueden ser revocados.
  
||
|:-----|
|En este artículo es parte de una serie de artículos sobre Office 365 Message Encryption más grande. En este artículo está destinada a los administradores y profesionales de TI. Si sólo está buscando información en enviar o recibir un mensaje cifrado, vea la lista de los artículos de [Office 365 Message Encryption (OME)](ome.md) y busque el artículo que mejor se adapte a sus necesidades. |
||

## <a name="create-branding-templates"></a>Creación de plantillas de personalización de marca

Crear plantillas de personalización de marca para la organización en Windows PowerShell con el cmdlet New-OMEConfiguration. Una vez que ha creado la plantilla, defina las piezas de la plantilla mediante el cmdlet Set-OMEConfiguration. Puede crear varias plantillas.

![Elementos de correo electrónico personalizable](media/ome-template-breakout.png)
  
1. Uso de una cuenta de trabajo o escuela que tiene permisos de administrador global de la organización de Office 365, iniciar una sesión de Windows PowerShell y conectarse a Exchange Online. Para obtener instrucciones, vea [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Use el cmdlet New-OMEConfiguration para crear una nueva plantilla.
     ```powershell
     New-OMEConfiguration -Identity <OMEConfigurationIdParameter>
     ```
     Por ejemplo,
     ```powershell
     New-OMEConfiguration -Identity <Branding template 1>
     ```
3. Definir las personalizaciones para la plantilla que acaba de definir mediante el cmdlet Set-OMEConfiguration tal como se describe en [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration) o use la tabla siguiente para obtener instrucciones.

|**Para personalizar esta característica de la experiencia de cifrado**|**Use estos comandos**|
|:-----|:-----|
|Color de fondo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> |
|Logotipo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Formatos de archivo compatibles: .png, .jpg, .bmp o .tiff  <br/> Tamaño óptimo del archivo de logotipo: inferior a 40 KB  <br/> Tamaño óptimo de la imagen de logotipo: 170 x 70 píxeles  <br/> |
|Texto situado junto a la dirección del remitente nombre y correo electrónico| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -IntroductionText "<String up to 1024 characters>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|Texto que aparece en el botón "Read Message"| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -ReadButtonText "<String up to 1024 characters>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|Texto que aparece por encima de debajo del botón "Read Message"| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|Aviso de declinación de responsabilidades en el correo electrónico que contiene el mensaje cifrado  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|Texto que aparece en la parte superior del portal de visualización de correo cifrado<br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."` <br/> |
|Para habilitar o deshabilitar la autenticación con un código de acceso única para esta plantilla personalizada| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -OTPEnabled <$true|$false>` <br/> **Ejemplos:** <br/>Para habilitar códigos de acceso única para esta plantilla personalizada <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> Para deshabilitar los códigos de acceso única para esta plantilla personalizada <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|Para habilitar o deshabilitar la autenticación con las identidades de Microsoft, Google o Yahoo para esta plantilla personalizada| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -SocialIdSignIn <$true|$false>` <br/> **Ejemplos:** <br/>Para habilitar los identificadores de sociales para esta plantilla personalizada <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> Para deshabilitar los identificadores de sociales para esta plantilla personalizada <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="to-remove-brand-customizations-from-the-ome-portal-and-email-messages-encrypted-by-ome"></a>Para quitar las personalizaciones de marca de los mensajes de correo electrónico y portal OME cifrados por OME
  
1. [Conexión a PowerShell de Exchange Online](https://aka.ms/exopowershell).

2. Use el cmdlet Set-OMEConfiguration tal como se describe en [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration). Para quitar la organización de las personalizaciones de la DisclaimerText, EmailText, con marca y los valores de PortalText, establezca el valor en una cadena vacía, `""`. Para todos los valores, como el logotipo, de imagen, establezca el valor en `"$null"`.

**Opciones de personalización de cifrado**

**Para hacer que esta característica de la experiencia de cifrado vuelva a los valores de texto e imagen predeterminados**|**Use estos comandos**|
|:-----|:-----|
|Texto predeterminado que acompaña a los mensajes de correo electrónico cifrado  <br/> El texto predeterminado aparece por encima de las instrucciones para ver los mensajes cifrados| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
|Aviso de declinación de responsabilidades en el correo electrónico que contiene el mensaje cifrado| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
|Texto que aparece en la parte superior del portal de visualización de correo cifrado| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **Back reversión de ejemplo a la configuración predeterminada:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|Logotipo| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **Back reversión de ejemplo a la configuración predeterminada:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
|Color de fondo| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **Back reversión de ejemplo a la configuración predeterminada:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="create-an-exchange-mail-flow-rule-that-applies-custom-branding-to-encrypted-emails"></a>Crear una regla de flujo de correo de Exchange que se aplica a mensajes de correo electrónico cifrados de personalización de marca

Una vez haya creado una plantilla de personalización de marca, puede crear reglas de flujo de correo de Exchange para aplicar dicha personalización de marca en función de ciertas condiciones. Dicha regla aplicará la personalización de marca en los siguientes escenarios:

- Si el correo electrónico se cifró manualmente por el usuario final de los clientes de Outlook u OWA
- Si el correo electrónico se cifra automáticamente una regla de flujo de correo de Exchange o la directiva de prevención de pérdida de datos de Office 365

Para obtener información sobre cómo crear una regla de flujo de correo de Exchange que se aplica el cifrado, consulte [definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md).

1. En un explorador web, usando una cuenta de trabajo o escuela que se ha concedido permisos de administrador global, [iniciar sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Elija el icono de **administración** .

3. En el Centro de administración de Office 365, elija **Centros de administración** \> **Exchange**.

4. En el EAC, vaya a **flujo de correo** \> **reglas** y seleccione **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **crear una nueva regla**. Para obtener más información sobre cómo usar el CEF, vea el [Centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. En **nombre**, escriba un nombre para la regla, como la personalización de marca para el departamento de ventas.

6. En **aplicar esta regla si** seleccionar una condición, seleccione la condición que **el remitente se encuentra dentro de la organización** , así como otras condiciones que desee de la lista de condiciones disponibles. Por ejemplo, es posible que desee aplicar una plantilla determinada de personalización de marca para:

     - Todos los correos electrónicos enviados desde los miembros del departamento de finanzas de cifrados
     - Mensajes de correo electrónico cifrados enviados con una determinada palabra clave, como "Externos" o "Socio"
     - Mensajes de correo electrónico cifrados enviados a un dominio concreto

7. En **hacer lo siguiente**, seleccione **modificar la seguridad de los mensajes** > **aplicar a los mensajes OME de personalización de marca**. A continuación, en la lista desplegable, seleccione una plantilla de personalización de marca de los que ha creado.
8. (Opcional) Si desea que la regla de flujo de correo para aplicar también el cifrado además personalizados de personalización de marca, desde **hacer lo siguiente**, seleccione **modificar la seguridad de los mensajes** y, a continuación, elija **aplicar el cifrado de mensajes de Office 365 y protección de derechos**. Seleccione una plantilla de RMS en la lista, elija **Guardar**y, a continuación, elija **Aceptar**.
  
     La lista de plantillas incluye todas las plantillas predeterminadas y opciones, así como las plantillas personalizadas que ha creado para utilizan por Office 365. Si la lista está vacía, asegúrese de que ha configurado el cifrado de mensajes de Office 365 con las nuevas capacidades de tal como se describe en [Set up nuevas capacidades de cifrado de mensajes de Office 365](set-up-new-message-encryption-capabilities.md). Para obtener información acerca de las plantillas predeterminadas, vea [configuración y administración de plantillas para la protección de la información de Azure](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Para obtener información acerca de la opción **No reenviar** , vea [no reenviar una opción para los correos electrónicos](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Para obtener información acerca de la opción de **cifrar sólo** , vea [cifrar sólo una opción para los correos electrónicos](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

     Puede elegir **Agregar acción** si desea especificar otra acción.

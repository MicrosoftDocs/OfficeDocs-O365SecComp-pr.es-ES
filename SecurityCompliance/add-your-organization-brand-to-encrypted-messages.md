---
title: Agregar marca de su organización a los mensajes cifrados
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/2/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
description: 'Como administrador de Exchange, puede aplicar la personalización de marca de su organización a los mensajes de correo electrónico cifrado de la organización y el contenido del portal de cifrado. '
ms.openlocfilehash: 2f34b5cea3155f587fd7787f1f69270d1373400b
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536214"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>Agregar la marca de su organización a los mensajes cifrados

Como administrador de Exchange Online o Exchange Online Protection, puede aplicar su compañía para personalizar la apariencia de los mensajes de correo electrónico de cifrado de mensajes de Office 365 de su organización y el contenido del portal de cifrado de personalización de marca. Mediante los cmdlets Get-OMEConfiguration y Set-OMEConfiguration Windows PowerShell, puede personalizar los siguientes aspectos de la experiencia de visualización para los destinatarios de los mensajes de correo electrónico cifrado:
  
- Texto de introducción del correo electrónico que contiene el mensaje cifrado
    
- Texto de aviso de declinación de responsabilidades del correo electrónico que contiene el mensaje cifrado
    
- Texto que aparece en el portal de OME
    
- Logotipo que aparece en el mensaje de correo electrónico y portal OME
    
- Color de fondo en el mensaje de correo electrónico y portal OME
    
También puede volver a la apariencia predeterminada en cualquier momento.
  
||
|:-----|
|En este artículo es parte de una serie de artículos sobre Office 365 Message Encryption más grande. En este artículo está destinada a los administradores y profesionales de TI. Si sólo está buscando información en enviar o recibir un mensaje cifrado, vea la lista de los artículos de [Office 365 Message Encryption (OME)](ome.md) y busque el artículo que mejor se adapte a sus necesidades. |
||
   
**Para personalizar la apariencia de los mensajes de correo electrónico y portal OME cifrados por OME con la marca de la organización**
  
1. Conectarse a Exchange Online mediante PowerShell remoto, tal como se describe en [conectarse a Exchange Online Using Remote PowerShell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx).
    
2. Use el cmdlet Set-OMEConfiguration tal como se describe en [Set-OMEConfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b) o use la tabla siguiente para obtener instrucciones. 
    
**Opciones de personalización de cifrado**

|**Para personalizar esta característica de la experiencia de cifrado**|**Use estos comandos**|
|:-----|:-----|
|Texto predeterminado que acompaña a los mensajes de correo electrónico cifrado. El texto predeterminado aparece por encima de las instrucciones para ver los mensajes cifrados  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|Aviso de declinación de responsabilidades en el correo electrónico que contiene el mensaje cifrado  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only."` <br/> |
|Texto que aparece en la parte superior del portal de visualización de correo cifrado<br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."` <br/> |
|Logotipo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Formatos de archivo compatibles: .png, .jpg, .bmp o .tiff  <br/> Tamaño óptimo del archivo de logotipo: inferior a 40 KB  <br/> Tamaño óptimo de la imagen de logotipo: 170 x 70 píxeles  <br/> |
|Color de fondo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -BackgroundColor "#ffffff"` <br/> |
   
**Para quitar las personalizaciones de marca de los mensajes de correo electrónico y portal OME cifrados por OME**
  
1. Conectarse a Exchange Online mediante PowerShell remoto, tal como se describe en [conectarse a Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).
    
2. Use el cmdlet Set-OMEConfiguration tal como se describe en [Set-OMEConfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b). Para quitar la organización de las personalizaciones de la DisclaimerText, EmailText, con marca y los valores de PortalText, establezca el valor en una cadena vacía, `""`. Para todos los valores, como el logotipo, de imagen, establezca el valor en `"$null"`.
    
**Opciones de personalización de cifrado**

**Para hacer que esta característica de la experiencia de cifrado vuelva a los valores de texto e imagen predeterminados**|**Use estos comandos**|
|:-----|:-----|
|Texto predeterminado que acompaña a los mensajes de correo electrónico cifrado  <br/> El texto predeterminado aparece por encima de las instrucciones para ver los mensajes cifrados  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
|Aviso de declinación de responsabilidades en el correo electrónico que contiene el mensaje cifrado  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **Ejemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
|Texto que aparece en la parte superior del portal de visualización de correo cifrado  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **Back reversión de ejemplo a la configuración predeterminada:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|Logotipo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **Back reversión de ejemplo a la configuración predeterminada:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |
|Color de fondo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **Back reversión de ejemplo a la configuración predeterminada:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null` <br/> |
   


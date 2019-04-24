---
title: Configurar una colección de certificados virtuales en Exchange Online para validar S/MIME
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: Los administradores pueden aprender a crear una colección de certificados virtuales que se usará para validar certificados S/MIME en Exchange Online.
ms.openlocfilehash: 15998bce1971952286d8dd4401a92f1e9e47c25d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260728"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>Configurar una colección de certificados virtuales en Exchange Online para validar S/MIME

Como administrador, tendrá que configurar una colección de certificados virtuales en Exchange online que se usará para validar los certificados S/MIME. Esta colección de certificados virtuales se configura como un almacén de certificados con una extensión de nombre de archivo SST. El archivo SST contiene todos los certificados raíz e intermedios que se usan al validar un certificado S/MIME.

## <a name="create-and-save-an-sst"></a>Crear y guardar un SST

Puede crear este archivo de almacén de certificados SST exportando los certificados de una máquina de confianza mediante el cmdlet **Export-Certificate** en Windows PowerShell y especificando el valor de _tipo_ como SST. Para obtener instrucciones, consulte [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).

Una vez que tenga el archivo del almacén de certificados SST, use la siguiente sintaxis en Exchange Online PowerShell para guardar el contenido del archivo SST en el almacén de certificados virtuales de Exchange Online. Para conectarse al PowerShell de Exchange Online, consulte [Conectarse al PowerShell de Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554).

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

En este ejemplo se importa el archivo SST C:\Mis Documentos\exported rules de certificados Store. SST.

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-SmimeConfig](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).

## <a name="ensuring-a-certificate-is-valid"></a>Garantizar que un certificado es válido

En Exchange Online, solo se usa SST para la validación de certificados.

## <a name="more-information"></a>Más información

[S/MIME para la firma y el cifrado de mensajes](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)

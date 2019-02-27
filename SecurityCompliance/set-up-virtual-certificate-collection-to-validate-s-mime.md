---
title: Configurar una colección de certificados virtuales en Exchange Online para validar S/MIME
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: Los administradores pueden aprender a crear una colección de certificados virtuales que se usará para validar certificados S/MIME en Exchange Online.
ms.openlocfilehash: 2aa6e529f5ca374af6fe6d80a403058a8b6e468a
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296953"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="3b6ae-103">Configurar una colección de certificados virtuales en Exchange Online para validar S/MIME</span><span class="sxs-lookup"><span data-stu-id="3b6ae-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

<span data-ttu-id="3b6ae-p101">Como administrador, tendrá que configurar una colección de certificados virtuales en Exchange online que se usará para validar los certificados S/MIME. Esta colección de certificados virtuales se configura como un almacén de certificados con una extensión de nombre de archivo SST. El archivo SST contiene todos los certificados raíz e intermedios que se usan al validar un certificado S/MIME.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-p101">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates. This virtual certificate collection is set up as a certificate store with an SST filename extension. The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="3b6ae-107">Crear y guardar un SST</span><span class="sxs-lookup"><span data-stu-id="3b6ae-107">Create and save an SST</span></span>

<span data-ttu-id="3b6ae-p102">Puede crear este archivo de almacén de certificados SST exportando los certificados de una máquina de confianza mediante el cmdlet **Export-Certificate** en Windows PowerShell y especificando el valor de _tipo_ como SST. Para obtener instrucciones, consulte [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span><span class="sxs-lookup"><span data-stu-id="3b6ae-p102">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST. For instructions, see [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="3b6ae-p103">Una vez que tenga el archivo del almacén de certificados SST, use la siguiente sintaxis en Exchange Online PowerShell para guardar el contenido del archivo SST en el almacén de certificados virtuales de Exchange Online. Para conectarse a Exchange Online PowerShell, consulte [conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="3b6ae-p103">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store. To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="3b6ae-112">En este ejemplo se importa el archivo SST C:\Mis Documentos\exported rules de certificados Store. SST.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="3b6ae-113">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-SmimeConfig](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="3b6ae-113">For detailed syntax and parameter information, see [Set-SmimeConfig](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="3b6ae-114">Garantizar que un certificado es válido</span><span class="sxs-lookup"><span data-stu-id="3b6ae-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="3b6ae-115">En Exchange Online, solo se usa SST para la validación de certificados.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="3b6ae-116">Más información</span><span class="sxs-lookup"><span data-stu-id="3b6ae-116">More Information</span></span>

[<span data-ttu-id="3b6ae-117">S/MIME para la firma y el cifrado de mensajes</span><span class="sxs-lookup"><span data-stu-id="3b6ae-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="3b6ae-118">Get-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="3b6ae-118">Get-SmimeConfig</span></span>](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)

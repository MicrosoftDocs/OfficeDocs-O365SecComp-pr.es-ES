---
title: Configurar una colección de certificados virtuales para validar S/MIME
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: s un administrador de inquilinos tendrá que configurar una colección de certificados virtuales que se usará para validar los certificados S/MIME.
ms.openlocfilehash: 0e8226ca35e872cd8c7da16ba353bf8b99a6954d
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2019
ms.locfileid: "30091062"
---
# <a name="set-up-virtual-certificate-collection-to-validate-smime"></a>Configurar una colección de certificados virtuales para validar S/MIME

Como administrador de inquilinos tendrá que configurar una colección de certificados virtuales que se usará para validar certificados S/MIME. Esta colección de certificados virtuales se configura como un tipo de archivo de almacén de certificados con una extensión de nombre de archivo SST. El archivo SST contiene todos los certificados raíz e intermedios que se usan al validar un certificado S/MIME.
  
## <a name="create-and-save-an-sst"></a>Crear y guardar un SST
<a name="sectionSection0"> </a>

Solo puede usar el Shell para realizar este procedimiento. Para obtener información sobre cómo abrir el Shell de administración de Exchange en su organización local Exchange, vea **Open the Shell**. Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online, vea [Conexión a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
  
Como administrador, puede crear este archivo SST exportando los certificados desde un equipo de confianza mediante el cmdlet  `Export-Certificate` y especificando el tipo como SST. Para obtener más información sobre el cmdlet  `Export-Certificate`, consulte el tema de referencia [Export-Certificate](https://docs.microsoft.com/en-us/powershell/module/pkiclient/export-certificate?view=win10-ps). 
  
Una vez que se genere el archivo SST, use el cmdlet  `Set-Smimeconfig` para guardarlo en el almacén de certificados virtuales mediante el parámetro  _-SMIMECertificateIssuingCA_. Por ejemplo:  `Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content filename.sst -Encoding Byte)`
  
## <a name="ensuring-a-certificate-is-valid"></a>Garantizar que un certificado es válido
<a name="sectionSection1"> </a>

Exchange 2013 SP1 primero comprueba el archivo SST y valida el certificado. Si se produce un error en la validación, examinará el almacén de certificados del equipo local para validar el certificado. Este comportamiento es nuevo para Exchange 2013 SP1 y diferente de las versiones anteriores de Exchange. En Exchange Online solo se usará el SST para la validación.
  
## <a name="more-information"></a>Más información
<a name="sectionSection2"> </a>

[S/MIME para la firma y el cifrado de mensajes](s-mime-for-message-signing-and-encryption.md)
  
[Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)
  


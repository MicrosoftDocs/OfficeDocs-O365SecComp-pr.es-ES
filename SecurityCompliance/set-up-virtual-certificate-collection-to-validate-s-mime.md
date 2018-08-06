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
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: s un administrador de inquilinos debe configurar una colección virtual de certificado que se usará para validar certificados S/MIME.
ms.openlocfilehash: 4b2d85181d95bb1f90d46412cca85c2356d98e10
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2018
ms.locfileid: "22028147"
---
# <a name="set-up-virtual-certificate-collection-to-validate-smime"></a><span data-ttu-id="90c87-103">Configurar una colección de certificados virtuales para validar S/MIME</span><span class="sxs-lookup"><span data-stu-id="90c87-103">Set up virtual certificate collection to validate S/MIME</span></span>

<span data-ttu-id="90c87-p101">Como administrador de inquilinos tendrá que configurar una colección de certificados virtuales que se usará para validar certificados S/MIME. Esta colección de certificados virtuales se configura como un tipo de archivo de almacén de certificados con una extensión de nombre de archivo SST. El archivo SST contiene todos los certificados raíz e intermedios que se usan al validar un certificado S/MIME.</span><span class="sxs-lookup"><span data-stu-id="90c87-p101">As a tenant administrator you will need to configure a virtual certificate collection that will be used to validate S/MIME certificates. This virtual certificate collection is set up as a certificate store file type with an SST filename extension. The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>
  
## <a name="create-and-save-an-sst"></a><span data-ttu-id="90c87-107">Crear y guardar un SST</span><span class="sxs-lookup"><span data-stu-id="90c87-107">Create and save an SST</span></span>
<span data-ttu-id="90c87-108"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="90c87-108"></span></span>

<span data-ttu-id="90c87-p102">Solo puede usar el Shell para realizar este procedimiento. Para obtener información sobre cómo abrir el Shell de administración de Exchange en su organización local Exchange, vea **Open the Shell**. Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online, vea [Conexión a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="90c87-p102">You can only use the Shell to perform this procedure. To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**. To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
  
<span data-ttu-id="90c87-p103">Como administrador, puede crear este archivo SST exportando los certificados desde un equipo de confianza mediante el cmdlet  `Export-Certificate` y especificando el tipo como SST. Para obtener más información sobre el cmdlet  `Export-Certificate`, consulte el tema de referencia [Export-Certificate](https://technet.microsoft.com/en-us/library/hh848628.aspx).</span><span class="sxs-lookup"><span data-stu-id="90c87-p103">As an administrator, you can create this SST file by exporting the certificates from a trusted machine using the  `Export-Certificate` cmdlet and specifying the type as SST. For more information the  `Export-Certificate` cmdlet, see the [Export-Certificate](https://technet.microsoft.com/en-us/library/hh848628.aspx) reference topic.</span></span> 
  
<span data-ttu-id="90c87-p104">Una vez que se genere el archivo SST, use el cmdlet  `Set-Smimeconfig` para guardarlo en el almacén de certificados virtuales mediante el parámetro  _-SMIMECertificateIssuingCA_. Por ejemplo:  `Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content filename.sst -Encoding Byte)`</span><span class="sxs-lookup"><span data-stu-id="90c87-p104">Once the SST file is generated, use the  `Set-Smimeconfig` cmdlet to save it in the virtual certificate store by using the  _-SMIMECertificateIssuingCA_ parameter. For example:  `Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content filename.sst -Encoding Byte)`</span></span>
  
## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="90c87-116">Garantizar que un certificado es válido</span><span class="sxs-lookup"><span data-stu-id="90c87-116">Ensuring a certificate is valid</span></span>
<span data-ttu-id="90c87-117"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="90c87-117"></span></span>

<span data-ttu-id="90c87-p105">Exchange 2013 SP1 primero comprueba el archivo SST y valida el certificado. Si se produce un error en la validación, examinará el almacén de certificados del equipo local para validar el certificado. Este comportamiento es nuevo para Exchange 2013 SP1 y diferente de las versiones anteriores de Exchange. En Exchange Online solo se usará el SST para la validación.</span><span class="sxs-lookup"><span data-stu-id="90c87-p105">Exchange 2013 SP1 first checks for the SST file and validates the certificate. If the validation fails, it will look at the local machine certificate store to validate the certificate. This behavior is new for Exchange 2013 SP1 and different from prior versions of Exchange. In Exchange Online only the SST will be used for validation.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="90c87-122">Más información</span><span class="sxs-lookup"><span data-stu-id="90c87-122">More Information</span></span>
<span data-ttu-id="90c87-123"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="90c87-123"></span></span>

[<span data-ttu-id="90c87-124">S/MIME para la firma y el cifrado de mensajes</span><span class="sxs-lookup"><span data-stu-id="90c87-124">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
  
[<span data-ttu-id="90c87-125">Get-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="90c87-125">Get-SmimeConfig</span></span>](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)
  


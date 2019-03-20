---
title: Sincronizar certificados de usuario con Office 365 para S/MIME
ms.author: chrisda
author: chrisda
manager: Serdars
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: Antes de poder enviar mensajes protegidos por S/MIME, deben configurarse los certificados apropiados. Para poder enviar mensajes cifrados mediante Exchange Online, el programa de correo electrónico del remitente usa el certificado público del destinatario para cifrar el mensaje. Este certificado X.509 público debe publicarse en Office 365.
ms.openlocfilehash: 927f6b4c7a166ee35e11a8712cc99054b0e67dee
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692569"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="70a12-105">Sincronizar certificados de usuario con Office 365 para S/MIME</span><span class="sxs-lookup"><span data-stu-id="70a12-105">Sync user certificates to Office 365 for S/MIME</span></span>

<span data-ttu-id="70a12-106">Para que cualquier persona pueda enviar mensajes protegidos por S/MIME en Exchange Online, deben configurarse los certificados apropiados.</span><span class="sxs-lookup"><span data-stu-id="70a12-106">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="70a12-107">Para enviar mensajes cifrados a través de Exchange Online, la aplicación de correo electrónico del remitente usa el certificado público del destinatario para cifrar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="70a12-107">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="70a12-108">Este certificado X.509 público debe publicarse en Office 365.</span><span class="sxs-lookup"><span data-stu-id="70a12-108">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="70a12-109">Para sincronizar los certificados que admiten S/MIME</span><span class="sxs-lookup"><span data-stu-id="70a12-109">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="70a12-110">Para comenzar a configurar S/MIME, emita los certificados y publíquelos en sus Servicios de directorio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="70a12-110">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="70a12-111">Para obtener más información acerca de la administración de certificados en Exchange Server, consulte [digital Certificates and SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).</span><span class="sxs-lookup"><span data-stu-id="70a12-111">For more information about managing certificates in Exchange Server, see [Digital Certificates and SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).</span></span>

<span data-ttu-id="70a12-p104">Una vez publicados los certificados, use la Herramienta de sincronización de Microsoft Azure Active Directory para sincronizar los datos de usuario de su entorno local de Exchange con Office 365. Para obtener más información acerca de este proceso, consulte [DirSync: historial de publicación de las versiones de la herramienta de sincronización](https://go.microsoft.com/fwlink/p/?LinkId=392587).</span><span class="sxs-lookup"><span data-stu-id="70a12-p104">After your certificates are published, use the Azure Active Directory Sync tool to synchronize user data from your on-premises Exchange environment to Office 365. For more information on this process, see [DirSync: Directory Sync Tool Version Release History](https://go.microsoft.com/fwlink/p/?LinkId=392587).</span></span>

<span data-ttu-id="70a12-114">Además de sincronizar otros datos de directorio, para fines de S/MIME, la herramienta sincronizará los atributos **userCertificate** y **userSMIMECertificate** para cada objeto de usuario, de modo que los datos puedan usarse para firmar y cifrar mensajes.</span><span class="sxs-lookup"><span data-stu-id="70a12-114">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="70a12-115">Más información</span><span class="sxs-lookup"><span data-stu-id="70a12-115">More Information</span></span>

[<span data-ttu-id="70a12-116">S/MIME para la firma y cifrado de mensajes</span><span class="sxs-lookup"><span data-stu-id="70a12-116">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="70a12-117">Herramienta de sincronización de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="70a12-117">Azure Active Directory Sync tool</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=392587)

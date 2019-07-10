---
title: Sincronizar certificados de usuario con Office 365 para S/MIME
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: Antes de poder enviar mensajes protegidos por S/MIME, deben configurarse los certificados apropiados. Para poder enviar mensajes cifrados mediante Exchange Online, el programa de correo electrónico del remitente usa el certificado público del destinatario para cifrar el mensaje. Este certificado X.509 público debe publicarse en Office 365.
ms.openlocfilehash: ad58b5663eaadf771ed1518edc01ce2f765f5202
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600693"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="dbc1b-105">Sincronizar certificados de usuario con Office 365 para S/MIME</span><span class="sxs-lookup"><span data-stu-id="dbc1b-105">Sync user certificates to Office 365 for S/MIME</span></span>

<span data-ttu-id="dbc1b-106">Para que cualquier persona pueda enviar mensajes protegidos por S/MIME en Exchange Online, deben configurarse los certificados apropiados.</span><span class="sxs-lookup"><span data-stu-id="dbc1b-106">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="dbc1b-107">Para enviar mensajes cifrados a través de Exchange Online, la aplicación de correo electrónico del remitente usa el certificado público del destinatario para cifrar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="dbc1b-107">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="dbc1b-108">Este certificado X.509 público debe publicarse en Office 365.</span><span class="sxs-lookup"><span data-stu-id="dbc1b-108">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="dbc1b-109">Para sincronizar los certificados que admiten S/MIME</span><span class="sxs-lookup"><span data-stu-id="dbc1b-109">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="dbc1b-110">Para comenzar a configurar S/MIME, emita los certificados y publíquelos en sus Servicios de directorio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dbc1b-110">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="dbc1b-111">Para obtener más información acerca de la administración de certificados en Exchange Server, consulte [digital Certificates and SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).</span><span class="sxs-lookup"><span data-stu-id="dbc1b-111">For more information about managing certificates in Exchange Server, see [Digital Certificates and SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).</span></span>

<span data-ttu-id="dbc1b-p104">Una vez publicados los certificados, use la Herramienta de sincronización de Microsoft Azure Active Directory para sincronizar los datos de usuario de su entorno local de Exchange con Office 365. Para obtener más información acerca de este proceso, consulte [DirSync: historial de publicación de las versiones de la herramienta de sincronización](https://go.microsoft.com/fwlink/p/?LinkId=392587).</span><span class="sxs-lookup"><span data-stu-id="dbc1b-p104">After your certificates are published, use the Azure Active Directory Sync tool to synchronize user data from your on-premises Exchange environment to Office 365. For more information on this process, see [DirSync: Directory Sync Tool Version Release History](https://go.microsoft.com/fwlink/p/?LinkId=392587).</span></span>

<span data-ttu-id="dbc1b-114">Además de sincronizar otros datos de directorio, para fines de S/MIME, la herramienta sincronizará los atributos **userCertificate** y **userSMIMECertificate** para cada objeto de usuario, de modo que los datos puedan usarse para firmar y cifrar mensajes.</span><span class="sxs-lookup"><span data-stu-id="dbc1b-114">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="dbc1b-115">Más información</span><span class="sxs-lookup"><span data-stu-id="dbc1b-115">More Information</span></span>

[<span data-ttu-id="dbc1b-116">S/MIME para la firma y cifrado de mensajes</span><span class="sxs-lookup"><span data-stu-id="dbc1b-116">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="dbc1b-117">Herramienta de sincronización de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="dbc1b-117">Azure Active Directory Sync tool</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=392587)

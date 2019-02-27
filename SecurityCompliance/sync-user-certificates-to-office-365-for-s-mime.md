---
title: Sincronizar certificados de usuario con Office 365 para S/MIME
ms.author: chrisda
author: chrisda
manager: Serdars
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: Antes de poder enviar mensajes protegidos por S/MIME, deben configurarse los certificados apropiados. Para poder enviar mensajes cifrados mediante Exchange Online, el programa de correo electrónico del remitente usa el certificado público del destinatario para cifrar el mensaje. Este certificado X.509 público debe publicarse en Office 365.
ms.openlocfilehash: 35de3ba34be48a8553c7034f646576e4fca8b870
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295003"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Sincronizar certificados de usuario con Office 365 para S/MIME

Para que cualquier persona pueda enviar mensajes protegidos por S/MIME en Exchange Online, deben configurarse los certificados apropiados. Para enviar mensajes cifrados a través de Exchange Online, la aplicación de correo electrónico del remitente usa el certificado público del destinatario para cifrar el mensaje. Este certificado X. 509 público debe publicarse en Office 365.

## <a name="to-sync-certificates-that-support-smime"></a>Para sincronizar los certificados que admiten S/MIME

Empiece a configurar S/MIME mediante la emisión de certificados y su publicación en el servicio de dominio local de Active Directory. Para obtener más información acerca de la administración de certificados en Exchange Server, consulte [digital Certificates and SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).

Una vez publicados los certificados, use la Herramienta de sincronización de Microsoft Azure Active Directory para sincronizar los datos de usuario de su entorno local de Exchange con Office 365. Para obtener más información acerca de este proceso, consulte [DirSync: historial de publicación de las versiones de la herramienta de sincronización](https://go.microsoft.com/fwlink/p/?LinkId=392587).

Además de sincronizar otros datos de directorio, para fines de S/MIME, la herramienta sincronizará los atributos **userCertificate** y **userSMIMECertificate** para cada objeto de usuario, de modo que los datos puedan usarse para firmar y cifrar mensajes.

## <a name="more-information"></a>Más información

[S/MIME para la firma y el cifrado de mensajes](s-mime-for-message-signing-and-encryption.md)

[Herramienta de sincronización de Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=392587)

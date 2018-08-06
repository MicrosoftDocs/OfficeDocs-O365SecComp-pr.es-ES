---
title: Sincronizar certificados de usuario con Office 365 para S/MIME
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: Antes de poder enviar mensajes protegidos por S/MIME, deben configurarse los certificados apropiados. Para poder enviar mensajes cifrados mediante Exchange Online, el programa de correo electrónico del remitente usa el certificado público del destinatario para cifrar el mensaje. Este certificado X.509 público debe publicarse en Office 365.
ms.openlocfilehash: aa94dfa6702a25b3fc6b8b883daceddf31d2f66a
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026197"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Sincronizar certificados de usuario con Office 365 para S/MIME

Antes de poder enviar mensajes protegidos por S/MIME, deben configurarse los certificados apropiados. Para poder enviar mensajes cifrados mediante Exchange Online, el programa de correo electrónico del remitente usa el certificado público del destinatario para cifrar el mensaje. Este certificado X.509 público debe publicarse en Office 365.
  
## <a name="to-sync-certificates-that-support-smime"></a>Para sincronizar los certificados que admiten S/MIME

Para comenzar a configurar S/MIME, emita los certificados y publíquelos en sus Servicios de directorio de Active Directory. Para obtener más información acerca de la administración de certificados en Exchange 2013, consulte [Digital Certificates and SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).
  
Una vez publicados los certificados, use la Herramienta de sincronización de Microsoft Azure Active Directory para sincronizar los datos de usuario de su entorno local de Exchange con Office 365. Para obtener más información acerca de este proceso, consulte [DirSync: historial de publicación de las versiones de la herramienta de sincronización](https://go.microsoft.com/fwlink/p/?LinkId=392587).
  
Además de sincronizar otros datos de directorio, para los fines de S/MIME, la herramienta sincronizará los atributos  `userCertificate` y  `userSMIMECertificate` para cada objeto de usuario de manera que los datos puedan usarse para firmar y cifrar mensajes. 
  
## <a name="more-information"></a>Más información

[S/MIME para la firma y el cifrado de mensajes](s-mime-for-message-signing-and-encryption.md)
  
[Herramienta de sincronización de Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=392587)
  


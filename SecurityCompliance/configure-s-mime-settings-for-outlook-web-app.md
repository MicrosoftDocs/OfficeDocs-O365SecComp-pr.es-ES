---
title: Configurar la configuración S/MIME en Exchange Online para Outlook en la web
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Breve descripción de lo que los administradores de Exchange Online deben hacer para ver y configurar la configuración S/MIME en Outlook en la web en Exchange Online.
ms.openlocfilehash: 74d2f37f0cabc0b49abdd78d2a10928b543fd615
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295363"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Configurar la configuración S/MIME en Exchange Online para Outlook en la web

Como administrador de Exchange Online, puede configurar Outlook en la web (anteriormente conocido como Outlook Web App) para permitir el envío y la recepción de mensajes protegidos por S/MIME. Use los cmdlets **Get-SmimeConfig** y **set-SmimeConfig** para ver y administrar esta característica en Exchange Online PowerShell. Para conectarse a Exchange Online PowerShell, consulte [conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) y [set-SmimeConfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx).

## <a name="considerations-for-chrome"></a>Consideraciones sobre Chrome

Para usar S/MIME en Outlook en la web en el explorador web Google Chrome, usted (u otro administrador) debe establecer y configurar la Directiva de cromo denominada **ExtensionInstallForcelist** para instalar la extensión S/MIME de Microsoft en Chrome. La Directiva debe usar la sintaxis: `<extension-id>;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` por ejemplo: `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`. Este paso es un requisito previo para usar Chrome; no reemplaza el control S/MIME instalado por los usuarios. Para obtener más información sobre la directiva **ExtensionInstallForcelist** , consulte [ExtensionInstallForcelist](http://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist).

## <a name="for-more-information"></a>Más información

[S/MIME para la firma y el cifrado de mensajes](s-mime-for-message-signing-and-encryption.md)

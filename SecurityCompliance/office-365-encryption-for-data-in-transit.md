---
title: Office 365 cifrado para los datos en tránsito
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 'Resumen: breve explicación de cómo Microsoft cifra los datos en tránsito.'
ms.openlocfilehash: 596b884ac76c9b138d01958363c7921acf926345
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275850"
---
# <a name="office-365-encryption-for-data-in-transit"></a>Office 365 cifrado para los datos en tránsito

Además de proteger los datos de clientes en reposo, Microsoft usa tecnologías de cifrado para proteger los datos de clientes de Office 365 en tránsito. 

Los datos están en tránsito:
- Cuando un equipo cliente se comunica con un servidor de Office 365;
- Cuando un servidor de Office 365 se comunica con otro servidor de Office 365; y
- Cuando un servidor de Office 365 se comunica con un servidor que no es Office 365 (por ejemplo, Exchange online que entrega el correo electrónico a un servidor de correo electrónico externo).

Las comunicaciones entre centros de recursos entre Office 365 Servers tienen lugar a través de TLS o IPsec, y todos los servidores orientados a clientes negocian una sesión segura mediante TLS con los equipos cliente (por ejemplo, Exchange online usa TLS 1,2 con la intensidad de cifrado de 256 bits (FIPS). se usa FIPS. 140-2 de nivel 2: validado). (Consulte [información de referencia técnica sobre el cifrado en Office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) para obtener una lista de los conjuntos de cifrado de TLS compatibles con Office 365). Esto se aplica a los protocolos que usan los clientes como Outlook, Skype empresarial y Outlook en la web (por ejemplo, HTTP, POP3, etc.).

Los certificados públicos los emite SSL de Microsoft IT con SSLAdmin, una herramienta interna de Microsoft para proteger la confidencialidad de la información transmitida. Todos los certificados emitidos por Microsoft IT tienen un mínimo de 2048 bits de longitud [](http://www.webtrust.org/homepage-documents/item70372.pdf) y el cumplimiento de WebTrust requiere SSLAdmin para asegurarse de que los certificados solo se emiten para las direcciones IP públicas que pertenecen a Microsoft. Las direcciones IP que no cumplan este criterio se enrutan a través de un proceso de excepción.

Todos los detalles de implementación, como la versión de TLS que se usa, si la confidencialidad directa (FS) está habilitada, el orden de los conjuntos de cifrado, etc., están disponibles públicamente. Una forma de ver estos detalles es usar un sitio web de terceros, como Qualys SSL Labs (www.ssllabs.com). A continuación se muestran los vínculos a páginas de prueba automatizadas desde Qualys que muestran información para los siguientes servicios:
- [Portal de Office 365](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [Exchange Online](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [SharePoint Online](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [Skype empresarial (SIP)](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [Skype empresarial (Web)](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [Exchange Online Protection](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [Microsoft Teams](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

Para la protección en línea de Exchange, las direcciones URL varían según los nombres de los inquilinos; sin embargo, todos los clientes pueden probar Office 365 mediante **Microsoft-com.mail.Protection.Outlook.com**.

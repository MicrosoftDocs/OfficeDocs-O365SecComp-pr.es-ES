---
title: Cifrado de Office 365 para los datos en tránsito
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: Una breve explicación de cómo Microsoft cifra los datos en tránsito.'
ms.openlocfilehash: 8f4781cf1127fb1b6bf742c267c76e3df39b8209
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535650"
---
# <a name="office-365-encryption-for-data-in-transit"></a>Cifrado de Office 365 para los datos en tránsito

Además de proteger los datos en reposo de cliente, Microsoft usa tecnologías de cifrado para proteger los datos de cliente de Office 365 en tránsito. 

Datos están en tránsito:
- Cuando un equipo cliente se comunica con un servidor de Office 365.
- Cuando un servidor de Office 365 se comunica con otro servidor de Office 365; y
- Cuando un servidor de Office 365 se comunica con un servidor que no sean Office 365 (por ejemplo, Exchange Online enviando correo electrónico a un servidor de correo electrónico externas).

Centro de datos entre las comunicaciones entre los servidores de Office 365 se lleva a cabo a través de TLS o IPsec, y todos los servidores orientados al cliente negocian una sesión segura con TLS con los equipos cliente (por ejemplo, Exchange Online usa se utiliza TLS 1.2 con intensidad de cifrado de 256 bits (FIPS Nivel de 140-2 validan 2). (Consulte los [Detalles de referencia técnica acerca del cifrado en Office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) para obtener una lista de conjuntos de cifrado TLS compatibles con Office 365). Esto se aplica a los protocolos que se usan clientes como Outlook, Skype para la empresa y Outlook en la web (por ejemplo, HTTP, POP3, etcetera).

Los certificados públicos emitidos por Microsoft IT SSL con SSLAdmin, una herramienta interna de Microsoft para proteger la confidencialidad de la información transmitida. Todos los certificados emitidos por Microsoft IT tengan un mínimo de 2048 bits de longitud y cumplimiento [Webtrust](http://www.webtrust.org/homepage-documents/item70372.pdf) requiere SSLAdmin para asegurarse de que los certificados se emiten únicamente a las direcciones IP públicas que pertenecen a Microsoft. Todas las direcciones IP que no cumplen este criterio se enrutan a través de un proceso de excepción.

Todos los detalles de la implementación, como la versión de TLS usada, si está habilitada la confidencialidad hacia delante (FS), el orden de los conjuntos de aplicaciones de cifrado, etc., están disponibles públicamente. Una manera de ver estos detalles consiste en usar un sitio Web de terceros, como Qualys SSL laboratorios (www.ssllabs.com). A continuación están los vínculos a las páginas de prueba automatizada en Qualys que muestran información de los siguientes servicios:
- [Portal de Office 365](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [Exchange Online](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [SharePoint Online](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [Skype para la empresa (SIP)](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [Skype para la empresa (Web)](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [Exchange Online Protection](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [Microsoft Teams](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

Para Exchange Online Protection, las direcciones URL pueden variar por nombres de inquilino; Sin embargo, todos los clientes pueden probar Office 365 con **microsoft com.mail.protection.outlook.com**.

---
title: Direcciones de IP para Exchange Online Protection
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: eb14f38b-7b55-4a47-84a0-4a56a59e4111
description: Microsoft Exchange Online Protection (EOP) utiliza las siguientes direcciones IP del centro de datos de Microsoft al enviar correo electrónico, recibirlo o para el portal y los servicios administrativos de Exchange Online Protection. Para enviar y recibir mensajes de EOP o utilizar los servicios administrativos, asegúrese de que la red permite conexiones desde estas direcciones IP.
ms.openlocfilehash: 6c7d8c78a012be3928317eac1e9b6fcdeab64a24
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30222829"
---
# <a name="exchange-online-protection-ip-addresses"></a>Direcciones de IP para Exchange Online Protection

Microsoft Exchange Online Protection (EOP) utiliza las siguientes direcciones IP del centro de datos de Microsoft al enviar correo electrónico, recibirlo o para el portal y los servicios administrativos de Exchange Online Protection. Para enviar y recibir mensajes de EOP o utilizar los servicios administrativos, asegúrese de que la red permite conexiones desde estas direcciones IP.
 
> [!NOTE]
> Microsoft ha desarrollado un servicio Web basado en REST para las entradas de dirección IP y FQDN de esta página. Este nuevo servicio le ayuda a configurar y actualizar los dispositivos perimetrales de red, como firewalls y servidores proxy. Puede descargar la lista de puntos de conexión, la versión actual de la lista o los cambios específicos. Este servicio reemplaza el documento XML, la fuente RSS y las entradas de dirección IP y FQDN de esta página. Para probar este nuevo servicio, vaya a [Office 365 IP address and URL Web Service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service). 
 
## <a name="eop-ip-address-ranges"></a>Intervalos de direcciones IP para EOP

||||
|:-----|:-----|:-----|
|**Intervalos de direcciones IPv4** <br/> |**Intervalos de direcciones IPv6** <br/> |
| 23.103.132.0/22 | 2a01:111: F400:7c00::/54 |
| 23.103.136.0/21 | 2a01:111: F400: fc00::/54 |
| 23.103.144.0/20 | 2a01:111: F403::/48 |
| 23.103.198.0/23 |  |
| 23.103.200.0/22 |  |
| 40.92.0.0/14 |  |
| 40.107.0.0/17 |  |
| 52.100.0.0/14 |  |
| 52.238.78.88/32 |  |
| 65.55.88.0/24 |  |
| 65.55.169.0/24 |  |
| 94.245.120.64/26 |  |
| 104.47.0.0/17 |  |
| 157.55.234.0/24 |  |
| 157.56.110.0/23 |  |
| 157.56.112.0/24 |  |
| 207.46.100.0/24 |  |
| 207.46.163.0/24 |  |
| 213.199.154.0/24 |  |
| 213.199.180.128/26 |  |
| 216.32.180.0/23 |  |
||||
 
> [!IMPORTANT]
> Los intervalos de direcciones IP que se proporcionan aquí solo se usan para la retransmisión a través de conectores de cliente. Los cambios en la lista de direcciones IP son poco frecuentes y se comunican por adelantado. Para asegurarse de que los mensajes que envía a sus socios comerciales, un host inteligente o un entorno local se enrutan a través del intervalo de direcciones IP publicadas del servicio, debe configurar el conector correcto para el enrutamiento a cada destino. Para obtener más información acerca de los conectores, consulte [decidir qué conector usar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail). las direcciones IP de este tema pueden cambiar con el tiempo.  
 
Para obtener más información sobre las direcciones IP utilizadas por Microsoft Office 365, vea [Intervalos de direcciones IP y URL de Office 365](https://go.microsoft.com/fwlink/p/?LinkId=324165).


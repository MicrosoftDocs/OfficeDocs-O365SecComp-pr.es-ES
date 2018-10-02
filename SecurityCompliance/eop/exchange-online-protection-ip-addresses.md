---
title: Direcciones de IP para Exchange Online Protection
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/2/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: eb14f38b-7b55-4a47-84a0-4a56a59e4111
description: Microsoft Exchange Online Protection (EOP) utiliza las siguientes direcciones IP del centro de datos de Microsoft al enviar correo electrónico, recibirlo o para el portal y los servicios administrativos de Exchange Online Protection. Para enviar y recibir mensajes de EOP o utilizar los servicios administrativos, asegúrese de que la red permite conexiones desde estas direcciones IP.
ms.openlocfilehash: 5742c19f98f8515670150f69c421c19ffecc7668
ms.sourcegitcommit: b6473cd6ba3f9ac79dc6a2040fc148020dfbe464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "25358369"
---
# <a name="exchange-online-protection-ip-addresses"></a>Direcciones de IP para Exchange Online Protection

Microsoft Exchange Online Protection (EOP) utiliza las siguientes direcciones IP del centro de datos de Microsoft al enviar correo electrónico, recibirlo o para el portal y los servicios administrativos de Exchange Online Protection. Para enviar y recibir mensajes de EOP o utilizar los servicios administrativos, asegúrese de que la red permite conexiones desde estas direcciones IP.
 
> [!NOTE]
> Microsoft ha desarrollado un servicio web basado en REST para la dirección IP y las entradas de FQDN en esta página. Este nuevo servicio le ayuda a configurar y actualizar los dispositivos de perímetro de red, como firewalls y servidores proxy. Puede descargar la lista de extremos, la versión actual de la lista o cambios específicos. Este servicio reemplaza el documento XML, la fuente RSS y la dirección IP y las entradas de FQDN en esta página. Para probar este nuevo servicio, vaya al [servicio Web](https://support.office.com/article/managing-office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#webservice). 
 
## <a name="eop-ip-address-ranges"></a>Intervalos de direcciones IP para EOP

||||
|:-----|:-----|:-----|
|**Intervalos de direcciones IPv4** <br/> |**Intervalos de direcciones IPv6** <br/> |
| 23.103.132.0/22 | c 2a01:111:f400:7 00:: / 54 |
| 23.103.136.0/21 | 2a01:111:f400:fc00:: / 54 |
| 23.103.144.0/20 | 2a01:111:f403:: / 48 |
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
> Los intervalos de direcciones IP proporcionados aquí solo se usan para retransmitir a través de conectores de atención al cliente. Los cambios realizados en la lista de direcciones IP son poco frecuentes y se comunican con antelación. Para asegurarse de que los mensajes que envíe a sus socios comerciales, un host inteligente o una ruta de entorno local a través del servicio publicado intervalo de direcciones IP, debe configurar el conector correcto para el enrutamiento a cada destino. Para obtener más información acerca de los conectores, vea [Decidir que conector que va a usar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail). las direcciones IP en este tema pueden cambiar con el tiempo. Para un registro de la dirección IP de todas las direcciones que se han agregado, cambiado o en desuso en el año pasado, vea [notificación de cambio para las direcciones IP de elevación de privilegios](change-notification-for-eop-ip-addresses.md). 
 
Para obtener más información sobre las direcciones IP utilizadas por Microsoft Office 365, vea [Intervalos de direcciones IP y URL de Office 365](https://go.microsoft.com/fwlink/p/?LinkId=324165).


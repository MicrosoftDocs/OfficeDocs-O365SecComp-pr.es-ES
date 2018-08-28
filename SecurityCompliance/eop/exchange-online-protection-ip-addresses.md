---
title: Direcciones de IP para Exchange Online Protection
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 8/2/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: eb14f38b-7b55-4a47-84a0-4a56a59e4111
description: Microsoft Exchange Online Protection (EOP) utiliza las siguientes direcciones IP del centro de datos de Microsoft al enviar correo electrónico, recibirlo o para el portal y los servicios administrativos de Exchange Online Protection. Para enviar y recibir mensajes de EOP o utilizar los servicios administrativos, asegúrese de que la red permite conexiones desde estas direcciones IP.
ms.openlocfilehash: 853b64410969fcc2f3c9ef238d2e9f4a4bb36e7b
ms.sourcegitcommit: edf5db9357c0d34573f8cc406314525ef10d1eb9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23230012"
---
# <a name="exchange-online-protection-ip-addresses"></a>Direcciones de IP para Exchange Online Protection

Microsoft Exchange Online Protection (EOP) utiliza las siguientes direcciones IP del centro de datos de Microsoft al enviar correo electrónico, recibirlo o para el portal y los servicios administrativos de Exchange Online Protection. Para enviar y recibir mensajes de EOP o utilizar los servicios administrativos, asegúrese de que la red permite conexiones desde estas direcciones IP.
 
> [!NOTE]
> Microsoft está desarrollando un servicio web basado en REST para la dirección IP y las entradas de FQDN en esta página. Este nuevo servicio le ayudará a configurar y actualizar los dispositivos de perímetro de red, como firewalls y servidores proxy. Puede descargar la lista de extremos, la versión actual de la lista o cambios específicos. Este servicio finalmente reemplazará el documento XML, la fuente RSS y la dirección IP y las entradas de FQDN en esta página. Para probar este nuevo servicio, vaya al [servicio Web](https://support.office.com/article/managing-office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#webservice). 
 
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
 
## <a name="ip-ranges-by-region"></a>Intervalos IP por región

Exchange Online Protection enruta el correo de la forma más eficaz y, a la vez, nos permite cumplir con nuestras obligaciones contractuales con los clientes. Teniendo esto en cuenta, los puntos de conexión de EOP siguientes conforman la lista actual de intervalos IPv4 regionales. En cambio, puede que estas direcciones IP se vuelvan a aprovisionar a otra función de EOP sin previo aviso para mejorar la capacidad y la eficacia. En estos eventos, el correo seguirá funcionando en función de nuestras obligaciones contractuales, y haremos todo lo posible para actualizar esta lista de puntos de conexión de forma puntual tras realizar cambios. En estos momentos, no mantenemos listas de puntos de conexión regionales para otros componentes de Office 365.
 
||||
|:-----|:-----|:-----|
|**América** <br/> |**EMEA** <br/> |**APAC** <br/> |
| 23.103.132.0/22 | 23.103.132.0/22 |23.103.136.0/21 |
| 23.103.136.0/21 | 23.103.144.0/22 |23.103.152.0/22 |
| 23.103.148.0/22 | 40.92.0.0/18 |40.92.128.0/17 |
| 23.103.152.0/21 | 40.93.0.0/18 |40.93.128.0/17 |
| 23.103.156.0/22 | 40.94.0.0/18 |40.94.128.0/17 |
| 23.103.198.0/24 | 40.95.0.0/18 |40.95.128.0/17 |
| 23.103.200.0/22 | 40.107.0.0/18 |52.100.128.0/17 |
| 40.92.64.0/18 | 52.100.0.0/18 |52.101.128.0/17 |
| 40.93.64.0/18 | 52.101.0.0/18 |52.102.128.0/17 |
| 40.94.64.0/18 | 52.102.0.0/18 |52.103.128.0/17 |
| 40.95.64.0/18 | 52.103.0.0/18 |65.55.88.0/24 |
| 40.107.64.0/18 | 94.245.120.64/27 |104.47.64.0/18 |
| 52.100.64.0/18 | 104.47.0.0/19 |c 2a01:111:f400:7 00:: / 54 |
| 52.101.64.0/18 | 157.55.234.0/24 |  |
| 52.102.64.0/18 | 157.56.112.0/24 | |
| 52.103.64.0/18 | 213.199.154.0/24 | |
| 65.55.169.0/24 | 213.199.180.128/26 | |
| 104.47.32.0/19 | 2a01:111:f400:7e00:: / 56 | |
| 157.56.110.0/23 | 2a01:111:f400:fe00:: / 56 | |
| 207.46.100.0/24 |  | |
| 207.46.163.0/24 |  | |
| 216.32.180.0/23 |  | |
| c 2a01:111:f400:7 00:: / 54 |  | |
||||


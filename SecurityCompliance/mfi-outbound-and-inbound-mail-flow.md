---
title: Flujo de correo entrante y saliente
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 8/7/2018
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Los administradores pueden Obtenga información sobre la salida y el widget de flujo de correo entrante en el panel de flujo de correo en el centro de cumplimiento de seguridad de Office 365 &.
ms.openlocfilehash: 57792c0347490b40f97a8b92945a9c809484ba4f
ms.sourcegitcommit: 25fb33a1f8b2844fde15f6c03db2936c610824e0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2019
ms.locfileid: "28685652"
---
# <a name="outbound-and-inbound-mail-flow"></a>Flujo de correo entrante y saliente

El widget de **flujo de correo entrante y saliente** combina la información desde el **Informe de conector** y el primer **Informe de información general de TLS** en un solo lugar.

![El informe de flujo de correo de entrada y salida en el panel de flujo de correo en el centro de cumplimiento de seguridad de Office 365 &](media/2c591d1c-bad6-4b72-890e-f8fdfd4f447a.png)

La información en el widget está relacionada con los conectores y protección de mensajes TLS en Office 365. Para obtener más información, vea estos temas:

- [Configure mail flow using connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx)

- [Empleo de TLS por parte de Exchange Online para proteger las conexiones de correo electrónico en Office 365](https://support.office.com/article/4CDE0CDA-3430-4DC0-B489-F2C0736C929F)

## <a name="message-protected-in-transit-by-tls"></a>Mensaje protegido en tránsito (por TLS)

El widget de **flujo de correo entrante y saliente** muestra el cifrado TLS que se usa para la conexión cuando los mensajes se envían a y desde la organización de Office 365. Las conexiones que se establecen con otros servicios de correo electrónico se cifran mediante TLS cuando TLS se ofrece por ambos lados. El widget ofrece una instantánea de la última semana del flujo de correo. Al hacer clic en **Ver detalles**, el emergente **mensaje protegido en tránsito (por TLS)** muestra la protección de TLS para los mensajes entran y salen de la organización.

![Los mensajes protegidos en tránsito (por TLS) emergente en el centro de cumplimiento de seguridad de Office 365 &](media/825aa74c-413d-4141-8e3c-dfe68ae78eed.png)

En la actualidad, 1.2 TLS es la versión más segura de TLS que se ofrece por Office 365. A menudo, necesitará saber el cifrado TLS que se utiliza para las auditorías de cumplimiento. Es probable que no tenga una relación directa con la mayoría de los servidores correo electrónico de origen y de destino (no dispone de ellas y ni hace Microsoft), por lo que no tienen muchas opciones para mejorar el cifrado TLS que se usa en esos servidores.

Pero, puede usar [los conectores](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx) para garantizar la mejor TLS protección disponible para los mensajes enviados entre los servidores de correo electrónico y Office 365. Flujo de correo entre Office 365 y sus propios servidores de correo electrónico o servidores que pertenecen a los socios a menudo es más importante y sensibles que no son mensajes regulares, por lo que se desea aplicar seguridad adicional y vigilancia a esos mensajes. Puede actualizar o corregir sus propios servidores de correo electrónico para mejorar el cifrado TLS que se está usando o llega a los socios para hacer lo mismo. El **Conector de informe** muestra el volumen del flujo de correo y el cifrado TLS para los mensajes que utilizan los conectores de Office 365.

## <a name="connector-report"></a>Informe de conector

Al hacer clic en el vínculo de **Informe de conector** del elemento de **mensaje protegido en tránsito (por TLS)** , el informe muestra información sobre los mensajes que se entregan a y desde la organización de Office 365 mediante conectores. Usar los conectores entre sus propios servidores de correo electrónico y Office 365 o su socio servidores y Office 365. El volumen de mensaje para cada conector y el cifrado TLS para la conexión están disponibles. Además, también puede ver los datos para los mensajes que se han enviado o recibido en Office 365 sin usar un conector.

La vista de **Flujo de correo** muestra el volumen de mensajes a través del conector de la semana pasada. Puede cambiar el intervalo de fechas mediante la selección de **filtro** , donde puede aumentar el intervalo a un máximo de 30 días. La vista de **Todo el flujo de correo** muestra todo el correo fluya hacia y desde la organización de Office 365 a través de todos los conectores. Puede seleccionar un conector específico por su nombre en el menú desplegable.

Puede seleccionar la vista **uso de TLS** en el desplegable hacia abajo para ver el desglose de protección de TLS para los mensajes a través del conector. Como con el informe de **Informe de información general de TLS** , esta vista muestra el porcentaje de las diferentes versiones TLS. Para las conexiones TLS 1.0, necesita realmente obtener su servidor de correo electrónico o servidor de su compañero actualizado o fijo evitar cualquier problema al soporte técnico de TLS 1.0 finalmente está en desuso en Office 365. Para obtener más información, vea [los detalles de referencia técnica acerca del cifrado en Office 365](https://support.office.com/article/862cbe93-4268-4ef9-ba79-277545ecf221).

Entendimiento de elija conectores para ayudar a dirigir su atención a los posibles problemas de cifrado TLS para el conector. Las perspectivas son: **TLS No es más del 25%** o **TLS 1.0 es superior al 50%**. Si ve estas perspectivas, debe investigar los servidores de correo electrónico que están asociados con el conector o llegar a su organización asociada.

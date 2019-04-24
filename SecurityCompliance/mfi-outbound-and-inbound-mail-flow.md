---
title: Flujo de correo entrante y saliente
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 8/7/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Los administradores pueden obtener información sobre el widget de flujo de correo entrante y saliente en el panel de flujo de correo en el centro de seguridad & cumplimiento.
ms.openlocfilehash: 89408618e7c5b3c921382b3efa0257f263509b6d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32252228"
---
# <a name="outbound-and-inbound-mail-flow"></a>Flujo de correo entrante y saliente

El widget de **flujo de correo entrante y** saliente combina la información del **Informe de conector** y el anterior **Informe de información general de TLS** en un único punto.

![El informe de flujo de correo entrante y saliente en el panel de flujo de correo en el centro de seguridad & cumplimiento](media/2c591d1c-bad6-4b72-890e-f8fdfd4f447a.png)

La información del widget está relacionada con los conectores y la protección de mensajes TLS en Office 365. Para obtener más información, vea estos temas:

- [Configure mail flow using connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx)

- [Cómo Exchange Online usa TLS para proteger las conexiones de correo electrónico en Office 365](https://support.office.com/article/4CDE0CDA-3430-4DC0-B489-F2C0736C929F)

## <a name="message-protected-in-transit-by-tls"></a>Mensaje protegido en tránsito (por TLS)

El widget de **flujo de correo entrante y** saliente muestra el cifrado TLS que se usa para la conexión cuando los mensajes se entregan a y desde la organización de Office 365. Las conexiones que se establecen con otros servicios de correo electrónico se cifran mediante TLS cuando se ofrece TLS por ambas partes. El widget ofrece una instantánea de la última semana del flujo de correo. Al hacer clic en **Ver detalles**, el control flotante de **mensaje protegido en tránsito (por TLS)** muestra la protección de TLS para los mensajes que entran y salen de la organización.

![El control flotante de mensajes protegidos en tránsito (por TLS) en el centro de seguridad & cumplimiento](media/825aa74c-413d-4141-8e3c-dfe68ae78eed.png)

Actualmente, TLS 1,2 es la versión más segura de TLS que ofrece Office 365. A menudo, necesitará conocer el cifrado de TLS que se usa para las auditorías de cumplimiento. Probablemente no tiene una relación directa con la mayoría de los servidores de correo electrónico de origen y de destino (no es propietario de ellos, ni tampoco Microsoft), por lo que no tiene muchas opciones para mejorar el cifrado de TLS que usan dichos servidores.

Sin embargo, puede usar [conectores](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx) para garantizar la mejor protección de TLS disponible para los mensajes que se envían entre los servidores de correo electrónico y Office 365. El flujo de correo entre Office 365 y sus propios servidores de correo electrónico o servidores que pertenecen a sus socios suele ser más importante y sensible que los mensajes normales, por lo que querrá aplicar seguridad y vigilancia adicionales a dichos mensajes. Puede actualizar o arreglar sus propios servidores de correo electrónico para mejorar el cifrado TLS que se está usando o llegar a sus asociados para hacer lo mismo. El **Informe de conectores** muestra el volumen del flujo de correo y el cifrado TLS para los mensajes que usan los conectores de Office 365.

## <a name="connector-report"></a>Informe de conector

Al hacer clic en el vínculo del **Informe del conector** desde el control flotante **protegido en tránsito (por TLS)** , el informe muestra información acerca de los mensajes que se entregan a y desde la organización de Office 365 mediante conectores. Use conectores entre sus propios servidores de correo electrónico y Office 365 o los servidores de su compañero y Office 365. El volumen del mensaje para cada conector y el cifrado TLS para la conexión está disponible. Además, también puede ver los datos de los mensajes que se enviaron o recibieron en Office 365 sin usar un conector.

La vista de **flujo de correo** muestra el volumen de mensajes a través del conector de la semana pasada. Puede cambiar el intervalo de fechas seleccionando **filtro** , donde puede aumentar el intervalo a un máximo de 30 días. La vista **todo el flujo de correo** muestra todo el flujo de correo hacia y desde la organización de Office 365 a través de todos los conectores. Puede seleccionar un conector específico por nombre en el menú desplegable.

Puede seleccionar la vista de **uso de TLS** de la lista desplegable para ver el desglose de la protección TLS para los mensajes a través del conector. Al igual que con el informe de **Informe General de TLS** , esta vista muestra el porcentaje de las diferentes versiones de TLS. Para las conexiones TLS 1,0, es necesario que el servidor de correo electrónico o el servidor de su compañero se actualice o se corrija para evitar problemas cuando la compatibilidad con TLS 1,0 está en desuso en Office 365. Para obtener más información, vea [información de referencia técnica sobre el cifrado en Office 365](https://support.office.com/article/862cbe93-4268-4ef9-ba79-277545ecf221).

La información apunta a los conectores para ayudar a atraer la atención sobre posibles problemas de cifrado de TLS para el conector. La información es: **ningún TLS es superior al 25%** o **TLS 1,0 es superior al 50%**. Si ve esta información, debe investigar los servidores de correo electrónico que están asociados con el conector o ponerse en contacto con la organización asociada.

## <a name="see-also"></a>Vea también

Para obtener más información acerca de otras indicaciones de flujo de correo en el panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad _AMP_ cumplimiento](mail-flow-insights.md).

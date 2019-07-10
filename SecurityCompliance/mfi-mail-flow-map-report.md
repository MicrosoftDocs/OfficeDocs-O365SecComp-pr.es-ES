---
title: Informe de mapa de flujo de correo
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Los administradores pueden obtener información sobre el informe de mapa de flujo de correo en el panel de flujo de correo en el centro de seguridad & cumplimiento.
ms.openlocfilehash: 04ffbdc339a084f3ae2bf9947469966f1a868d02
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35601027"
---
# <a name="mail-flow-map-report"></a>Informe de mapa de flujo de correo

Este informe proporciona información sobre cómo fluye el correo a través de la organización de Office 365. Puede usar esta información para aprender patrones, identificar anomalías y corregir problemas a medida que se produzcan.

![El informe de mapa de flujo de correo en el panel de flujo de correo en el centro de seguridad & cumplimiento](media/mail-flow-map-selected.png)

## <a name="mail-flow-map-widget"></a>Widget de mapa de flujo de correo

De forma predeterminada, el mapa de flujo de correo muestra el patrón de flujo de correo de alto nivel del día anterior. Puede usar las flechas izquierda y derecha para los distintos días. Al colocar el cursor del mouse sobre cada área del informe, se mostrará el volumen de correo desde y hacia la organización de Office 365, tal como se muestra en el siguiente diagrama:

![Flechas izquierda y derecha en el widget mapa de flujo de correo](media/mail-flow-map-widget.png)

## <a name="overview"></a>Información general

Al hacer clic en el widget **mapa de flujo de correo** , irá al informe de mapa de flujo de **correo** . Aquí puede ver el nivel de informe más granular, puede hacer clic en ver tabla de detalles para ver los datos detallados. También puede descargar el informe detallado haciendo clic en Request Report.

![Vista general en el informe de mapa de flujo de correo](media/mail-flow-map-overview.png)

## <a name="details"></a>Detalles

De forma predeterminada, **Mostrar datos para** se establece en el valor **información general**. Al hacer clic en la lista desplegable y seleccionar **detalles**, la vista cambia a los detalles del nivel de dominio.

![Seleccione detalle en Mostrar datos para en la vista de información general en el informe de mapa de flujo de correo](media/mail-flow-map-select-detail.png)

Se enumeran los dominios principales de remitente y destinatario, y el resto se colocará en **otros** como se muestra en los siguientes diagramas:

![Vista de detalles en el informe de mapa de flujo de correo](media/mail-flow-map-detail.png)

## <a name="related-insights"></a>Información relacionada

La información relacionada se muestra debajo del mapa de flujo de correo si está disponible (por ejemplo, el conocimiento del dominio del remitente o el conocimiento del bucle de correo).

## <a name="see-also"></a>Vea también

Para obtener más información acerca de otras indicaciones del flujo de correo en el panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).
---
title: Comparación de versiones de cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
description: Ayuda a explicar las diferencias en las características de entregar con distintas versiones de Office 365 Message Encryption, así como el modo en los dos continuarán para que funcionen conjuntamente.
ms.openlocfilehash: a418d840c7e0eb50ae076bf2b03164bef9488058
ms.sourcegitcommit: 88f3982217c29b558e3f9e838bcb425da395dd5e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2019
ms.locfileid: "29708547"
---
# <a name="compare-versions-of-ome"></a>Comparar versiones de OME

En este artículo se compara heredado Office 365 Message Encryption para las nuevas capacidades OME. Las nuevas capacidades son una fusión y la versión más reciente de OME y de Information Rights Management (IRM). También trataremos cómo pueden coexistir los dos en la organización de Office 365.

||
|:-----|
|En este artículo es parte de una serie de artículos sobre Office 365 Message Encryption más grande. En este artículo está destinada a los administradores y profesionales de TI. Si sólo está buscando información en enviar o recibir un mensaje cifrado, vea la lista de los artículos de [Office 365 Message Encryption (OME)](ome.md) y busque el artículo que mejor se adapte a sus necesidades. |
||

## <a name="side-by-side-comparison-of-features-and-capabilities"></a>Comparación de características y funciones

|                                   |Características antiguas       |                   |Características nuevas              |
|-----------------------------------|-------------------|-------------------|--------------------------|
|**Función**                     | **OME heredado**    | **IRM**           | **Nuevas capacidades OME** |
|*Enviar un correo cifrado*        |A través de reglas de flujo de correo de Exchange|Para el usuario final iniciado desde el escritorio de Outlook o Outlook en la Web; o a través de Exchange de reglas de flujo de correo|Para el usuario final iniciado desde el escritorio de Outlook, Outlook para Mac o Outlook en la Web; a través de las reglas de transporte de Exchange y prevención de pérdida de datos (DLP) de Office 365|
|*Plantilla de derechos de administración*       |   N/D      |Realice la opción no reenviar y las plantillas personalizadas|Realice la opción no reenviar, opción sólo cifrar y las plantillas personalizadas|
|*Tipo de destinatario*                   |Destinatarios internos y externos|Sólo los destinatarios internos         |Destinatarios internos y externos|
|*Experiencia para el destinatario interno*|Los destinatarios reciben un mensaje HTML, que se puedan descargan y abrirán en un explorador web o una aplicación móvil|Experiencia en línea nativo en los clientes de Outlook|Experiencia en línea nativo para los destinatarios de Office 365. Todos los otros destinatarios pueden leer mensaje desde el portal de OME (ninguna descarga ni aplicación necesarios).|
|*Experiencia para los destinatarios externos*|Los destinatarios reciben un mensaje HTML, que se puedan descargan y abrirán en un explorador web o una aplicación móvil|N/D|Experiencia en línea nativo para los destinatarios de Office 365. Todos los otros destinatarios pueden leer mensaje desde el portal de OME (ninguna descarga ni aplicación necesarios).|
|*Permisos de los datos adjuntos*           |No hay restricciones en los datos adjuntos|Los datos adjuntos están protegidos|Los datos adjuntos están protegidos de la opción de no reenviar y las plantillas personalizadas. Los administradores pueden elegir si los datos adjuntos para la opción de cifrar sólo están protegidos o no.|
|*Traer su propio soporte clave (BYOK)*|Ninguno                |Ninguno               |BYOK compatibles          |
||

## <a name="advantages-of-using-the-new-ome-capabilities-over-legacy-ome"></a>Ventajas de usar las nuevas capacidades OME OME heredado

Las nuevas capacidades ofrecen las siguientes ventajas:

- Capacidad de usar cifrar sólo (que permite la colaboración segura), no reenviar, así como restricciones personalizadas.
- Los remitentes pueden enviar mensajes de correo cifrados con las nuevas capacidades manualmente desde el escritorio de Outlook, Outlook para Mac y Outlook en los clientes web.
- Obtener destinatarios de Office 365 usar una experiencia en línea en los clientes de Outlook compatibles. Como alternativa, pueden elegir los administradores mostrar una experiencia de marca de los destinatarios de Office 365.
- Cuentas fuera de Office 365, como las cuentas de Gmail, Yahoo y Microsoft, son contactos asociados externos con el portal de OME, que proporciona una mejor experiencia de usuario para estos destinatarios. Todas las otras identidades utilice un código de acceso única para tener acceso a los mensajes cifrados.
- Los administradores pueden personalizar la personalización de marca y crear varias plantillas de personalización de marca.
- Los administradores pueden revocar mensajes de correo electrónico cifrados con las nuevas capacidades.
- Las nuevas capacidades proporcionan informes de uso detallados a través de la seguridad &amp; centro de cumplimiento.

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>Coexistencia de OME heredado y las nuevas capacidades en el mismo arrendatario

Puede usar OME heredado y las nuevas capacidades en el mismo arrendatario. Como administrador, para ello, elegir qué versión de OME que va a usar al crear reglas de flujo de correo de.

- Para especificar la versión heredada de OME, use la acción de regla de flujo de correo de Exchange "Aplicar la versión anterior de OME".
- Para especificar las nuevas capacidades, use el correo flujo regla acción "aplicar Office 365 mensaje cifrado y derechos de protección de Exchange".

Los usuarios también pueden enviar mensajes de correo cifrados con las nuevas capacidades manualmente desde el escritorio de Outlook, Outlook para Mac y Outlook en los clientes web.

## <a name="migrating-from-legacy-ome-to-the-new-capabilities"></a>Migración de OME heredado a las nuevas capacidades

Aunque ambas versiones de OME pueden coexistir, es muy recomendable que modificar las reglas de flujo de correo antiguo que utilice la acción de regla "Se aplican a la versión anterior de OME" para usar las nuevas capacidades mediante la especificación de la acción de regla de flujo de correo "aplicar mensaje cifrado de Office 365 derechos y protección". Para obtener instrucciones, consulte [definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md).

## <a name="getting-started-with-ome"></a>Introducción a OME

Normalmente, las nuevas capacidades OME se habilitan automáticamente para la organización de Office 365. Si está listo para empezar a usar las nuevas capacidades OME dentro de la organización, consulte [Configurar nuevas capacidades de cifrado de mensajes de Office 365](set-up-new-message-encryption-capabilities.md).

Si ha habilitado la protección de la información de Azure, se habilita automáticamente la versión heredada de OME para la organización de Office 365. En el pasado, ha funcionado OME heredado incluso si no se ha habilitado la protección de la información de Azure. Ya no es el caso.

Para empezar a usar OME heredado, si ha habilitado la protección de la información de Azure, todo lo que necesita hacer es configurar reglas de flujo de correo que utilizan la acción de regla "Aplicar la versión anterior de OME". Para obtener instrucciones, consulte [definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md).
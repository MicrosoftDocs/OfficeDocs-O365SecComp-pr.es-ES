---
title: Comparación de versiones de cifrado de mensajes (OME) de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Ayuda a explicar las diferencias en las características proporcionadas con diferentes versiones del cifrado de mensajes de Office 365 y la forma en que los dos continúan trabajando juntos.
ms.openlocfilehash: bb13208e2b630c8a6217b78b48a4cd3bb4b0de79
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262332"
---
# <a name="compare-versions-of-ome"></a>Comparar versiones de OME

En este artículo se compara el cifrado de mensajes de Office 365 heredado (OME) con las nuevas capacidades de OME. Las nuevas funciones son una fusión y una versión más reciente tanto de OME como de Information Rights Management (IRM). También se describen las características únicas de la implementación en GCC High. También trataremos cómo pueden coexistir los dos en su organización de Office 365.

||
|:-----|
|Este artículo forma parte de una amplia serie de artículos sobre el cifrado de mensajes de Office 365. Este artículo está destinado a los administradores y ITPros. Si solo está buscando información sobre cómo enviar o recibir un mensaje cifrado, vea la lista de artículos en el cifrado de [mensajes de Office 365 (OME)](ome.md) y busque el artículo que mejor se adapte a sus necesidades. |
||

## <a name="side-by-side-comparison-of-features-and-capabilities"></a>Comparación en paralelo de las características y capacidades

|                                   |Características antiguas       |                   |Características nuevas              |
|-----------------------------------|-------------------|-------------------|--------------------------|
|**Función**                     | **OME heredado**    | **IRM**           | **Nuevas funciones de OME** |
|*Enviar un correo cifrado*        |Mediante reglas de flujo de correo de Exchange|Usuario final iniciado desde un equipo de escritorio de Outlook o Outlook en la web; o mediante reglas de flujo de correo de Exchange|Usuario final iniciado desde el escritorio de Outlook, Outlook para Mac o Outlook en la web; mediante reglas de flujo de correo de Exchange (también conocidas como reglas de transporte) y la prevención de pérdida de datos (DLP) de Office 365|
|*Plantilla de administración de derechos*       |   N/D      |No reEnviar opciones y plantillas personalizadas|Opción no reEnviar, opción de solo codificación y plantillas personalizadas|
|*Tipo de destinatario*                   |Destinatarios internos y externos|Solo destinatarios internos         |Destinatarios internos y externos|
|*Experiencia para destinatario interno*|Los destinatarios reciben un mensaje HTML que descargan y abren en un explorador Web o en una aplicación móvil|Experiencia en línea nativa en clientes de Outlook|Experiencia en línea nativa para destinatarios de Office 365. El resto de los destinatarios pueden leer el mensaje del portal de OME (no se requiere descarga ni aplicación).|
|*Experiencia para destinatario externo*|Los destinatarios reciben un mensaje HTML que descargan y abren en un explorador Web o en una aplicación móvil|N/D|Experiencia en línea nativa para destinatarios de Office 365. El resto de los destinatarios pueden leer el mensaje del portal de OME (no se requiere descarga ni aplicación).|
|*Permisos de datos adJuntos*           |No hay restricciones en los datos adjuntos|Los datos adJuntos están protegidos|Los datos adJuntos están protegidos para la opción no reEnviar y las plantillas personalizadas. Los administradores pueden elegir si los datos adjuntos de la opción de solo codificación están protegidos o no.|
|*Proporcionar compatibilidad con claves propias (BYOK)*|Ninguno                |Ninguno               |BYOK compatible          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>Ventajas de las nuevas capacidades de OME sobre el legado de OME

Las nuevas capacidades proporcionan las siguientes ventajas:

- Capacidad para usar el cifrado (lo que permite la colaboración segura), no reEnviar y personalizar restricciones.
- Los remitentes pueden enviar correo cifrado con las nuevas funciones de forma manual desde los clientes de escritorio de Outlook, Outlook para Mac y Outlook en la Web.
- Office 365 destinatarios usan una experiencia en línea en clientes de Outlook compatibles. Como alternativa, los administradores pueden elegir mostrar a los destinatarios de Office 365 una experiencia de personalización de marca.
- Las cuentas fuera de Office 365, como las cuentas de gmail, Yahoo y Microsoft, están federadas con el portal OME, que proporciona una mejor experiencia de usuario para estos destinatarios. El resto de las identidades usan un código de paso único para acceder a los mensajes cifrados.
- Los administradores pueden personalizar la personalización de marca y crear varias plantillas de personalización de marca.
- Los administradores pueden revocar mensajes de correo electrónico cifrados con las nuevas funciones.
- Las nuevas funciones proporcionan informes de uso detallados &amp; a través del centro de seguridad y cumplimiento.

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>Características únicas del cifrado de mensajes de Office 365 en una implementación alta de GCC

Si planea usar el cifrado de mensajes de Office 365 en un entorno de GCC High, hay algunas características únicas sobre la experiencia de los destinatarios.

### <a name="encrypted-email-from-gcc-high-to-gcc-high-recipients"></a>Correo electrónico cifrado de GCC High a GCC destinatarios altos

Los remitentes pueden cifrar mensajes de correo electrónico manualmente en Outlook para PC y Mac y Outlook en la web, o las organizaciones pueden configurar una directiva para cifrar correos electrónicos con las reglas de flujo de correo de Exchange.

Los destinatarios dentro de GCC reciben alta experiencia de lectura en línea en Outlook para PC y Mac y Outlook en la web como todos los demás usuarios de Office 365.

### <a name="encrypted-email-from-gcc-high-to-non-gcc-high-recipients"></a>Mensajes de correo electrónico cifrados de GCC High a non-GCC High Recipients

Los remitentes de GCC High pueden enviar correo electrónico cifrado fuera del límite superior de GCC.

Todos los destinatarios que superen GCC High, incluidos los usuarios comerciales de Office 365, los usuarios de Outlook.com y otros usuarios de otros proveedores de correo electrónico, como gmail y Yahoo, reciben un correo de contenedor que redirige al destinatario al portal de OME donde el destinatario puede leer y responder al mensaje.

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>Coexistencia de OME heredados y las nuevas funcionalidades en el mismo espacio empresarial

Puede usar OME y las funciones nuevas en el mismo inquilino. Como administrador, para ello, debe elegir la versión de OME que desea usar para crear las reglas de flujo de correo.

- Para especificar la versión heredada de OME, use la acción de regla de flujo de correo de Exchange **aplique la versión anterior de OME**.
- Para especificar las nuevas funciones, use la acción de regla de flujo de correo de Exchange **aplicar el cifrado de mensajes de Office 365 y la protección de derechos**.

Los usuarios pueden enviar manualmente correo cifrado con las nuevas funciones desde el escritorio de Outlook, Outlook para Mac y Outlook en la Web.

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>Migrar de OME heredado a las nuevas capacidades

Aunque ambas versiones de OME pueden coexistir, se recomienda encarecidamente editar las reglas de flujo de correo antiguas que usen la acción de regla **aplique la versión anterior de OME** para usar las nuevas funciones. Actualizar estas reglas para usar la acción de regla de flujo de correo aplique el cifrado de **mensajes de Office 365 y la protección de derechos**. Para obtener instrucciones, vea [definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md).

## <a name="get-started-with-ome"></a>Introducción a OME

Normalmente, las nuevas funciones de OME se habilitan automáticamente para su organización de Office 365. Para obtener más información acerca de las nuevas funciones de OME dentro de su organización, vea [set up New Office 365 Message Encryption Capabilities](set-up-new-message-encryption-capabilities.md).

La versión heredada de OME se habilita automáticamente para su organización de Office 365 si ha habilitado Azure Information Protection. En el pasado, los OME heredados funcionaban incluso si Azure Information Protection no estaba habilitado. Ya no es así.

Para empezar a usar OME heredados, si ha habilitado Azure Information Protection, simplemente configure las reglas de flujo de correo que usen la acción de regla, **aplique la versión anterior de OME**. Para obtener instrucciones, vea [definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md).
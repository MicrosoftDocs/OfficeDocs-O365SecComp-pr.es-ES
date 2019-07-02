---
title: Crear listas de remitentes bloqueados en Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/6/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: Las opciones de la lista bloquear remitente incluyen los remitentes bloqueados de Outlook, los remitentes de correo no deseado y las listas de bloqueo de dominio, las listas de direcciones IP bloqueadas y las reglas de transporte de Exchange (ETR) también denominadas reglas de flujo de correo.
ms.openlocfilehash: 9933cb79b7dce949384815a7b2ed8a9ac8a7824b
ms.sourcegitcommit: f96029928a6cdd141783026d57bc2179d7963af6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2019
ms.locfileid: "35017692"
---
# <a name="create-block-sender-lists-in-office-365"></a>Crear listas de remitentes bloqueados en Office 365

A veces es necesario bloquear el correo no deseado de los remitentes. Hay varios métodos disponibles para elegir. Estas opciones incluyen los remitentes bloqueados de Outlook, los remitentes de correo no deseado y las listas de bloqueados de dominios, las listas de direcciones IP bloqueadas y las reglas de transporte de Exchange (ETR, que también se conocen como reglas de flujo de correo).

> [!NOTE]
> Mientras que las listas de bloqueo de organización se pueden usar para solucionar falsos negativos (correo no deseado), estos candidatos también deben enviarse a Microsoft para su análisis. Administrar los falsos negativos mediante listas de bloqueo aumenta considerablemente la sobrecarga administrativa. Si va a usar una lista de bloqueados para este propósito, también tendrá que mantener el artículo para [enviar mensajes de correo no deseado, correo no deseado y estafas de suplantación de identidad a Microsoft para su análisis](https://docs.microsoft.com/en-us/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis), en la lista desplegable.

El método adecuado para configurar listas de remitentes bloqueados varía en función del ámbito del impacto. Para un solo impacto en el usuario, la solución correcta puede ser usar remitentes bloqueados de Outlook, pero si se ven afectados varios usuarios o todos los usuarios, una de las otras opciones sería más adecuada.

## <a name="options-from-least-to-broadest-scope"></a>Opciones de menor a mayor ámbito

Al crear una lista de bloqueados, es importante elegir el método adecuado en función del alcance del impacto (cuántas personas se verán afectadas), de modo que coincida con la amplitud del método de bloqueo. Las opciones que se enumeran a continuación están ordenadas por ámbito y amplitud. La lista va de estrecho a amplio, pero *Lea los detalles específicos* para obtener recomendaciones completas.

- Remitentes bloqueados de Outlook
- Directiva contra correo no deseado: listas de bloqueo de remitente/dominio
- Reglas de transporte de Exchange (ETR también denominadas reglas de flujo de correo)
- Directiva contra correo no deseado: listas de direcciones IP bloqueadas

## <a name="use-outlook-blocked-senders"></a>Usar los remitentes bloqueados de Outlook

Cuando solo se ven afectados un pequeño número de usuarios, es necesario usar los remitentes bloqueados de Outlook, ya que esto sólo afectará al correo que se les envíe.

> [!IMPORTANT]
> Si los mensajes no deseados son boletines de un origen fiable y reconocible, la cancelación del correo electrónico es otra opción para impedir que el usuario obtenga los correos electrónicos en el futuro.

Los pasos para configurar esto son diferentes entre [Outlook Web App](https://support.office.com/en-us/article/block-or-allow-junk-email-settings-48c9f6f7-2309-4f95-9a4d-de987e880e46) y el [cliente de Outlook](https://support.office.com/en-us/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). **Cuando los mensajes se bloquean correctamente debido a los remitentes bloqueados, verá SFV: BLK en el X-Forefront-antispam-Report** , que indica que el mensaje se está bloqueando.

## <a name="use-anti-spam-policy-senderdomain-block-lists"></a>Usar la Directiva contra correo no deseado listas de bloqueo de remitente/dominio

Cuando se ven afectados varios usuarios, el ámbito es más amplio y es necesario usar una directiva de bloqueo de correo no deseado de lista de remitentes/dominios en toda la empresa. Puede encontrar los pasos detallados en [configurar las directivas de filtro de correo no deseado](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-your-spam-filter-policies) . Cualquier mensaje bloqueado mediante este método seguirá la acción de correo no deseado, tal como se ha configurado en la Directiva.

## <a name="use-exchange-transport-rules-etrs-to-block-specific-senders"></a>Usar reglas de transporte de Exchange (ETR) para bloquear remitentes específicos

Si es necesario bloquear los mensajes que se envían a usuarios específicos o en toda la organización, se puede usar ETR (también denominadas reglas de flujo de correo). ETR son más flexibles porque pueden desencadenar la dirección de correo electrónico o el dominio del remitente, así como palabras clave y otras propiedades del mensaje. Esta flexibilidad le permitirá crear bloques parciales para completar. [Haga clic en para conocer los pasos para crear una ETR, también conocida como reglas de flujo de correo](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages).

> [!IMPORTANT]
> Es fácil crear reglas excesivamente agresivas ** , por lo tanto, es importante que los criterios que se usen sean tan específicos como sea posible. Además, asegúrese de habilitar la auditoría de la regla que cree y realice pruebas para asegurarse de que todo funciona según lo esperado.

## <a name="use-anti-spam-policy-ip-block-lists"></a>Usar listas de direcciones IP bloqueadas de la Directiva contra correo no deseado

Cuando no es posible usar una de las otras opciones para bloquear a un remitente, se puede ** usar la lista de direcciones IP bloqueadas de la Directiva contra correo no deseado. [Puede encontrar los pasos detallados en el artículo Configure the Connection Filter Policy](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-the-connection-filter-policy). Es importante mantener la lista de IP bloqueadas en un *mínimo* y usar intervalos de direcciones IP aquí *no* se recomienda.

En *especial* , debe evitar agregar intervalos de direcciones IP que pertenezcan a servicios de consumidores o infraestructuras compartidas, y también asegurarse de que revisa la lista de direcciones IP permitidas como parte del mantenimiento regular. **Como permitir-entradas puede abrir rutas para un ataque, debe administrar atentamente esta lista y quitar con regularidad las entradas que permiten que ya no sean necesarias.** Además, si va a realizar la habilitación en una lista de remitentes seguros, asegúrese de leer y comprender los riesgos y las precauciones en *[crear listas de remitentes seguros en Office 365](create-safe-sender-lists-in-office-365.md)*.
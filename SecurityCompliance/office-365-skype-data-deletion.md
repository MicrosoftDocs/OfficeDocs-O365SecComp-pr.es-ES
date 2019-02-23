---
title: Eliminación de datos de Skype empresarial para Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Explicación de la eliminación de datos en Skype empresarial.
ms.openlocfilehash: 77ead8b8c2251ce21f9a0c0db9e29d5d48829760
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30221150"
---
# <a name="skype-for-business-data-deletion-in-office-365"></a>Eliminación de datos de Skype empresarial en Office 365

Skype Empresarial proporciona archivado de mensajes instantáneos de punto a punto, mensajes instantáneos entre varios participantes y actividades de carga de contenido en reuniones. La capacidad de archivado requiere Exchange y se controla mediante el atributo Conservación local del buzón de correo de Exchange del usuario, que archiva el contenido de Skype Empresarial y de correo electrónico.

Todo el archivado de Skype Empresarial se considera "archivado de nivel de usuario" porque consiste en habilitar o deshabilitar el archivado para uno o más usuarios o grupos de usuarios específicos mediante la creación, configuración y aplicación de una directiva de archivado a nivel de usuario para esos usuarios. No existe control directo de la configuración de archivado desde el Centro de administración de Skype Empresarial.

Los siguientes tipos de contenido no se archivan en Skype empresarial: 
- Transferencias de archivos de punto a punto
- Audio/vídeo para conferencias y mensajes instantáneos de punto a punto
- Uso compartido de aplicaciones para conferencias y mensajes instantáneos de punto a punto
- Anotaciones de conferencias 

## <a name="meeting-content-retention"></a>Conservación del contenido de la reunión
Los clientes que usan Skype empresarial pueden cargar contenido en una reunión de Skype empresarial como datos adjuntos, como presentaciones de PowerPoint, archivos de OneNote y otros archivos. El período de retención para el contenido que se ha cargado en una reunión es el siguiente:
- **Reunión única** : el contenido se conserva durante 15 días a partir del momento en que la última persona abandona la reunión.
- **Reunión recurrente** : el contenido se conserva durante 15 días después de que la última persona abandone la última sesión de la reunión. El temporizador de retención se reinicia si alguien se une a la misma sesión de reunión en 15 días. Por ejemplo, supongamos que una reunión de Skype empresarial está programada para realizarse semanalmente durante un año y se carga un archivo en la reunión durante la primera instancia. Si al menos una persona se une a la sesión de reunión cada semana, el archivo se conserva en los servidores de Skype empresarial online durante todo el año más 15 días después de que la última persona abandone la última reunión de la serie.
- **Reunirse ahora** : el contenido se conserva durante 8 horas después de la hora de finalización de la reunión.

> [!NOTE]
> Si un usuario está deshabilitado o sin licencia (por ejemplo, si **msRTCSIP-userEnabled** está establecido en *false*) y, a continuación, vuelve a estar habilitado o con licencia, no se conservará el contenido de la reunión.

## <a name="meeting-expiration"></a>Expiración de la reunión
Los usuarios pueden acceder a una reunión específica después de que haya finalizado, respetando los siguientes períodos de expiración:
- **Reunión única** : la reunión expira 14 días después de la hora de finalización programada de la reunión.
- **Reunión periódica con fecha** de finalización: la reunión expira 14 días después de la hora de finalización programada de la última ocurrencia de la reunión.
- **Reunirse ahora** : reunión expira después de 8 horas.

## <a name="whiteboard-collaboration"></a>Colaboración en pizarra
Todos los participantes verán las anotaciones realizadas en las pizarras. Al guardar una pizarra, la pizarra y todas las anotaciones se almacenarán en un servidor de Skype empresarial, y se conservará en el servidor de acuerdo con las directivas de expiración del contenido de la reunión establecidas por el administrador.

## <a name="audio-test-service"></a>Servicio de prueba de audio
Una muestra breve (aproximadamente 5 segundos) de la voz se graba durante la llamada de servicio de prueba de audio. La muestra de voz se usa para comprobar o comprobar la calidad de sonido de la llamada de Skype empresarial en función de la calidad de la grabación. Cuando finaliza la llamada del servicio de prueba de audio, se elimina la muestra de voz.

## <a name="persistent-group-chat"></a>Chat de grupo persistente
El chat de grupo persistente almacena el contenido de las conversaciones de chat en grupo. Si se habilita, el administrador puede controlar el período de retención, el servidor en el que se almacena esta información, si el historial de chat de grupo se archiva para cumplimiento o para otros fines, y administrar o modificar las propiedades de un salón. Los usuarios con diferentes roles tienen un acceso diferente a los datos persistentes, de la siguiente manera:
- Los administradores pueden eliminar contenido antiguo (por ejemplo, contenido publicado antes de una fecha determinada) de cualquier salón de chat para evitar que el tamaño de la base de datos crezca en gran medida. O bien pueden quitar o reemplazar los mensajes considerados inapropiados para un salón de chat determinado (o considerados inadecuados).
- Los usuarios finales, incluidos los autores de mensajes, no pueden eliminar contenido de ningún salón de chat.
- Los administradores de salones de chat pueden deshabilitar las salas pero no eliminar las salas. Solo los administradores pueden eliminar un salón de chat una vez creado.
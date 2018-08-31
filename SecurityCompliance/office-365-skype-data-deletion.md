---
title: Office 365 Skype para su eliminación de datos de negocio
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Una explicación de eliminación de datos en Skype para la empresa.
ms.openlocfilehash: f3ddd0ad0797c465857919e8f7b28341492769ba
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536449"
---
# <a name="skype-for-business-data-deletion-in-office-365"></a>Skype para su eliminación de datos de negocio en Office 365

Skype Empresarial proporciona archivado de mensajes instantáneos de punto a punto, mensajes instantáneos entre varios participantes y actividades de carga de contenido en reuniones. La capacidad de archivado requiere Exchange y se controla mediante el atributo Conservación local del buzón de correo de Exchange del usuario, que archiva el contenido de Skype Empresarial y de correo electrónico.

Todo el archivado de Skype Empresarial se considera "archivado de nivel de usuario" porque consiste en habilitar o deshabilitar el archivado para uno o más usuarios o grupos de usuarios específicos mediante la creación, configuración y aplicación de una directiva de archivado a nivel de usuario para esos usuarios. No existe control directo de la configuración de archivado desde el Centro de administración de Skype Empresarial.

Los siguientes tipos de contenido no se archivan en Skype para la empresa: 
- Transferencias de archivos de punto a punto
- Audio/vídeo para conferencias y mensajes instantáneos de punto a punto
- Uso compartido de aplicaciones para conferencias y mensajes instantáneos de punto a punto
- Anotaciones de conferencias 

## <a name="meeting-content-retention"></a>Conservación del contenido de la reunión
Los clientes que usen Skype para la empresa pueden cargar contenido en un Skype para la reunión de negocios como datos adjuntos, como las presentaciones de PowerPoint, archivos de OneNote y otros archivos. El período de retención para el contenido que se han cargado en una reunión es como sigue:
- **Reunión única** - contenido se conserva durante 15 días a partir de cuando la última persona abandona la reunión.
- **Reunión periódica** - contenido se conserva durante 15 días después de la última persona abandona la última sesión de la reunión. Se restablece el temporizador de retención si alguien se une a la misma sesión de reunión dentro de 15 días. Por ejemplo, supongamos que un Skype para la reunión de negocios está programado que se produzca semanalmente para un año, y se carga un archivo a la reunión durante la primera instancia. Si al menos una persona se une a la sesión de reunión todas las semanas, el archivo se mantiene en Skype para los servidores en línea de negocio para el año completo además de 15 días después de la última persona abandona la última reunión de la serie.
- Contenido de la **reunión Reunirse ahora** - se conserva durante 8 horas después de hora de finalización de la reunión.

> [!NOTE]
> Si un usuario no tiene licencia o deshabilitado (por ejemplo, si **msRTCSIP-userenabled** está establecida en *False*) y, a continuación, se vuelve a con licencia o vuelva a habilitar, no se conserva el contenido de la reunión.

## <a name="meeting-expiration"></a>Expiración de la reunión
Los usuarios pueden acceder a una reunión específica después de que haya finalizado, respetando los siguientes períodos de expiración:
- **Reunión única** - reunión expira 14 días después de hora de finalización de la reunión programada.
- **Reunión periódica con fecha de finalización** - reunión expira 14 días después de la hora de finalización programada de la última aparición de reunión.
- **La reunión Reunirse ahora** - reunión expira después de 8 horas.

## <a name="whiteboard-collaboration"></a>Colaboración de Pizarra
Todos los participantes verán las anotaciones realizadas en pizarras. Al guardar una pizarra, la Pizarra y todas las anotaciones se almacenará en una Skype para Business server y que se conserva en el servidor de acuerdo con las directivas de caducidad del contenido de reunión establecido por el administrador.

## <a name="audio-test-service"></a>Servicio de prueba de audio
Se registra un ejemplo short (aproximadamente 5 segundos) de la voz durante la llamada al servicio de prueba de Audio. En el ejemplo de voz se usa por el usuario para comprobar o comprobar la calidad de sonido de su Skype para llamada de negocio en función de la calidad de la grabación. Cuando finaliza la llamada de servicio de prueba de Audio, se elimina la muestra de voz.

## <a name="persistent-group-chat"></a>Conversaciones en grupo persistentes
Conversaciones en grupo persistentes almacena el contenido de las conversaciones de chat de grupo. Si se habilita, el administrador puede controlar el período de retención, el servidor en el que se almacena esta información, si se archiva el historial de conversaciones en grupo para cumplimiento u otros fines y administrar o modificar las propiedades en un salón. Los usuarios con distintos roles tienen diferente acceso a los datos persistentes, como se indica a continuación:
- Los administradores pueden eliminar contenido antiguo (por ejemplo, el contenido expuesto antes de una fecha determinada) desde cualquier salón de chat para mantener el tamaño de la base de datos crezca en gran medida de. O bien, puede quitar o reemplazar los mensajes considera inapropiada para un salón de chat determinado (o considera apropiadas).
- Los usuarios finales, incluidos a los autores de mensajes, no pueden eliminar el contenido de ningún salón de chat.
- Administradores de salones de chat pueden deshabilitar salones pero no pueden eliminar salas. Sólo los administradores pueden eliminar un salón de chat después de crearla.
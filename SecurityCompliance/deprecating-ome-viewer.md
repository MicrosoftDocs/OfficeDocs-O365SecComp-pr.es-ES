---
title: Aplicación del Visor de dejar obsoletos Office 365 mensaje cifrado
ms.author: krowley
author: kccross
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
description: En 15 de agosto de 2018, vamos a eliminar la aplicación móvil de Office 365 Message Encryption (OME) Visor de almacenes de Android y Apple. La aplicación móvil de Visor de cifrado de mensajes de Office 365 se requería para leer mensajes de correo electrónico y datos adjuntos que se han cifrado con la versión anterior de OME en Apple y teléfonos Android. Aparte de eliminación de la aplicación de Visor de OME, no se estamos efectuar otros cambios en la versión anterior de OME.
ms.openlocfilehash: 43e514bd8336d283aaf774ffa4f49565f86e7102
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535598"
---
# <a name="deprecating-office-365-message-encryption-viewer-app"></a>Aplicación del Visor de dejar obsoletos Office 365 mensaje cifrado

En 15 de agosto de 2018, vamos a eliminar la aplicación móvil de Office 365 Message Encryption (OME) Visor de almacenes de Android y Apple. La aplicación móvil de Visor de cifrado de mensajes de Office 365 se requería para leer mensajes de correo electrónico y datos adjuntos que se han cifrado con la versión anterior de OME en Apple y teléfonos Android. Aparte de eliminación de la aplicación de Visor de OME, no se estamos efectuar otros cambios en la versión anterior de OME.
  
## <a name="changes-beginning-august-2018"></a>Cambios a partir de agosto de 2018

Como anunciado última septiembre, hemos publicado una nueva versión de [Office 365 Message Encryption](https://aka.ms/ome2017) para que los usuarios pueden enviar cifrada y protegida mensajes a todas las personas dentro o fuera de la organización sin el requisito de la aplicación móvil. Desde entonces, hemos agregado capacidades adicionales: 
  
- [Plantilla de sólo cifrar](https://aka.ms/encryptonly)
    
- [Control para descifrar los datos adjuntos](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)
    
Con este cambio, los usuarios ya no podrán descargar la aplicación móvil de Visor de cifrado de mensajes de Office 365 empieza el 1 de agosto. Como resultado, es podrán que los destinatarios de correo no pueda leer los mensajes cifrados con la versión anterior de OME en algunos dispositivos móviles Android y Apple. Sin embargo, aún podrá leer estos mensajes en los equipos personales (a través de los exploradores de escritorio). Los usuarios que ya se han descargado la aplicación continuará poder usarla.
  
## <a name="why-this-change-was-made"></a>¿Por qué este cambio se realizó

La nueva versión de OME ya no requiere una aplicación móvil para leer mensajes de correo electrónico protegido y los datos adjuntos. Los clientes de Office 365 con el nuevo OME capacidades pueden ver el mensaje protegido en Outlook mobile y los clientes que no sean Office 365 pueden ver mensajes protegidos en un explorador.
  
Requerir que los usuarios descargar una aplicación móvil es otro obstáculo para los clientes ver los mensajes protegidos. Las nuevas capacidades de Office 365 Message Encryption proporcionan una mejor experiencia móvil.
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>¿Puedo seguir utilizando la versión anterior del cifrado de mensajes de Office 365

La versión anterior de Office 365 Message Encryption no quedará obsoleto en este momento, sin embargo, hemos tomado mejoras significativas a la nueva versión de cifrado de mensajes de Office 365, que hacen que sea más fácil cifrar y proteger los datos confidenciales a todas las personas de derechos y en cualquier dispositivo -, incluida la capacidad de los usuarios de Office 365 leer los mensajes protegidos directamente en Outlook (escritorio, mobile y web). 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>¿Qué es necesario que hacer para preparar para que este cambio

Si la organización envía actualmente cifrados los datos adjuntos a los destinatarios que requieren la aplicación de Visor de OME, debe actualizar su documentación y recursos de aprendizaje.
  
Se recomienda actualizar las reglas de flujo de correo de Exchange existentes para usar la versión actual de OME para que su organización puede sacar provecho de las funciones nuevas y mejoradas. Una vez haya configurado las nuevas capacidades OME, los destinatarios no necesitan la aplicación de Visor de OME para leer los mensajes cifrados en dispositivos móviles.
  
Microsoft recomienda que realice un plan para mover a las nuevas capacidades OME tan pronto como es razonable para la organización. Para obtener instrucciones, vea [Configurar nuevas capacidades de cifrado de mensajes de Office 365](set-up-new-message-encryption-capabilities.md). Si desea obtener más información acerca de cómo funcionan en primer lugar las nuevas capacidades, consulte [Cifrado de mensajes de Office 365](ome.md).
  


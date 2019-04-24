---
title: Aislamiento de inquilino de Office 365 en vídeo de Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 'Resumen: explicación del aislamiento de inquilinos en Office 365 video.'
ms.openlocfilehash: 071a71266191748db8f6cb27ae86e1f65dcb4d1d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262592"
---
# <a name="tenant-isolation-in-office-365-video"></a>Aislamiento del inquilino en Office 365 Video

> [!NOTE]
> El vídeo de Office 365 se reemplazará por Microsoft Stream. Para obtener más información sobre el nuevo servicio de vídeo empresarial que aporta inteligencia a la colaboración de vídeos y sobre los planes de transición para los clientes actuales de vídeo de Office 365, vea [Migrate to stream from office 365 video](https://docs.microsoft.com/stream/).

## <a name="introduction"></a>Introducción
Azure Storage se usa para almacenar datos para varios servicios de Office 365, incluidos Office 365 video y Sway. Azure Storage incluye almacenamiento de blobs, que es un almacén de objetos de nube altamente escalable y basado en REST que se usa para almacenar datos sin estructurar. Azure Storage usa un modelo de control de acceso sencillo; cada suscripción de Azure puede crear una o varias cuentas de almacenamiento. Cada cuenta de almacenamiento tiene una clave secreta única que se usa para controlar el acceso a todos los datos de esa cuenta de almacenamiento. Esto es compatible con el escenario típico en el que el almacenamiento está asociado a las aplicaciones y estas aplicaciones tienen control total sobre sus datos asociados; por ejemplo, Sway almacenando contenido en Azure Storage. Todo el contenido de los clientes de Sway se almacena en cuentas de almacenamiento de Azure compartidas. El contenido de cada usuario está en un árbol de directorios independiente de blobs en Azure Storage.

Los sistemas que administran el acceso a los entornos del cliente (por ejemplo, el portal de Azure, SMAPI, etc.) están aislados dentro de una aplicación de Azure operada por Microsoft. De esta forma, se separa lógicamente la infraestructura de acceso al cliente de la capa de aplicaciones y almacenamiento del cliente.

## <a name="tenant-isolation-in-office-365-video"></a>Aislamiento del inquilino en Office 365 Video
[Office 365 video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) es un portal empresarial que ofrece a las organizaciones un destino de gran seguridad y de toda la organización para publicar, compartir y detectar contenido de vídeo. En Office 365 vídeo, los vídeos de cada inquilino se mantienen aislados y cifrados en todas las ubicaciones, y solo están disponibles para los usuarios autenticados que tienen acceso y permisos para los vídeos de la organización. Office 365 video usa una combinación de tecnologías para hacerlo:
- SharePoint Online se usa para almacenar el archivo de vídeo y los metadatos (título de vídeo, descripción, etc.). También proporciona la capa de seguridad y cumplimiento (incluida la autenticación) y las características de búsqueda.
- Servicios multimedia de Azure proporciona transcodificación, transmisión por secuencias adaptable, entrega segura (mediante cifrado AES) y características de miniaturas.

[Azure Media Services](https://azure.microsoft.com/services/media-services/) es una oferta de plataforma como servicio para habilitar flujos de trabajo de medios de un extremo a otro en la nube. La plataforma proporciona una API de REST para cargar, codificar, cifrar (con PlayReady) y entregar medios a través de centros de contenido de Azure en todo el mundo.

Todas las cargas para Office 365 video se producen a través de HTTPS. Cuando se carga un archivo de vídeo, se almacena en SharePoint Online y se envía una copia del archivo a través de un canal cifrado a Azure Media Services. Azure Media Services transcodifica el vídeo en varios formatos optimizados para la experiencia de visualización (por ejemplo, móvil, bajo ancho de banda, alto ancho de banda, etc.). Estos archivos, junto con el archivo original adquirido durante la carga, se almacenan en Azure BLOB Storage. Los archivos se cifran mediante AES 128 según el algoritmo de empaquetado de cifrado MPEG Common (o una versión anterior de PlayReady) para la reproducción y cifrados con el cifrado de almacenamiento AES 256 antes de almacenarlos en el almacenamiento de blobs de Azure. (Con el SDK del cliente de Azure Media Services, los clientes pueden controlar qué cifrado se usa. Por ejemplo, un cliente podría aplicar el cifrado de almacenamiento de Azure Media Services (AES 256) a un activo de medios de valor alto antes de cargar el almacenamiento de blobs de Azure.

Servicios multimedia de Azure también genera una miniatura para el vídeo, que transmite junto con los metadatos de miniaturas a SharePoint Online a través de un canal cifrado.

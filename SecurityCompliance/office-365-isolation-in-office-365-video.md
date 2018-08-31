---
title: Aislamiento de inquilinos de Office 365 en vídeo de Office 365
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
description: 'Resumen: Una explicación de aislamiento de inquilinos en vídeo de Office 365.'
ms.openlocfilehash: 9476047d56161ec2589fdf743d7ee837ea558865
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536460"
---
# <a name="tenant-isolation-in-office-365-video"></a>Aislamiento del inquilino en Office 365 Video

> [!NOTE]
> Vídeo de Office 365 se reemplazará por Microsoft Stream. Para obtener más información sobre el nuevo servicio de vídeo de empresa que agrega inteligencia para colaboración de vídeo y obtenga información acerca de los planes de transición para los clientes actuales de vídeo de Office 365, vea [Migrate a la secuencia de vídeo de Office 365](https://docs.microsoft.com/stream/).

## <a name="introduction"></a>Introducción
Almacenamiento de Azure se usa para almacenar datos de varios servicios de Office 365, incluido el vídeo de Office 365 y balanceo. Almacenamiento de Azure incluye almacenamiento de blobs, que es un almacén de objetos en la nube altamente escalable, basado en REST, que se usa para almacenar datos no estructurados. Almacenamiento de Azure usa un modelo de control de acceso sencillo; cada suscripción de Azure puede crear una o más cuentas de almacenamiento. Cada cuenta de almacenamiento tiene una única clave secreta que se utiliza para controlar el acceso a todos los datos en esa cuenta de almacenamiento. Esto es compatible con el escenario típico donde almacenamiento está asociado con aplicaciones y esas aplicaciones tienen control total sobre sus datos asociados; Por ejemplo, influir hora de elegir almacenar contenido en almacenamiento de Azure. Todo el contenido del cliente para balanceo se almacena en las cuentas de almacenamiento compartido de Azure. Contenido de cada usuario está en un árbol de directorio independiente de blobs en almacenamiento de Azure.

Los sistemas de administración del acceso a entornos de clientes (por ejemplo, el Portal de Azure, SMAPI, etc.) se aíslan dentro de una aplicación de Azure operada por Microsoft. Esto lógicamente separa la infraestructura de acceso de cliente desde las aplicaciones de cliente y la capa de almacenamiento.

## <a name="tenant-isolation-in-office-365-video"></a>Aislamiento del inquilino en Office 365 Video
[Vídeo de Office 365](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) es un portal empresarial que proporciona a las organizaciones con un destino de alta seguridad, toda la organización para el registro, uso compartido y detección de contenido de vídeo. En vídeo de Office 365, vídeos de cada inquilino se mantienen aislado y cifrados en todas las ubicaciones y están disponibles solo a los usuarios autenticados que tienen acceso y los permisos a los vídeos de la organización. Vídeo de Office 365 usa una combinación de tecnologías para hacerlo:
- SharePoint Online se usa para almacenar el archivo de vídeo y los metadatos (título de vídeo, descripción, etcetera). También proporciona la capa de seguridad y cumplimiento de normas (incluida la autenticación) y las características de búsqueda.
- Servicios de medios Azure proporciona transcodificación, adaptable de transmisión por secuencias, entrega segura (mediante cifrado AES) y características en miniatura.

[Servicios de Azure Media](https://azure.microsoft.com/services/media-services/) es una plataforma-as-a-service que ofrece para habilitar flujos de trabajo de medios end-to-end en la nube. La plataforma proporciona una API de REST para cargar, codificación, el cifrado (con PlayReady) y la entrega de medios a través de centros de datos Azure todo el mundo.

Todas las cargas de vídeo de Office 365 se producen a través de HTTPS. Cuando se carga un archivo de vídeo, se encuentra almacenada en SharePoint Online, y se envía una copia del archivo a través de un canal cifrado a los servicios de medios de Azure. Azure Media Services transcodifica el vídeo en varios formatos que están optimizados para la visualización de la experiencia (por ejemplo, móvil, ancho de banda bajo, ancho de banda alto, etcetera). Estos archivos, junto con el archivo original adquirido durante la carga, se almacenan en el almacenamiento de blobs de Azure. Los archivos se cifran mediante AES 128 por el algoritmo de empaquetado de cifrado comunes de MPEG (o una versión anterior de PlayReady) para la reproducción y cifran mediante el cifrado de almacenamiento de AES 256 antes de que se almacenan en almacenamiento de blobs de Azure. (Con el SDK de cliente de servicios de medios de Azure, los clientes pueden controlar qué cifrado se usa. Por ejemplo, un cliente podría aplicar cifrado de almacenamiento de los servicios de Azure Media (AES 256) a un activo de medios de gran valor antes de cargarlas almacenamiento de blobs de Azure.)

Servicios de medios Azure también genera una vista en miniatura del vídeo, que transmite junto con los metadatos en miniatura a SharePoint Online a través de un canal cifrado.

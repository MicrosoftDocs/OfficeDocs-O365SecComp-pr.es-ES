---
title: Office 365 destrucción de datos
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
description: Información general sobre las directivas de Microsoft sobre reciclado, eliminación o destrucción de los servidores y las unidades de disco del centro de datos de Office 365.
ms.openlocfilehash: d94a4ff5f240bfbfcd690e6247869f0edc88059f
ms.sourcegitcommit: aa60a6cdf83c67576e858668d1182cd4fffeb5e0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "33622250"
---
# <a name="office-365-data-destruction"></a>Office 365 destrucción de datos

## <a name="physical-data-destruction"></a>Destrucción de datos físicos

Microsoft tiene datos que controlan las directivas estándar que abordan el reciclaje y la eliminación de las unidades de disco y los servidores con o sin errores. Antes de reutilizar cualquiera de las unidades de disco de Office 365, Microsoft realiza un proceso de limpieza física coherente con las directrices de la publicación especial National Institute of Standards and Technology 800-88 ([NIST SP 800-88 para la limpieza de medios](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf)). Como todas las unidades de disco en Office 365 se cifran con cifrado de nivel de volumen de BitLocker, el borrado compatible con el SP 800-88 no es técnicamente necesario. Sin embargo, Microsoft realiza este proceso.

Los discos con errores que se usan en los centros de TI de Office 365 se destruyen y auditan físicamente a través del proceso ISO. Tipo de activo determina los medios adecuados de eliminación. En el caso de las unidades de disco duro que no se pueden eliminar, Microsoft usa un proceso de destrucción para destruir los medios y representar la recuperación de la información que no se pueda. Por ejemplo, los discos están físicamente destruidos, Pulverized o incinerados. Microsoft conserva todos los registros de la destrucción y realiza un proceso de saneamiento similar en los servidores reutilizados en Office 365. Estas instrucciones abarcan la limpieza electrónica y física.

Cada centro de información usa un proceso de destrucción física en el sitio para eliminar sus discos. Las ubicaciones seguras para medios de almacenamiento designados para la eliminación de discos se encuentran en cada área del centro de información. Cada estación de ubicación segura tiene una vigilancia de monitorado de vídeo. Una vez que una ubicación de cancelación alcanza aproximadamente el 50% de capacidad, el equipo de servicios de sitio se pone en contacto con el equipo de seguridad físico para coordinar la eliminación. El personal de servicios del sitio y una oficina de seguridad quitan la bandeja de eliminación segura y la colocan en un área de almacenamiento seguro designada. Las directivas y los procedimientos que rigen el tratamiento de los dispositivos de cojinete de datos durante la eliminación se prueban rutinariamente, incluidos los procedimientos para garantizar la condición de maquinaria aprobada para la destrucción.

En el proceso de destrucción de datos, los discos se borran de una manera compatible con NIST 800-88 (si es posible) y, a continuación, se colocan en una destrucción industrial y se demolishedn físicamente. Microsoft mantiene la responsabilidad de los activos que salen del centro de recursos con NIST SP 800-88, limpieza y depuración coherentes, destrucción de activos, cifrado, inventario preciso, seguimiento y protección de una cadena de custodia durante el transporte. Este proceso se supervisa a través de televisor de circuito cerrado y se emite un certificado de destrucción al finalizar.

Microsoft usa unidades de eliminación de datos de las [soluciones de protocolo extrema](http://www.enterprisedataerasure.com/) (EPS). El software EPS admite los requisitos de NIST SP 800-88 para la limpieza y depuración/borrado seguro. Antes de limpiar o destruir, Microsoft Asset Manager crea un inventario. Si se usa un proveedor para la destrucción, el proveedor proporciona un certificado de destrucción para cada activo destruido, validado por el administrador de activos.

## <a name="virtual-data-destruction"></a>Destrucción de datos virtuales

Microsoft tiene directivas y procedimientos de administración de datos que abordan una destrucción virtual efectiva de los datos para protegerse contra la posibilidad de que los datos se compartan de forma inadecuada entre los inquilinos de servicio o sea accesible después de la eliminación de hardware en el servicio. No se puede tener acceso a los datos eliminados del servicio en un inquilino para otro espacio empresarial de servicios, incluso si se reasigna el almacenamiento físico subyacente. Esto es un resultado de los efectos compuestos de varias tecnologías de virtualización y fragmentación usadas para escalar entornos virtuales, el comportamiento de eliminación activa de las aplicaciones de cada espacio empresarial de servicios (como [llenado con ceros](https://docs.microsoft.com/office365/securitycompliance/office-365-exchange-online-data-deletion#page-zeroing)de las páginas) y los requisitos procesos de cifrado de contenido de aplicaciones y medios.
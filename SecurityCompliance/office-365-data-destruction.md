---
title: Office 365 destrucción de datos
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Información general sobre las directivas de Microsoft en relación con el reciclado, eliminación o destrucción de los servidores y las unidades de disco de Office 365 Datacenter.
ms.openlocfilehash: d273640dc12370386f08d16fe3f254800ede47b3
ms.sourcegitcommit: 24659bdb09f49d0ffed180a4b80bbb7c45c2d301
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2019
ms.locfileid: "29696327"
---
# <a name="office-365-data-destruction"></a>Office 365 destrucción de datos

## <a name="physical-data-destruction"></a>Destrucción de datos físicos

Microsoft tiene datos que controlan las directivas estándar que abordan el reciclaje y la eliminación de las unidades de disco y los servidores con o sin errores. Antes de volver a usar las unidades de disco de Office 365, Microsoft realiza un proceso de limpieza física que es coherente con las directrices del Instituto Nacional de normas y tecnología de tecnología 800-88 ([NIST SP 800-88 para la limpieza de medios](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf) . ). Todas las unidades de disco de Office 365 se cifran con cifrado a nivel de volumen de BitLocker, por lo que en la práctica, no es necesario el borrado de la compatibilidad con el SP 800-88 de NIST. Sin embargo, Microsoft sigue realizando esta función.

Los discos con errores que se usan en los centros de TI de Office 365 se destruyen y auditan físicamente a través del proceso ISO. El tipo de activo determina los medios adecuados de eliminación. Para las unidades de disco duro que no se pueden eliminar, Microsoft usa un proceso de destrucción que destruye los medios (por ejemplo, diintegra, pulverizes o incinera) y hace que la recuperación de la información no sea posible. Microsoft también conserva todos los registros de la destrucción. Microsoft realiza un proceso de saneamiento similar en los servidores que se van a volver a usar en Office 365. Estas instrucciones abarcan la limpieza electrónica y física.

Las unidades de disco que no se pueden volver a usar se eliminan mediante un proceso de destrucción física que se realiza en el sitio del centro de proceso que contiene los discos que se están destruyendo. Los medios de almacenamiento designados para la eliminación se colocan en ubicaciones seguras situadas en cada área del centro de información. Cada estación de bandeja segura está supervisada por el monitorado de vídeo. Una vez que una ubicación de cancelación alcanza aproximadamente el 50% de capacidad, el equipo de servicios de sitio se pone en contacto con el equipo de seguridad físico para coordinar su eliminación. A continuación, el personal de servicios de sitio quita la ubicación de cancelación de Escort por un funcionario de seguridad hasta que se coloca en un área de almacenamiento seguro para esperar la destrucción de los datos. Las directivas y los procedimientos que rigen el tratamiento de los dispositivos de cojinete de datos durante la eliminación se prueban rutinariamente, incluidos los procedimientos para garantizar la condición de maquinaria aprobada para la destrucción.

En el proceso de destrucción de datos, el disco se borra primero de una manera que cumple con NIST 800-88 (si es posible) y, a continuación, se coloca en un triturador industrial y Demolished de forma física. Microsoft mantiene la responsabilidad de los activos que salen del centro de recursos con NIST SP 800-88, limpieza y depuración coherentes, destrucción de activos, cifrado, inventario preciso, seguimiento y protección de una cadena de custodia durante el transporte. Este proceso se supervisa a través de televisor de circuito cerrado y se emite un certificado de destrucción al finalizar.

Microsoft usa unidades de eliminación de datos de las [soluciones de protocolo extrema](http://www.enterprisedataerasure.com/) (EPS). El software EPS admite los requisitos de NIST SP 800-88 para la limpieza y depuración/borrado seguro. Antes de limpiar o destruir, Microsoft Asset Manager crea un inventario. Si se usa un proveedor para la destrucción, el proveedor proporciona un certificado de destrucción para cada activo destruido, validado por el administrador de activos.

## <a name="virtual-data-destruction"></a>Destrucción de datos virtuales

Microsoft tiene directivas y procedimientos de administración de datos que también abordan la destrucción virtual efectiva de datos para protegerse contra la posibilidad de que los datos se compartan de forma inadecuada entre los inquilinos de servicio o sea accesible después de la eliminación de hardware en el servicio. No se puede tener acceso a los datos que se eliminan del servicio en un inquilino para otro espacio empresarial de servicios, aunque se reasigne parte o todo el mismo almacenamiento físico subyacente. Esto es un resultado de los efectos compuestos de varias tecnologías de virtualización y fragmentación usadas para escalar entornos virtuales, el comportamiento de eliminación activa de las aplicaciones de cada espacio empresarial de servicios (como [llenado con ceros](https://docs.microsoft.com/office365/securitycompliance/office-365-exchange-online-data-deletion#page-zeroing)de las páginas) y los requisitos procesos de cifrado de contenido de aplicaciones y medios.
---
title: Destrucción de datos de Office 365
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
description: Una descripción general de las directivas de Microsoft sobre el reciclado, eliminación o destrucción de unidades de disco de centro de datos de Office 365 y los servidores.
ms.openlocfilehash: c9950be4919520f2f46badaa4a7d4cfce5c55b45
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535938"
---
# <a name="office-365-data-destruction"></a>Destrucción de datos de Office 365
Microsoft tiene directivas estándar de tratamiento de datos que se ocupa de reciclaje y eliminación de unidades de disco y con errores o retirar servidores. Antes de volver a usar las unidades de disco dentro de Office 365, Microsoft lleva a cabo un proceso de limpieza físico que sea coherente con National Institute of Standards y tecnología de la publicación especial 800-88 ([NIST SP 800-88 instrucciones sanitización de medios](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf) ). Todas las unidades de disco en Office 365 se cifran mediante el cifrado de nivel de volumen de BitLocker, por lo que en la práctica, la eliminación de NIST SP 800-88-compatible con no es necesaria. No obstante, aún se realiza por Microsoft.

No se pudo discos que se utilizan dentro de Office 365 centros de datos físicamente se destruye y auditar a través del proceso ISO. Los métodos adecuados de eliminación está determinado por el tipo de activo. Para unidades de disco duro que no se pueden realizar el borrado, Microsoft utiliza un proceso de destrucción que destruye los medios (por ejemplo, disintegrates, pulverizes o incinerates) y representar imposible la recuperación de información. Microsoft también reserva todos los registros de destruir. Microsoft lleva a cabo un proceso similar de limpieza en los servidores que se va a volver a usar dentro de Office 365. Estas instrucciones abarcan limpieza electrónico y físico.

Unidades de disco que no se puede volver a utilizadas se eliminan mediante un proceso de destrucción física que se lleva a cabo en el sitio del centro de datos que contiene los discos que se va a destruir. Medios de almacenamiento designados para su eliminación se colocan en ubicaciones seguras que se encuentra en cada área del centro de datos. Cada estación de bin seguro está supervisado por vigilancia de vídeo. Una vez que una Papelera de eliminación alcanza aproximadamente 50% de capacidad, el equipo de servicios de sitio se pone en contacto con el equipo de seguridad física para coordinar su eliminación. Personal de servicios de sitio, a continuación, quite la Papelera de eliminación con escolta por un agente de seguridad hasta que se coloca en un área de almacenamiento seguro a la espera de destrucción de datos. Directivas y procedimientos que rigen el tratamiento de los dispositivos de soporte durante la eliminación de datos de manera rutinaria se prueban incluidos los procedimientos para garantizar la condición de máquinas aprobadas para la destrucción.

En el proceso de destrucción de datos, en primer lugar se borrará el disco de forma que sea compatible con NIST 800-88 (si es posible) y, a continuación, se coloca en un shredder industrial y físicamente demolida. Microsoft mantiene responsabilidad para salir del centro de datos con NIST SP 800-88 coherente limpieza/depuración, destrucción de activos, cifrado, precisos inventario, seguimiento y protección de la cadena de custodia durante el transporte de activos. Este proceso se supervisa mediante circuito cerrado de televisión y un certificado de destrucción se emite al finalizar.

Microsoft utiliza unidades de eliminación de datos de [Soluciones de protocolo extrema](http://www.enterprisedataerasure.com/) (EPS). Software EPS admite NIST SP 800-88 requisitos para eliminación de limpieza y depuración de seguro. Antes de la limpieza o destrucción, se crea un inventario por el Administrador de activos de Microsoft. Si se usa un proveedor para su destrucción, el proveedor proporciona un certificado de destrucción para cada activo destruida, que se valida mediante el Administrador de activos.
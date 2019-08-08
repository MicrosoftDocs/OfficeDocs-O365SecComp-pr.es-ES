---
title: Introducción a las barreras de información
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Usar barreras de la información para garantizar el cumplimiento de la comunicación mediante Microsoft Teams en su organización.
ms.openlocfilehash: b23e0f4285b2bee08dd19793f8461f39328e85f5
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230404"
---
# <a name="information-barriers"></a>Barreras de la información

## <a name="overview"></a>Información general

Los servicios en la nube de Microsoft incluyen eficaces capacidades de comunicación y colaboración. Pero supongamos que desea restringir las comunicaciones entre dos grupos para evitar que se produzca un conflicto de intereses en la organización. O quizás desee restringir las comunicaciones entre determinadas personas dentro de la organización con el fin de proteger la información interna. Microsoft 365 permite la comunicación y la colaboración entre grupos y organizaciones, así que hay una forma de restringir las comunicaciones entre grupos de usuarios específicos cuando sea necesario. Con las barreras de la información, puede hacerlo. 

Las barreras de la información se están implementando ahora, a partir de Microsoft Teams. Suponiendo que la [suscripción](#required-licenses-and-permissions) incluya barreras informativas, un administrador de cumplimiento o barreras de información puede definir directivas para permitir o impedir las comunicaciones entre grupos de usuarios en Microsoft Teams. Las directivas de barrera de información se pueden usar para situaciones como estas:

- Un comerciante de día no puede llamar a alguien del equipo de marketing
- El personal de finanzas que trabaja con información de la compañía confidencial no puede recibir llamadas de determinados grupos de la organización
- Un equipo interno con material de secreto comercial no puede llamar o chatear en línea con personas de determinados grupos de la organización
- Un equipo de investigación solo puede llamar o chatear en línea con un equipo de desarrollo del producto

Para todos estos escenarios de ejemplo (y más), se pueden definir directivas de barrera de información para impedir o permitir las comunicaciones en Microsoft Teams. Estas directivas pueden impedir que los usuarios llamen o chatean con ellos que no deben, o bien permitir que los usuarios se comuniquen solo con grupos específicos en Microsoft Teams. Con las directivas de barrera de información en vigor, cada vez que los usuarios que están cubiertos por estas directivas intentan comunicarse con otros usuarios de Microsoft Teams, se realizan comprobaciones para evitar (o permitir) la comunicación (según las directivas de la barrera de información definida). Para obtener más información sobre la experiencia del usuario con barreras de información, consulte [barreras de la información en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).

> [!IMPORTANT]
> Actualmente, las barreras de información no se aplican a las comunicaciones de correo electrónico ni al uso compartido de archivos a través de SharePoint Online o OneDrive. Además, las barreras de información son independientes de los [límites de cumplimiento](set-up-compliance-boundaries.md).<p>Antes de definir y aplicar directivas de barrera de información, asegúrese de que la organización no tiene [directivas de libreta de direcciones de Exchange](https://docs.microsoft.com/en-us/exchange/address-books/address-book-policies/address-book-policies) en vigor. (Las barreras de información se basan en las directivas de la libreta de direcciones). 

## <a name="what-happens-with-information-barriers"></a>Qué sucede con las barreras de la información

Cuando se implementan directivas de barrera, las personas que no deben comunicarse con otros usuarios específicos no podrán encontrar, seleccionar, chatear o llamar a dichos usuarios. Con obstáculos en cuanto a la información, hay que realizar comprobaciones para evitar la comunicación no autorizada.

Inicialmente, las barreras de información se aplican únicamente a los canales y chats de Microsoft Teams. En Microsoft Teams, las directivas de barrera de información determinan y evitan los siguientes tipos de comunicaciones no autorizadas:
- Buscar un usuario
- Adición de un miembro a un equipo
- Iniciar una sesión de chat con alguien
- Iniciar un chat en grupo
- Invitar a alguien a unirse a una reunión
- Uso compartido de una pantalla
- Realización de una llamada 

Si las personas implicadas se incluyen en una directiva de barrera de información para evitar la actividad, no podrán continuar. Además, es posible que se bloquee a todos los usuarios incluidos en una directiva de barrera de información para que no puedan comunicarse con otros usuarios de Microsoft Teams. Cuando las personas afectadas por las directivas de barrera de información forman parte de la misma conversación de grupo o equipo, es posible que se eliminen de esas sesiones de chat y que no se permita la comunicación con el grupo.

Para obtener más información sobre la experiencia del usuario con barreras de información, consulte [barreras de la información en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).

## <a name="required-licenses-and-permissions"></a>Permisos y licencias necesarios

Las barreras de información se están implementando ahora y se incluyen en las suscripciones, como:

- Microsoft 365 E5
- Office 365 E5
- Cumplimiento avanzado de Office 365
- Protección de la información y cumplimiento de Microsoft 365 E5

Para obtener más información, consulte [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).

Para [definir o editar directivas de barrera de información](information-barriers-policies.md), debe tener asignado uno de los siguientes roles:

- Administrador global de Microsoft 365
- Administrador global de Office 365
- Administrador de cumplimiento
- IB Compliance Management (este es un nuevo rol)

(Para obtener más información acerca de los roles y los permisos, consulte Permissions [in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)).

Debe estar familiarizado con los cmdlets de PowerShell para poder definir, validar o editar directivas de barrera de información. Aunque proporcionamos varios ejemplos de cmdlets de PowerShell en el [artículo de procedimientos](information-barriers-policies.md), necesitará conocer más detalles, como parámetros, para su organización.

## <a name="next-steps"></a>Pasos siguientes

- [Obtenga más información sobre las barreras de la información en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

- [Ver los atributos que se pueden usar para las directivas de barrera de información](information-barriers-attributes.md)

- [Definir políticas para las barreras de la información](information-barriers-policies.md)

- [Editar (o quitar) directivas de barrera de información](information-barriers-edit-segments-policies.md.md) 


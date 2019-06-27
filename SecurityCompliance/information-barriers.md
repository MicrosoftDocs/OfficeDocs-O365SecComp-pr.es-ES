---
title: Introducción a las barreras de información
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/26/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Usar barreras de la información para garantizar el cumplimiento de la comunicación mediante Microsoft Teams en su organización.
ms.openlocfilehash: 6565fc28d70ac6ff9a6f4df6edc75b89d19ae29a
ms.sourcegitcommit: 1c254108c522d0cb44023565268b5041d07748aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2019
ms.locfileid: "35279478"
---
# <a name="information-barriers-preview"></a>Barreras de la información (versión preliminar)

## <a name="overview"></a>Información general

Los servicios en la nube de Microsoft incluyen eficaces capacidades de comunicación y colaboración. Pero supongamos que desea restringir las comunicaciones entre dos grupos para evitar que se produzca un conflicto de intereses en la organización. O quizás desee restringir las comunicaciones entre determinadas personas dentro de la organización con el fin de proteger la información interna. Microsoft 365 permite la comunicación y la colaboración entre grupos y organizaciones, así que hay una forma de restringir las comunicaciones entre grupos de usuarios específicos cuando sea necesario. Con las barreras de la información, puede hacerlo. 

Las barreras de la información están ahora en versión preliminar, comenzando con Microsoft Teams. Cuando estas características están disponibles para su organización, un administrador de cumplimiento o una barrera de la información pueden definir directivas para permitir o impedir las comunicaciones entre grupos de usuarios en Microsoft Teams. Las directivas de barrera de información se pueden usar para situaciones como estas:

- Un comerciante de día no puede llamar a alguien del equipo de marketing
- El personal de finanzas que trabaja con información de la compañía confidencial no puede recibir llamadas de determinados grupos de la organización
- Un equipo interno con material de secreto comercial no puede llamar o chatear en línea con personas de determinados grupos de la organización
- Un equipo de investigación solo puede llamar o chatear en línea con un equipo de desarrollo del producto

Para todos estos escenarios de ejemplo (y más), se pueden definir directivas de barrera de información para impedir o permitir las comunicaciones en Microsoft Teams. Estas directivas pueden impedir que los usuarios llamen o chatean con ellos que no deben, o bien permitir que los usuarios se comuniquen solo con grupos específicos en Microsoft Teams. Con las directivas de barrera de información en vigor, cada vez que los usuarios que están cubiertos por estas directivas intentan comunicarse con otros usuarios de Microsoft Teams, se realizan comprobaciones para evitar (o permitir) la comunicación (según las directivas de la barrera de información definida). Para obtener más información sobre la experiencia del usuario con barreras de información, consulte [barreras de la información en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).

> [!NOTE]
> Las barreras de información no se aplican a las comunicaciones de correo electrónico o al uso compartido de archivos a través de SharePoint Online o OneDrive. Además, las barreras de información son independientes de los [límites de cumplimiento](set-up-compliance-boundaries.md).

## <a name="required-licenses-and-permissions"></a>Permisos y licencias necesarios

**Actualmente, la característica de barrera de información está en la versión preliminar privada**. Si estas características están disponibles para el público en general, se incluirán en las suscripciones, como:

- Microsoft 365 E5
- Office 365 E5
- Cumplimiento avanzado de Office 365
- Protección de la información y cumplimiento de Microsoft 365 E5

Para obtener más información, consulte [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).

Para [definir o editar directivas de barrera de información](information-barriers-policies.md), debe tener asignado uno de los siguientes roles:

- Administrador global de Microsoft 365
- Administrador global de Office 365
- Administrador de cumplimiento
- Administrador de obstáculos de la información

Debe estar familiarizado con los cmdlets de PowerShell para poder definir, validar o editar directivas de barrera de información. Aunque proporcionamos varios ejemplos de cmdlets de PowerShell en la [información de procedimientos](information-barriers-policies.md), necesitará conocer más detalles, como parámetros, para su organización.

## <a name="concepts-of-information-barrier-policies"></a>Conceptos de las directivas de barrera de información

Es útil conocer los conceptos subyacentes de las directivas de barrera de información:

- **Los atributos** de la cuenta de usuario se definen en Azure Active Directory (o Exchange Online). Estos atributos pueden incluir Departamento, puesto, ubicación, nombre del equipo y otros detalles del perfil del trabajo. 

- Los **segmentos** son conjuntos de usuarios que se definen en el centro de seguridad & cumplimiento de Office 365 con un **atributo de cuenta de usuario**seleccionado. (Consulte la [lista de atributos admitidos](information-barriers-attributes.md)). 

- **Las directivas de barrera de información** determinan límites de comunicación o restricciones. Al definir directivas de barrera de información, puede elegir entre dos tipos de directivas:
    - Las directivas "bloquear" impiden que un segmento se comunique con otro segmento.
    - Las directivas "permitir" permiten que un segmento se comunique con determinados otros segmentos.

- La **aplicación de directivas** se realiza una vez que se han definido todas las directivas de barrera de información y está listo para aplicarlas a la organización.

## <a name="next-steps"></a>Pasos siguientes

- [Obtenga más información sobre las barreras de la información en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [Ver los atributos que se pueden usar para las directivas de barrera de información](information-barriers-attributes.md)
- [Definir políticas para las barreras de la información](information-barriers-policies.md) 


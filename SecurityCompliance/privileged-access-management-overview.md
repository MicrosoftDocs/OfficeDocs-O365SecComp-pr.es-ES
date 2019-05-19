---
title: Administración del acceso con privilegios en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: Use este tema para obtener más información acerca de la administración del acceso con privilegios en Office 365
ms.openlocfilehash: 7547568d6ea2a13de5391d5a827df2921833838c
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157332"
---
# <a name="privileged-access-management-in-office-365"></a>Administración del acceso con privilegios en Office 365

> [!IMPORTANT]
> En este tema se tratan las instrucciones de implementación y configuración de las características disponibles actualmente en Office 365 E5 y las SKU de cumplimiento avanzado.

La administración de acceso privilegiado permite un control de acceso granular sobre las tareas de administración con privilegios en Office 365. Puede ayudar a proteger a su organización de las infracciones que usan cuentas de administrador con privilegios existentes con acceso permanente a los datos confidenciales o al acceso a las opciones de configuración críticas. La administración de acceso privilegiado requiere que los usuarios soliciten acceso puntual para completar las tareas elevadas y privilegiadas a través de un flujo de trabajo de aprobación limitado por el ámbito y de gran alcance. Esto proporciona a los usuarios un acceso suficiente para realizar la tarea a mano, sin arriesgar la exposición de los datos confidenciales o las opciones de configuración críticas. La habilitación de la administración de acceso privilegiada en Office 365 permite que su organización opere con privilegios de cero de posición y proporciona un nivel de defensa contra las vulnerabilidades de acceso administrativo.

Para obtener información general sobre el flujo de trabajo de clientes integrados y el flujo de trabajo de administración de acceso privilegiado, consulte esta [caja de control de acceso de cliente y administración de acceso privilegiada en Office 365 video](https://go.microsoft.com/fwlink/?linkid=2066800).

## <a name="layers-of-protection"></a>Niveles de protección

La administración de acceso privilegiada complementa a otros datos y otras protecciones de características de la arquitectura de seguridad de Office 365. La inclusión de la administración de acceso privilegiada como parte de un enfoque integrado y por capas de la seguridad proporciona un modelo de seguridad que maximiza la protección de la información confidencial y las opciones de configuración de Office 365. Como se muestra en el diagrama, la administración del acceso con privilegios se basa en la protección que se proporciona con el cifrado nativo de los datos de Office 365 y el modelo de seguridad de control de acceso basado en roles de los servicios de Office 365. Cuando se usan con [Azure ad privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), estas dos características proporcionan control de acceso con acceso Just-in-Time en diferentes ámbitos.

![Protección por niveles en Office 365](media/pam-layered-protection.png)

Se define la administración del acceso con privilegios en Office 365 y se aplica un ámbito en el nivel de **tarea** , mientras que la administración de identidades privilegiada de Azure ad aplica protección en el nivel de **rol** con la capacidad de ejecutar varias tareas. Azure AD privileged Identity Management permite básicamente administrar los accesos para los grupos de roles y roles de AD, mientras que la administración de acceso privilegiada en Office 365 solo se aplica en el nivel de tarea.

- **Habilitación de la administración de acceso privilegiada en Office 365 mientras se está usando Azure ad privileged Identity Management:** Agregar una administración de acceso privilegiada en Office 365 proporciona otra capa granular de capacidades de protección y auditoría para el acceso privilegiado a los datos de Office 365.

- **Habilitación de la administración de identidades privilegiada de Azure ad mientras se usa la administración de acceso con privilegios en Office 365:**  Al agregar la administración de identidades privilegiada de Azure AD a la administración de acceso privilegiada en Office 365, se puede extender el acceso privilegiado a los datos fuera de Office 365 que se definen principalmente por los roles de usuario o la identidad.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Arquitectura de administración del acceso privilegiado y flujo del proceso

Cada uno de los siguientes flujos de proceso describe la arquitectura de acceso privilegiado y el modo en que interactúa con el sustrato de Office 365, la auditoría de Office 365 y el espacio de ejecución de administración de Exchange.

### <a name="step-1-configure-a-privileged-access-policy"></a>Paso 1: configurar una directiva de acceso privilegiado

Cuando se configura una directiva de acceso privilegiado con el [centro de administración de Microsoft 365](https://admin.microsoft.com) o PowerShell de administración de Exchange, se define la Directiva y los procesos de características de acceso privilegiado y los atributos de directiva en el sustrato Office 365. Las actividades se registran en el centro de seguridad y cumplimiento de Office 365. La Directiva está ahora habilitada y lista para administrar las solicitudes entrantes para aprobaciones.

![Paso 1: creación de la Directiva](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Paso 2: solicitud de acceso

En el [centro de administración de Microsoft 365](https://admin.microsoft.com) o con PowerShell de administración de Exchange, los usuarios pueden solicitar acceso a tareas elevadas o privilegiadas. La característica de acceso privilegiado envía la solicitud al sustrato de Office 365 para su procesamiento en la Directiva configurada de acceso a privilegios y registra la actividad en los registros del centro de seguridad y cumplimiento de Office 365.

![Paso 2: solicitud de acceso](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Paso 3: aprobación de acceso

Se genera una solicitud de aprobación y la notificación de solicitud pendiente se envíe por correo electrónico a los aprobadores. Si se aprueba, la solicitud de acceso privilegiado se procesa como una aprobación y la tarea está lista para completarse. Si se deniega, la tarea se bloqueará y no se concederá acceso al solicitante. El solicitante recibe la notificación de la aprobación o la denegación de la solicitud mediante un mensaje de correo electrónico.

![Paso 3: aprobación de acceso](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Paso 4: acceso al procesamiento

Para una solicitud aprobada, el espacio de ejecución de administración de Exchange procesa la tarea. La aprobación se comprueba contra la Directiva de acceso privilegiado y la procesa el sustrato de Office 365. Toda la actividad de la tarea se registra en el centro de seguridad y cumplimiento de Office 365.

![Paso 4: acceso al procesamiento](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>¿Qué SKU puede usar el acceso con privilegios en Office 365?
La administración del acceso con privilegios está disponible para los clientes con Office 365 E5 y las SKU de cumplimiento avanzado.

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>¿Cuándo será compatible el acceso a Office 365 cargas de trabajo de Office más allá de Exchange?
La administración del acceso privilegiado estará disponible en otras cargas de trabajo de Office 365 pronto. Visite el [mapa de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para obtener más información.

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>Mi organización necesita más de 30 directivas de acceso privilegiadas, ¿aumentará este límite?
Sí, aumentar el límite actual de 30 directivas de acceso con privilegios por organización de Office 365 se encuentra en la guía básica de características.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>¿Es necesario ser administrador global para administrar el acceso con privilegios en Office 365?
No, necesita la función de administración de roles de Exchange asignada a cuentas que administran el acceso privilegiado en Office 365. Si no desea configurar el rol de administración de roles como un permiso de cuenta independiente, el rol de administrador global incluye esta función de forma predeterminada y puede administrar el acceso privilegiado. Los usuarios incluidos en un grupo de aprobadores no tienen que ser administrador global o tener asignado el rol de administración de roles para revisar y aprobar solicitudes.

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a>¿Cómo es la administración de acceso privilegiada en Office 365 relacionada con caja de caja del cliente?
[Caja de caja del cliente](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) permite un nivel de control de acceso para las organizaciones cuando Microsoft obtiene acceso a los datos. La administración de acceso con privilegios en Office 365 permite un control de acceso granular dentro de una organización para todas las tareas privilegiadas de Office 365.

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

Inicie [la configuración de la organización para la administración del acceso privilegiado](privileged-access-management-configuration.md).

## <a name="learn-more"></a>Más información

[Guía interactiva: supervise y controle las tareas de administrador con privilegios de administración de acceso](https://content.cloudguides.com/en-us/guides/Privileged%20Access%20Management)
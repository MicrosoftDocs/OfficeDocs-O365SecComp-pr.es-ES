---
title: Administración del acceso con privilegios en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
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
ms.openlocfilehash: 2a464bacaa568515e470e29a0c9c45a91a79cf8e
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001253"
---
# <a name="privileged-access-management-in-office-365"></a>Administración del acceso con privilegios en Office 365

> [!IMPORTANT]
> En este tema se tratan las instrucciones de implementación y configuración de las características disponibles actualmente en Office 365 E5 y las SKU de cumplimiento avanzado.

La administración de acceso privilegiado permite un control de acceso granular sobre las tareas de administración con privilegios en Office 365. Puede ayudar a proteger su organización de las infracciones que puedan usar las cuentas de administrador con privilegios existentes con acceso permanente a los datos confidenciales o a las opciones de configuración fundamentales. Después de habilitar la administración del acceso privilegiado, los usuarios necesitarán solicitar acceso puntual para completar las tareas elevadas y privilegiadas a través de un flujo de trabajo de aprobación que tenga un ámbito muy alto y esté limitado por el tiempo. Esto proporciona a los usuarios un acceso suficiente para realizar la tarea a mano, sin arriesgar la exposición de los datos confidenciales o las opciones de configuración críticas. La habilitación de la administración de acceso privilegiada en Office 365 permitirá que su organización opere con privilegios de cero posición y proporcionará una capa de defensa contra las vulnerabilidades que se produzcan a causa del acceso administrativo permanente.

Para obtener una descripción general rápida de la caja de control de clientes integrada y el flujo de trabajo completo de administración del acceso con privilegios, vea esta [caja de control de acceso de cliente y la administración de acceso privilegiada en Office 365 video](https://go.microsoft.com/fwlink/?linkid=2066800).

## <a name="layers-of-protection"></a>Niveles de protección

La administración de acceso privilegiada complementa a otros datos y otras protecciones de características de la arquitectura de seguridad de Office 365. Al habilitar la administración de acceso privilegiada como parte de un enfoque integrado para la seguridad y proteger su organización, se puede usar un modelo de seguridad en capas para maximizar la protección de la información confidencial y las opciones de configuración de Office 365. Como se muestra en el siguiente diagrama, habilitar la administración del acceso con privilegios ayuda a basarse en la protección proporcionada con el cifrado nativo de los datos de Office 365 y el modelo de seguridad de control de acceso basado en roles de los servicios de Office 365. Cuando se usa junto con la administración de identidades privilegiada de [Azure ad](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), estas dos características proporcionan control de acceso con acceso Just-in-Time en diferentes ámbitos.

![Protección por niveles en Office 365](media/pam-layered-protection.png)

La administración del acceso con privilegios en Office 365 puede definirse y tener un ámbito en el nivel de la **tarea** , mientras que Azure ad privileged Identity Management aplica protección en el nivel de **rol** con la capacidad de ejecutar varias tareas.  Azure AD privileged Identity Management permite básicamente administrar los accesos para los grupos de roles y roles de AD, mientras que la administración de acceso privilegiada en Office 365 solo se aplica en el nivel de tarea.

- **Habilitación de la administración de acceso privilegiada en Office 365 mientras se está usando Azure ad privileged Identity Management:** Agregar una administración de acceso privilegiada en Office 365 proporciona otra capa granular de capacidades de protección y auditoría para el acceso privilegiado a los datos de Office 365.

- **Habilitación de la administración de identidadEs privilegiada de Azure ad mientras se usa la administración de acceso con privilegios en Office 365:**  Agregar la administración de identidades privilegiada de Azure AD a la administración de acceso con privilegios en Office 365 puede ampliar el acceso privilegiado a los datos fuera de Office 365 que está definido principalmente por el rol o la identidad del usuario.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Arquitectura de administración del acceso privilegiado y flujo del proceso

Cada uno de los siguientes flujos de proceso describe la arquitectura de acceso privilegiado y el modo en que interactúa con el sustrato de Office 365, la auditoría de Office 365 y el espacio de ejecución de administración de Exchange.

### <a name="step-1-configuring-a-privileged-access-policy"></a>Paso 1: configurar una directiva de acceso privilegiado

Al configurar una directiva de acceso privilegiado con el centro de administración de [Microsoft 365](https://admin.microsoft.com) o PowerShell de administración de Exchange, puede crear y definir la Directiva y la característica de acceso privilegiado procesa los atributos de directiva en el sustrato de Office 365 y registra la actividad en el centro de seguridad y cumplimiento de Office 365. La Directiva está ahora habilitada y lista para administrar las solicitudes entrantes para aprobaciones.

![Paso 1: creación de la Directiva](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Paso 2: solicitud de acceso

Mediante el uso del centro de administración de [Microsoft 365](https://admin.microsoft.com) o de PowerShell de administración de Exchange, los usuarios pueden solicitar acceso a tareas elevadas o privilegiadas. La característica de acceso privilegiado envía la solicitud al sustrato de Office 365 para su procesamiento en la Directiva configurada de acceso a privilegios y registra la actividad en los registros del centro de seguridad y cumplimiento de Office 365.

![Paso 2: solicitud de acceso](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Paso 3: aprobación de acceso

Se genera una solicitud de aprobación y se notifica al grupo de aprobación por correo electrónico de la solicitud pendiente. Si se concede la aprobación, la solicitud de acceso privilegiado se procesa como una aprobación y la tarea está lista para completarse. Si se deniega la solicitud, la tarea se bloquea y no se concede acceso al solicitante. El solicitante recibirá una notificación de la aprobación de la solicitud o de una denegación mediante un mensaje de correo electrónico.

![Paso 3: aprobación de acceso](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Paso 4: acceso al procesamiento

Para las solicitudes aprobadas, el espacio de ejecución de administración de Exchange procesa la tarea. La aprobación se comprueba contra la Directiva de acceso privilegiado y la procesa el sustrato de Office 365. Toda la actividad de la tarea se registra en el centro de seguridad y cumplimiento de Office 365.

![Paso 4: procesamiento de acceso](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="what-skus-do-i-need-to-use-privileged-access-in-office-365"></a>¿Qué SKU necesito para usar el acceso privilegiado en Office 365?
Actualmente, la administración del acceso con privilegios solo está disponible para los clientes con Office 365 E5 y las SKU de cumplimiento avanzadas.

### <a name="when-will-privileged-access-be-available-for-office-365-workloads-beyond-exchange"></a>¿Cuándo estará disponible el acceso con privilegios para cargas de trabajo de Office 365 más allá de Exchange?
Planeamos ofrecer esta característica en otras cargas de trabajo de Office 365 pronto. Cuando esté listo para compartir una escala de tiempo, estará disponible a través del [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).

### <a name="my-organization-needs-more-than-30-privileged-access-polices-will-this-limit-be-increased"></a>Mi organización necesita más de 30 directivas de acceso con privilegios, ¿aumentará este límite?

Estamos planeando aumentar el límite actual de 30 directivas de acceso con privilegios por organización de Office 365 en breve.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>¿Es necesario ser administrador global para administrar el acceso con privilegios en Office 365?
No, debe tener asignada la función de administración de roles de Exchange a las cuentas que administrarán el acceso privilegiado en Office 365. Sin embargo, el rol de administrador global incluye esta función de forma predeterminada y se puede usar para administrar el acceso privilegiado si no desea configurar el rol de administración de roles como un permiso de cuenta independiente. Los usuarios incluidos en un grupo de aprobadores no tienen que ser administrador global o tener el rol de administración de roles asignado para revisar y aprobar solicitudes.

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a>¿Cómo es la administración de acceso privilegiada en Office 365 relacionada con caja de caja del cliente?
[Caja de caja del cliente](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) permite un nivel de control de acceso para que las organizaciones tengan acceso a los datos de su proveedor de servicios, por ejemplo, Microsoft. La administración de acceso con privilegios en Office 365 permite un control de acceso granular dentro de una organización para todas las tareas privilegiadas de Office 365.

---
title: Con privilegios de acceso a la administración de Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Strat_O365_IP
ms.custom: Ent_Solutions
ms.assetid: ''
description: Utilice este tema para obtener más información sobre con privilegios de acceso a la administración de Office 365
ms.openlocfilehash: 07e1f9090418e4261fef188ceb109c1b8083d34c
ms.sourcegitcommit: c168410974bc90aaf55f1dcaa9e05c09b2b78d76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25011866"
---
# <a name="privileged-access-management-in-office-365"></a>Con privilegios de acceso a la administración de Office 365

> [!IMPORTANT]
> En este tema se trata instrucciones de implementación y configuración para características sólo actualmente disponibles en Office 365 E5 y avanzada SKU de cumplimiento.

Con privilegios de acceso permite la administración de control de acceso granular a través de las tareas de administración con privilegios en Office 365.  Puede ayudar a proteger la organización de las infracciones que pueden usar cuentas con privilegios de administración existentes con acceso permanente a los datos confidenciales o acceso a la configuración de configuración crítica. Después de habilitar la administración con privilegios de acceso, los usuarios deberán solicitar acceso just-in-time para completar las tareas con privilegios elevados y con privilegios a través de un flujo de trabajo de aprobación que es altamente con ámbito y límite de tiempo. Esto proporciona a los usuarios just-suficientemente-acceso para realizar la tarea en curso, sin riesgo de exposición de datos confidenciales u opciones de configuración críticos. Habilitación de la administración de acceso con privilegios en Office 365 habilitará la organización operar con cero privilegios permanente y proporcionar un nivel de defensa contra las vulnerabilidades de seguridad que surjan debido a tales acceso administrativo permanente. 

## <a name="layers-of-protection"></a>Capas de protección

Con privilegios de acceso de administración complementa otras protecciones de característica de datos y el acceso dentro de la arquitectura de seguridad de Office 365. Mediante la habilitación de la administración de acceso con privilegios como parte de un enfoque integrado para la seguridad y la protección de la organización, un modelo de seguridad por capas puede usarse para maximizar la protección de información confidencial y opciones de configuración de Office 365. Como se muestra en el siguiente diagrama, habilitar con privilegios ayuda a administración de acceso se basa en la protección que se proporcionan con el cifrado de datos de Office 365 nativo y el modelo de seguridad de control de acceso basado en funciones de servicios de Office 365. Cuando se usa junto con [la administración de identidades AD con privilegios de Azure](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), estas dos características proporcionan control de acceso con acceso just-in-time en los distintos ámbitos.

![Protección de capas en Office 365](media/pam-layered-protection.jpg)

Con privilegios de acceso se puede definir y con ámbito en el nivel de **tarea** , mientras que la administración de identidades AD con privilegios de Azure aplica protección en el nivel de **función** con la capacidad de ejecutar varias tareas de administración de Office 365.  Administración de identidades de Azure con privilegios de AD principalmente permite la administración de acceso para grupos de roles y roles de AD, mientras obtener acceso con privilegios de administración de Office 365 se aplica sólo en el nivel de tarea.

- **Con privilegios de habilitar acceso a administración de Office 365 mientras ya está usando la administración de identidades de AD con privilegios de Azure:** Adición de administración de acceso con privilegios en Office 365 proporciona una capa pormenorizada de las capacidades de protección y auditoría para el acceso a datos de Office 365 con privilegios.

- **Mientras ya está usando la administración de identidades AD con privilegios de habilitación de Azure con privilegios de administración de acceso en Office 365:**  Adición de la administración de identidades con Azure AD privilegios a con privilegios de administración de acceso en Office 365 puede ampliar con privilegios de acceso a datos fuera de Office 365 que principalmente se define por función o la identidad de un usuario.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Flujo de proceso y arquitectura de administración de acceso con privilegios

Cada uno de los flujos de proceso siguientes se describen la arquitectura de acceso privilegiada y cómo interactúa con el sustrato de Office 365, la auditoría de Office 365 y el espacio de ejecución de la administración de Exchange.

### <a name="step-1-configuring-a-privileged-access-policy"></a>Paso 1: Configurar una directiva de acceso con privilegios

Al configurar una directiva de acceso con privilegios mediante el centro de administración de Office 365 o Exchange Management PowerShell, crear y definir la directiva y la característica de acceso con privilegios procesa los atributos de directiva en el sustrato de Office 365 y los registros de la actividad en el centro de cumplimiento y seguridad de Office 365. La directiva está habilitada y está listo para controlar las solicitudes entrantes para las aprobaciones.

![Paso 1: creación de directivas](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Paso 2: Solicitudes de acceso

Mediante el centro de administración de Office 365 o PowerShell de administración de Exchange, los usuarios pueden solicitar el acceso a las tareas con privilegios o con privilegios elevados. La característica de acceso con privilegios envía la solicitud al sustrato de Office 365 para el procesamiento de la directiva de acceso con privilegios configurada y la sctivity de registros en la seguridad de Office 365 y registros de centro de cumplimiento.

![Paso 2: solicitud de acceso](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Paso 3: Aprobación de acceso

Se genera una solicitud de aprobación y el grupo de aprobación es una notificación por correo electrónico de la solicitud pendiente. Si se aprueban, se procesa la solicitud de acceso con privilegios como una aprobación y está lista para completar la tarea. Si se deniega la solicitud, tarea es bloque y no hay acceso a la reqeustor. El solicitante recibirá una notificación de la aprobación de la solicitud o la denegación a través del mensaje de correo electrónico.

![Paso 3: aprobación de acceso](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Paso 4: Procesamiento de acceso

Para las solicitudes aprobadas, se procesa la tarea por el espacio de ejecución de la administración de Exchange. La aprobación se comprobarán con la directiva de acceso con privilegios y procesa el sustrato de Office 365. Toda la actividad de la tarea se registra en el centro de cumplimiento y seguridad de Office 365.

![Paso 4: procesamiento de Access](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="what-skus-do-i-need-to-use-privileged-access-in-office-365"></a>¿Qué SKU es necesario usar access con privilegios en Office 365?
Con privilegios de acceso de administración actualmente sólo está disponible para los clientes con Office 365 E5 y avanzada SKU de cumplimiento.

### <a name="when-will-privileged-access-be-available-for-office-365-workloads-beyond-exchange"></a>¿Cuándo estará disponible para cargas de trabajo de Office 365 más allá de Exchange con privilegios de acceso?
Se planea ofrecer esta característica en otras cargas de trabajo de Office 365 pronto. Cuando estamos listos para compartir una escala de tiempo, estará disponible a través de la guía básica de Office 365.

### <a name="my-organization-needs-more-than-30-privileged-access-polices-will-this-limit-be-increased"></a>Las directivas de las necesidades de mi organización más de 30 acceso con privilegios, se incrementará este límite?

Tenemos planes para aumentar el límite actual de directivas de acceso con privilegios 30 por la organización de Office 365 pronto.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>¿Es necesario ser un administrador Global para administrar el acceso con privilegios en Office 365?
Debe tener privilegios de administrador Global para poder administrar el acceso con privilegios en Office 365. Los usuarios que se incluyen en el grupo de los aprobadores no es necesario ser un administrador Global para revisar y aprobar las solicitudes. 

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a>¿Cómo es la administración de acceso con privilegios en Office 365 relacionadas con la caja de seguridad del cliente?
[Caja de seguridad de cliente](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2) permite a un nivel de control de acceso para las organizaciones para el acceso a datos por su proveedor de servicios, es decir, Microsoft. Con privilegios de acceso de control de acceso granular dentro de una organización para todas las tareas de Office 365 con privilegios permite la administración de Office 365.